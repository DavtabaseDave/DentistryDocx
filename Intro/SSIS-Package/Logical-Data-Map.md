[[_TOC_]]

# Vital note
**If you're unfamiliar with Expressions and/or Data flows in general, see [How To Add/Edit DTSX Packages](/Intro/How-To-Add-Edit-DTSX-Packages)**

# INB Extractions Data Flow Task

This runs several queries in parallel against the Banner Oracle DB via ADO .NET source connections. 
A maximum of 10 is the limit when using Expressions.
The data is temporarily stored in SQL Server holding tables via OLEDB connections. As there
is a 1:1 correspondence between the source queries and the target tables no data conversions
or complicated mappings are required. 

This is pictorially represented by:
 ![INB_Extractions_Data_Flow_Task.PNG](/.attachments/INB_Extractions_Data_Flow_Task-56d4fbc1-6872-4ace-8969-0e445b8ea330.PNG)
NB: Green arrows represent a data source and blue arrows a data destination

## Source queries

Double clicking on the source queries brings up an editor where the connection, Data access mode, and the SQL command
text can be set. This appears thus:
 ![Source _queries.PNG](/.attachments/Source%20_queries-6f663bf7-9c8e-4859-ab29-4daf43fb04f8.PNG)


This is repeated for all the source -> destination mappings as required to fulfill the data requirements

## Data Destination

Double clicking on the data destination brings up an editor where the connection, access mode, target table can be set.
This appears thus (for h_Applicants destination table):
 ![Data_destination.PNG](/.attachments/Data_destination-c2d5aa3a-bd10-4e16-9d9a-507dfa9eda09.PNG)

0. link the source and the destination and then set column mappings (see below)

## Set column mappings

To set/alter the column mappings, click on the "Mappings" item in the list box. This appears thus:
![source_dest_mappings.PNG](/.attachments/source_dest_mappings-29410702-bc68-4fcd-82e6-389f4b467760.PNG)
Mappings can be altered as desired by dragging and dropping, selecting and deleting, etc..

## The actual queries

This section details the plain text queries, the parameterized sections will be pointed out following them 

### Applicants

Here's the raw SQL text. Note the comment near the top detailing the parameterization of age_at_entry in the SqlCommand version:
``` sql
select distinct 
spriden_pidm,
sa.saradap_term_code_entry,
skrsain_applicant_no,
spriden_id,
sa.saradap_appl_no, -- added so that in next stage we can pick max()
skrsain_personalid,
spriden_last_name,
SPRIDEN_FIRST_NAME,
spriden_mi,
SUBSTR (spriden_first_name, 1, 1) || SUBSTR (spriden_mi, 1, 1) as STUDENT_INITIALS,
spbpers_name_prefix,
spbpers_birth_date,
f_calculate_age (NULL, spbpers_birth_date, spbpers_dead_date ) CURRENT_AGE,
f_calculate_age ('01-SEP-2019', spbpers_birth_date, spbpers_dead_date) age_at_entry,
-- paramtereized to: f_calculate_age ('01-SEP-" + @[$Project::AdEntryYear] + "', spbpers_birth_date, spbpers_dead_date) age_at_entry,
spbpers_sex,
sprmedi_disa_code,
skrsain_criminal_conv,
skruccr_ssdt_code_home,
pha.spraddr_street_line1 STREET_ADDRESS_PH_LINE1,
pha.spraddr_street_line2 STREET_ADDRESS_PH_LINE2,
pha.spraddr_street_line3 STREET_ADDRESS_PH_LINE3,
pha.spraddr_city,
pha.spraddr_zip,
substr (decode (pha.spraddr_natn_code, null, null, f_student_get_desc ('STVNATN', pha.spraddr_natn_code, 30 ) ), 1, 30 ) as nation_description_ph,
f_get_tele_no (spriden_pidm, 'PH') telephone_number_ph,
skbspin_natn_code_legal,
saradap_resd_code,
skrsain_appl_date,
f_get_email_addr (sa.saradap_pidm, 'ADM') email_address,
skbuarf_predictedgrades
,skbuarf_activity_date -- used for picking the latest
,lastschl.sorhsch_sbgi_code
,stvsbgi_desc high_school_name
,nvl(cast(SUBSTR(goksels.f_name_bio_value(saradap_pidm,'ETHN'),1,2) as varchar2(2)),'XX') eth_code
,stvdisa_desc
,SKRSAIN_SSDT_CODE_PARED, skrsain_care
From
    skrudap Inner Join saradap sa ON (saradap_term_code_entry = skrudap_term_code_entry AND saradap_appl_no = skrudap_appl_no)
    Inner Join Spriden On (sa.Saradap_Pidm = Spriden_Pidm And Skrudap_Pidm = Spriden_Pidm)
    Inner Join spbpers ON (spbpers_pidm = spriden_pidm)
    Inner Join Skrsain On (Skrudap_Pidm = Skrsain_Pidm And Skrudap_Applicant_No = Skrsain_Applicant_No)
    Inner Join Skruccr On (Skruccr_Pidm = Skrsain_Pidm And Skruccr_Applicant_No = Skrsain_Applicant_No)-- AND saradap_appl_no = Skruccr_appl_no)
    inner join swbslcr on (swbslcr_skrutop_code_crse = skruccr_ssdt_code_crse) -- changed to inner join
    Inner Join Skrutop On (Skrutop_Ssdt_Code_Crse = Skruccr_Ssdt_Code_Crse and Saradap_Majr_Code_1 = Skrutop_Majr_Code)
    left Join sprmedi On (Sprmedi_Pidm = Spriden_Pidm)
    left join stvdisa on (stvdisa_code = sprmedi_disa_code)
    left join spraddr pha on (pha.rowid = f_get_address_type_rowid (spriden_pidm, 'A', sysdate, 'S', 'PH'))
    Left Join Skbspin On (Skbspin_Pidm = Spriden_Pidm)
    left join skbuarf on (skbuarf_pidm = skrsain_pidm and skbuarf_appno = skrsain_applicant_no)
    left join sorhsch lastschl on (lastschl.rowid = f_get_sorhsch_rowid (spriden_pidm, 'LAST'))
    left join stvsbgi on (stvsbgi_code = lastschl.sorhsch_sbgi_code)
where spriden_change_ind   is null
  and spbpers_dead_ind is null
  and sprmedi_disa_code is not null
  and saradap_levl_code      in ('UG', 'MD', 'DE')
  and swbslcr_swvslcn_code = '1K'
  AND SKRUCCR_PROP_ENTRY_YR >= '2019'
  and skruccr_applicant_no > '180000000'
  and skrsain_appl_date > to_date('31-AUG-17','DD-MON-YY')
  and skruccr_ssdt_code_sbgi  = 'L23'
```
In the SqlCommand the last five lines are parameterized thus:
```
  "and swbslcr_swvslcn_code = '" + @[$Project::AdDentSelectorCentre] + "'
  AND SKRUCCR_PROP_ENTRY_YR >= '" + @[$Project::AdEntryYear] + "'
  and skruccr_applicant_no > '" + @[$Project::AdApplNoMask] + "'
  and skrsain_appl_date > to_date('31-AUG-" + @[$Project::AdPrevYear] + "','DD-MON-YY')
  and skruccr_ssdt_code_sbgi  = 'L23'"
```

