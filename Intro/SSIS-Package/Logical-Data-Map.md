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

Here's the raw SQL text. Note the comment near the top detailing the parameterization of age_at_entry from the SqlCommand version:
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
-- parameterized to: f_calculate_age ('01-SEP-" + @[$Project::AdEntryYear] + "', spbpers_birth_date, spbpers_dead_date) age_at_entry,
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
``` sql
"... 
  and swbslcr_swvslcn_code = '" + @[$Project::AdDentSelectorCentre] + "'
  AND SKRUCCR_PROP_ENTRY_YR >= '" + @[$Project::AdEntryYear] + "'
  and skruccr_applicant_no > '" + @[$Project::AdApplNoMask] + "'
  and skrsain_appl_date > to_date('31-AUG-" + @[$Project::AdPrevYear] + "','DD-MON-YY')
  and skruccr_ssdt_code_sbgi  = 'L23'"
```

### Applicant's Decisions


Here's the raw SQL text. Note the comment near the middle detailing the parameterization of isDeferred from the SqlCommand version:
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
-- parameterized to: when skruccr_prop_entry_yr >= '" + @[$Project::AdEntryYear]  + "'+1 then 1

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
The first three lines of the `where` clause are parameterized like so in the SqlCommand version
```
" … 
where swbslcr_swvslcn_code = '" + @[$Project::AdDentSelectorCentre] + "'
  and s1.skruccr_applicant_no > '" + @[$Project::AdApplNoMask] + "'
  and s1.skruccr_prop_entry_yr >= '" + @[$Project::AdEntryYear] + "'
  AND … "
```

### Offers

``` sql
select
gurmail_pidm,
gurmail_letr_code,
substr(gurmail_letr_code, 6, 1) as offer_letter,
substr(gurmail_letr_code, 8, 1) as offer_choice_no,
gurmail_term_code,
gurmail_date_printed,
gurmail_user
,gurmail_cpln_code 
from gurmail
where gurmail_letr_code like 'UCAS____'
  and gurmail_term_code >= '201920'
```
The last line of the `where` clause is parameterized like so in the SqlCommand version

```
" … 
  and gurmail_term_code >= '" + @[$Project::AdTermCodeEntry] + "'"
```

### Results

``` sql
select sortest_pidm, ltrim(sys_connect_by_path(subject_result,'; '),'; ') actual_results
  from (select sortest_pidm,
        (case nvl(sortest_tadm_code, 'empty')
          when 'empty' then stvtesc_desc || ': ' || sortest_test_score
          else stvtadm_desc || ' ' || stvtesc_desc || ': ' || sortest_test_score/* || ' (' || sortest_tadm_code || ')'*/
        end)subject_result,
        row_number() over (partition by sortest_pidm order by sortest_tesc_code) rn,
        count(*) over (partition by sortest_pidm) cnt
        from sortest inner join stvtesc on sortest_tesc_code = stvtesc_code
            inner join stvtadm on sortest_tadm_code = stvtadm_code
        where sortest_pidm in (
SELECT
  DISTINCT SPRIDEN_PIDM as PIDM
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
where spriden_change_ind   is null
  and spbpers_dead_ind is null
  and sprmedi_disa_code is not null
  and saradap_levl_code      in ('UG', 'MD', 'DE')
  and swbslcr_swvslcn_code = '1K'
  AND SKRUCCR_PROP_ENTRY_YR >= '2019'
  and skruccr_applicant_no > '180000000'
  and skrsain_appl_date > to_date('31-AUG-17','DD-MON-YY')
  and skruccr_ssdt_code_sbgi  = 'L23'
))
where rn = cnt
start with rn = 1
connect by prior sortest_pidm = sortest_pidm and prior rn = rn - 1
```
The inner `where` clause are parameterized like so in the SqlCommand version
```
" … 
where spriden_change_ind   is null
  and spbpers_dead_ind is null
  and sprmedi_disa_code is not null
  and saradap_levl_code      in ('UG', 'MD', 'DE')
  and swbslcr_swvslcn_code = '" + @[$Project::AdDentSelectorCentre] + "'
  AND SKRUCCR_PROP_ENTRY_YR >= '" + @[$Project::AdEntryYear] + "'
  and skruccr_applicant_no > '" + @[$Project::AdApplNoMask] + "'
  and skrsain_appl_date > to_date('31-AUG-" + @[$Project::AdPrevYear] + "','DD-MON-YY')
  and skruccr_ssdt_code_sbgi  = 'L23'
))
… 
```