### Applicant's Decisions


Here's the raw SQL text. Note the comment near the middle detailing the parameterization of isDeferred in the SqlCommand version:
``` sql
select
	distinct
	skruccr_pidm,
	skruccr_applicant_no,
	skruccr_choice_type_no,
	skruccr_ssdt_code_crse,
	crse.skrutop_program program_code,
	substr(f_get_long_progtitle(crse.skrutop_program,crse.skrutop_term_code_eff),1,255) program_desc,
	skrsain_ssdt_code_cwd_flg,
	skruccr_ssdt_code_decn,
	skruccr_decision_date,
	skrudec_trans_status,
	skruccr_ssdt_code_reply,
	skruccr_ssdt_code_cf_decn,
	skruccr_ssdt_code_ap_resp,
	skruccr_prop_entry_yr,
	skruccr_prop_entry_mth,
	skruccr_conditions,
	skruccr_ssdt_code_entry
  ,(case 
    when skruccr_prop_entry_yr >= '2019'+1 then 1
    else 0
    end) isDeferred

from skruccr s1
  inner join skrutop crse on (crse.skrutop_ssdt_code_crse = s1.skruccr_ssdt_code_crse
                             and (crse.skrutop_ssdt_code_camp      = s1.skruccr_ssdt_code_camp
                                  or crse.skrutop_ssdt_code_camp   is null
                                  or s1.skruccr_ssdt_code_camp        is null)
                             )
  inner join skrsain on (s1.skruccr_pidm = skrsain_pidm
                      and s1.skruccr_applicant_no = skrsain_applicant_no)
 left join swbslcr on swbslcr_skrutop_code_crse = s1.skruccr_ssdt_code_crse
  left join skrudec sd on sd.rowid = F_Get_Skrudec_Rowid(skruccr_applicant_no,skruccr_choice_type,skruccr_choice_type_no)
where swbslcr_swvslcn_code = '1K'
  and s1.skruccr_applicant_no > '180000000'
  and s1.skruccr_prop_entry_yr >= '2019'
  AND s1.skruccr_ssdt_code_sbgi        = 'L23'
  AND crse.skrutop_term_code_eff   =
    (SELECT MAX(a.skrutop_term_code_eff)
    FROM SKRUTOP a
    WHERE a.skrutop_ssdt_code_crse = skruccr_ssdt_code_crse)
```