### A2L Running Record (A2L_RR)

``` sql
select 
  SARCHRT_PIDM
  ,sp.SPRIDEN_ID
  ,SKRSAIN_PERSONALID
  ,sp.SPRIDEN_FIRST_NAME,
   sp.SPRIDEN_LAST_NAME,
   SKRUCCR_SSDT_CODE_CRSE,
   f_get_program_desc(SORLCUR_PROGRAM,30) Programme,
   DECODE((select SARCHRT2.SARCHRT_CHRT_CODE
     from SARCHRT SARCHRT2
    where SARCHRT2.SARCHRT_PIDM = sc.SARCHRT_PIDM
          and SARCHRT2.SARCHRT_TERM_CODE_ENTRY = sc.SARCHRT_TERM_CODE_ENTRY
          and SARCHRT2.SARCHRT_APPL_NO = sc.SARCHRT_APPL_NO
          and SARCHRT2.SARCHRT_CHRT_CODE in('A2LELG','A2LNOT')), 'A2LELG', 'Eligible', 'A2LNOT', 'Not Eligible', 'Awaiting Assessment') A2L_Eligibility_Decision,
   SARADAP_TERM_CODE_ENTRY,
   (select Count( SARADAP1.SARADAP_APPL_NO )
        from SARADAP SARADAP1
        where SARADAP1.SARADAP_PIDM = sd.SARADAP_PIDM
        and SARADAP1.SARADAP_TERM_CODE_ENTRY = SARCHRT_TERM_CODE_ENTRY ) Number_Courses_Applied_For,
   (CASE WHEN SARCHRT_CHRT_CODE = 'A2LAPP' THEN 'Route 1'
   ELSE 'Route 2' END) A2L_Route,
   (CASE WHEN SARCHRT_CHRT_CODE = 'A2LAPP' THEN to_char(SARCHRT_ACTIVITY_DATE,'dd/mm/yyyy')
   ELSE '' END) A2L_Application_Received,
   (select to_char(SARCHRT1.SARCHRT_ACTIVITY_DATE,'dd/mm/yyyy')
     from SARCHRT SARCHRT1
    where SARCHRT1.SARCHRT_PIDM = sc.SARCHRT_PIDM
          and SARCHRT1.SARCHRT_TERM_CODE_ENTRY = sc.SARCHRT_TERM_CODE_ENTRY
          and SARCHRT1.SARCHRT_APPL_NO = sc.SARCHRT_APPL_NO
          and SARCHRT1.SARCHRT_CHRT_CODE in('A2LELG','A2LNOT')) A2L_Decision_Date
   --,SKRSAIN_UCAS_APP_DATE UCAS_App_Date
from  SARCHRT sc
  inner join SARADAP sd on SARCHRT_PIDM = SARADAP_PIDM
                     and SARCHRT_TERM_CODE_ENTRY = SARADAP_TERM_CODE_ENTRY
                     and SARCHRT_APPL_NO = SARADAP_APPL_NO
  inner join SPRIDEN sp on SARCHRT_PIDM = sp.SPRIDEN_PIDM
  inner join SKRUDAP on SARADAP_PIDM = SKRUDAP_PIDM
                     and SARADAP_TERM_CODE_ENTRY = SKRUDAP_TERM_CODE_ENTRY
                     and SARADAP_APPL_NO = SKRUDAP_APPL_NO
  inner join SKRSAIN sk on SKRUDAP_APPLICANT_NO = SKRSAIN_APPLICANT_NO
  inner join SKRUCCR on SKRUDAP_APPLICANT_NO = SKRUCCR_APPLICANT_NO
                     and SKRUDAP_CHOICE_NO = SKRUCCR_CHOICE_TYPE_NO
  inner join SORLCUR on SARADAP_PIDM = SORLCUR_PIDM
                     and SARADAP_TERM_CODE_ENTRY = SORLCUR_TERM_CODE
                     and SARADAP_APPL_NO = SORLCUR_KEY_SEQNO
  inner join SORLFOS on SORLCUR_PIDM = SORLFOS_PIDM
                     and SORLCUR_SEQNO = SORLFOS_LCUR_SEQNO
                     and SORLCUR_TERM_CODE = SORLFOS_TERM_CODE
  inner join SKBUSTN skb on SKRSAIN_APPLICANT_NO = skb.SKBUSTN_APPNO
                     and SKRSAIN_PERSONALID = skb.SKBUSTN_PERSONALID
                     and SKRSAIN_APP_SCHEME_CODE = skb.SKBUSTN_APP_SCHEME_CODE
  inner join SPBPERS on sp.SPRIDEN_PIDM = SPBPERS.SPBPERS_PIDM
where  SARCHRT_CHRT_CODE in('A2LAPP','A2LELG')
  and SARCHRT_TERM_CODE_ENTRY in ('201920', '201920'+101) 
  and SORLCUR_COLL_CODE ='MH'
  and SORLCUR_LMOD_CODE ='ADMISSIONS'
  and SORLCUR_CURRENT_CDE ='Y'
  and SORLFOS_DEPT_CODE ='DENT'
  and SORLFOS_CURRENT_CDE ='Y'
  and sp.SPRIDEN_CHANGE_IND is null
  and skb.SKBUSTN_APPLICATIONYEAR = '2019'
  and SARCHRT_CHRT_CODE =
      (select Min( SARCHRT3.SARCHRT_CHRT_CODE ) Min_SARCHRT_CHRT_CODE
         from SARCHRT SARCHRT3
        where SARCHRT3.SARCHRT_PIDM = sc.SARCHRT_PIDM
              and SARCHRT3.SARCHRT_TERM_CODE_ENTRY = sc.SARCHRT_TERM_CODE_ENTRY
              and SARCHRT3.SARCHRT_APPL_NO = sc.SARCHRT_APPL_NO
              and SARCHRT3.SARCHRT_CHRT_CODE in('A2LAPP','A2LELG'))
    and not exists (select SARCHRT4.SARCHRT_CHRT_CODE Not_Eligible
                from SARCHRT SARCHRT4
               where SARCHRT4.SARCHRT_PIDM = sc.SARCHRT_PIDM
                     and SARCHRT4.SARCHRT_TERM_CODE_ENTRY = sc.SARCHRT_TERM_CODE_ENTRY
                     and SARCHRT4.SARCHRT_APPL_NO = sc.SARCHRT_APPL_NO
                     and SARCHRT4.SARCHRT_CHRT_CODE ='A2LNOT')
  and skb.SKBUSTN_SEQ =
    (select Max( SKBUSTN1.SKBUSTN_SEQ ) Max_SKBUSTN_SEQ
       from SKBUSTN SKBUSTN1
      where SKBUSTN1.SKBUSTN_APPNO = sk.SKRSAIN_APPLICANT_NO
            and SKBUSTN1.SKBUSTN_PERSONALID =sk. SKRSAIN_PERSONALID
            and SKBUSTN1.SKBUSTN_APPLICATIONYEAR = '2019'
            and SKBUSTN1.SKBUSTN_APP_SCHEME_CODE = sk.SKRSAIN_APP_SCHEME_CODE)
```
The `where` clause is parameterized like so in the SqlCommand version
```
" … 
where  SARCHRT_CHRT_CODE in('A2LAPP','A2LELG')
  and SARCHRT_TERM_CODE_ENTRY in ('" + @[$Project::AdTermCodeEntry]  + "', '" + @[$Project::AdTermCodeEntry]  + "'+101) 
  and SORLCUR_COLL_CODE ='" + @[$Project::AdDentFacCode]  + "'
  and SORLCUR_LMOD_CODE ='ADMISSIONS'
  and SORLCUR_CURRENT_CDE ='Y'
  and SORLFOS_DEPT_CODE ='" + @[$Project::AdDentSchoolCode]  + "'
  and SORLFOS_CURRENT_CDE ='Y'
  and sp.SPRIDEN_CHANGE_IND is null
  and skb.SKBUSTN_APPLICATIONYEAR = '" +  @[$Project::AdEntryYear] + "'
  and SARCHRT_CHRT_CODE =
      (select Min( SARCHRT3.SARCHRT_CHRT_CODE ) Min_SARCHRT_CHRT_CODE
         from SARCHRT SARCHRT3
        where SARCHRT3.SARCHRT_PIDM = sc.SARCHRT_PIDM
              and SARCHRT3.SARCHRT_TERM_CODE_ENTRY = sc.SARCHRT_TERM_CODE_ENTRY
              and SARCHRT3.SARCHRT_APPL_NO = sc.SARCHRT_APPL_NO
              and SARCHRT3.SARCHRT_CHRT_CODE in('A2LAPP','A2LELG'))
    and not exists (select SARCHRT4.SARCHRT_CHRT_CODE Not_Eligible
                from SARCHRT SARCHRT4
               where /*:parm_CB_HideNotEligible = 1
                     and */SARCHRT4.SARCHRT_PIDM = sc.SARCHRT_PIDM
                     and SARCHRT4.SARCHRT_TERM_CODE_ENTRY = sc.SARCHRT_TERM_CODE_ENTRY
                     and SARCHRT4.SARCHRT_APPL_NO = sc.SARCHRT_APPL_NO
                     and SARCHRT4.SARCHRT_CHRT_CODE ='A2LNOT')
  and skb.SKBUSTN_SEQ =
    (select Max( SKBUSTN1.SKBUSTN_SEQ ) Max_SKBUSTN_SEQ
       from SKBUSTN SKBUSTN1
      where SKBUSTN1.SKBUSTN_APPNO = sk.SKRSAIN_APPLICANT_NO
            and SKBUSTN1.SKBUSTN_PERSONALID =sk. SKRSAIN_PERSONALID
            and SKBUSTN1.SKBUSTN_APPLICATIONYEAR = '" + @[$Project::AdEntryYear]  + "'
            and SKBUSTN1.SKBUSTN_APP_SCHEME_CODE = sk.SKRSAIN_APP_SCHEME_CODE)"
```

### Nationalities (stvnatn)

Not parameterized 
``` sql
select s1.skvssdt_sdat_code_opt_1, s1.skvssdt_short_title
from Skvssdt s1
where s1.skvssdt_sdat_code_entity = 'SKBSPIN'
  and s1.skvssdt_sdat_code_attr = 'SKBSPIN_NATN_CODE_LEGAL'
  and s1.skvssdt_status_ind <> 'I'
  AND s1.skvssdt_eff_date =
           (select  max(skvssdt_eff_date)
             from    skvssdt s2
            WHERE   s2.skvssdt_sdat_code_entity = 'SKBSPIN'
              and   s2.skvssdt_sdat_code_attr = 'SKBSPIN_NATN_CODE_LEGAL'
              and   s2.skvssdt_sdat_code_opt_1 = s1.skvssdt_sdat_code_opt_1)
```

### Ethnicity (stvethn)

Not parameterized 
``` sql
select
  stvethn_code
  ,stvethn_desc
from stvethn
```