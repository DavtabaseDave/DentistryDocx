[[_TOC_]]

# SSIS Import Holding Tables

These are used as temporary stores for Banner data as it is first extract by the SSIS DTSX package.
As they permit duplicates they have to be cleared before and after use.

## h_Applicants

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fh_Applicants.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|----------|--------------|
| SPRIDEN_PIDM	| numeric	| 	| 	|
| SARADAP_TERM_CODE_ENTRY	| nvarchar	| 6	| 	|
| SKRSAIN_APPLICANT_NO	| nvarchar	| 9	| 	|
| SPRIDEN_ID	| nvarchar	| 9	| 	|
| SARADAP_APPL_NO	| numeric	| 	| 	|
| SKRSAIN_PERSONALID	| nvarchar	| 10	| Yes |
| SPRIDEN_LAST_NAME	| nvarchar	| 60	| 	|
| SPRIDEN_FIRST_NAME	| nvarchar	| 60	| Yes |
| SPRIDEN_MI	| nvarchar	| 60	| Yes |
| STUDENT_INITIALS	| nvarchar	| 2	| Yes |
| SPBPERS_NAME_PREFIX	| nvarchar	| 20	| Yes |
| SPBPERS_BIRTH_DATE	| datetime2	| 	| Yes |
| CURRENT_AGE	| nvarchar	| 384	| Yes |
| AGE_AT_ENTRY	| nvarchar	| 384	| Yes |
| SPBPERS_SEX	| nvarchar	| Yes | Yes |
| SPRMEDI_DISA_CODE	| nvarchar	| 2	| Yes |
| SKRSAIN_CRIMINAL_CONV	| nvarchar	| Yes | Yes |
| SKRUCCR_SSDT_CODE_HOME	| nvarchar	| Yes | Yes |
| STREET_ADDRESS_PH_LINE1	| nvarchar	| 75	| Yes |
| STREET_ADDRESS_PH_LINE2	| nvarchar	| 75	| Yes |
| STREET_ADDRESS_PH_LINE3	| nvarchar	| 75	| Yes |
| SPRADDR_CITY	| nvarchar	| 50	| Yes |
| SPRADDR_ZIP	| nvarchar	| 30	| Yes |
| NATION_DESCRIPTION_PH	| nvarchar	| 30	| Yes |
| TELEPHONE_NUMBER_PH	| nvarchar	| 4000	| Yes |
| SKBSPIN_NATN_CODE_LEGAL	| nvarchar	| 50	| Yes |
| SARADAP_RESD_CODE	| nvarchar	| Yes | 	|
| SKRSAIN_APPL_DATE	| datetime2	| 	| Yes |
| EMAIL_ADDRESS	| nvarchar	| 4000	| Yes |
| SKBUARF_PREDICTEDGRADES	| nvarchar	| 1000	| Yes |
| SKBUARF_ACTIVITY_DATE	| datetime2	| 	| Yes |
| SORHSCH_SBGI_CODE	| nvarchar	| 6	| Yes |
| HIGH_SCHOOL_NAME	| nvarchar	| 30	| Yes |
| ETH_CODE	| nvarchar	| 2	| Yes |
| STVDISA_DESC	| nvarchar	| 30	| Yes |
| SKRSAIN_SSDT_CODE_PARED	| nvarchar	| Yes | Yes |
| skrsain_care	| nvarchar	| 10	| Yes |

## h_Decisions

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fh_Decisions.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|----------|--------------|
| SKRUCCR_PIDM	| numeric	| 	| |
| SKRUCCR_APPLICANT_NO	| nvarchar	| 9	| |
| SKRUCCR_CHOICE_TYPE_NO	| nvarchar	| 2	| |
| SKRUCCR_SSDT_CODE_CRSE	| nvarchar	| 12	| Yes |
| PROGRAM_CODE	| nvarchar	| 12	| Yes |
| PROGRAM_DESC	| nvarchar	| 255	| Yes |
| SKRSAIN_SSDT_CODE_CWD_FLG	| nvarchar	| 1 | Yes |
| SKRUCCR_SSDT_CODE_DECN	| nvarchar	| 3	| Yes |
| SKRUCCR_DECISION_DATE	| datetime2	| 	| Yes |
| SKRUDEC_TRANS_STATUS	| nvarchar	| 2	| Yes |
| SKRUCCR_SSDT_CODE_REPLY	| nvarchar	| 3	| Yes |
| SKRUCCR_SSDT_CODE_CF_DECN	| nvarchar	| 1 | Yes |
| SKRUCCR_SSDT_CODE_AP_RESP	| nvarchar	| 1 | Yes |
| SKRUCCR_PROP_ENTRY_YR	| numeric	| 	| Yes |
| SKRUCCR_PROP_ENTRY_MTH	| numeric	| 	| Yes |
| SKRUCCR_CONDITIONS	| nvarchar	| 6	| Yes |
| SKRUCCR_SSDT_CODE_ENTRY	| nvarchar	| 1 | Yes |
| isDeferred	| bit	| 	| Yes |

## h_A2L_RR

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fh_A2L_RR.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|----------|--------------|
| sarchrt_pidm	| int	| 	| 	|
| spriden_id	| nvarchar	| 1	| 	|
| skrsain_personalid	| nvarchar	| 1	| 	|
| spriden_first_name	| nvarchar	| 35	| 	|
| spriden_last_name	| nvarchar	| 35	| 	|
| skruccr_ssdt_code_crse	| nvarchar	| 1	| 	|
| Programme	| nvarchar	| 4	| 	|
| A2L_Eligibility_Decision	| nvarchar	| 25	| 	|
| saradap_term_code_entry	| nvarchar	| 6	| 	|
| Number_Courses_Applied_For	| tinyint	| 	| 	|
| A2L_Route	| nvarchar	| 1	| 	|
| A2L_Application_Received	| datetime	| 	| Yes	
| A2L_Decision_Date	| datetime	| 	| Yes	|

## h_Offers

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fh_Offers.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|----------|--------------|
| GURMAIL_PIDM	| numeric	| 	| 	|
| GURMAIL_LETR_CODE	| nvarchar	| 15	| Yes	|
| OFFER_LETTER	| nvarchar	| 1	| Yes	|
| OFFER_CHOICE_NO	| nvarchar	| 1	| Yes	|
| GURMAIL_TERM_CODE	| nvarchar	| 6	| Yes	|
| GURMAIL_DATE_PRINTED	| datetime2	| 	| Yes	|
| GURMAIL_USER	| nvarchar	| 30	| Yes	|
| GURMAIL_CPLN_CODE	| nvarchar	| 4	| Yes	|

## h_Results

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fh_Results.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|----------|--------------|
| SORTEST_PIDM	|numeric	|| Yes	|
| ACTUAL_RESULTS	| nvarchar	| 1000 | Yes	|

## h_stvethn

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fh_stvethn.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|----------|--------------|
| stvethn_code	| nvarchar	| 2 | |
| stvethn_desc	| nvarchar	| 30 ||

## h_stvnatn

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fh_stvnatn.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|----------|--------------|
| SKVSSDT_SDAT_CODE_OPT_1	| nvarchar	| 8||
| SKVSSDT_SHORT_TITLE	| nvarchar	| 35 ||

# XSLX Import Holding Tables

These table are *NOT* standard user visible, they are for administrative use only. They are intended for importing data from XLSX files before being transformed into user visible tables. Unlike normal tables they don't have Primary Keys as the data is not guaranteed to be in any "normal" form. Also, as the importer program may include the odd blank row all the fields must be null-able :(

## A2L_Passlist$

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FA2L_Passlist_.sql&version=GBmaster)
*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Data Length | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|--------------|
| First Name	| nvarchar	| 255 | Yes	|
| Surname	| nvarchar	| 255 | Yes	|
| UCAS ID	| float	| |Yes	|
| Banner ID	| nvarchar	| 255 | Yes	|
| Route	| float	| |Yes	|
| Course Code	| nvarchar	| 255 | Yes	|
| Programme	| nvarchar	| 255 | Yes	|
| Offer status	| nvarchar	| 255 | Yes	|
| Study Skills Pass	| nvarchar	| 255 | Yes	|
| Subject Mark	| nvarchar	| 255 | Yes	|
| A2L Pass	| nvarchar	| 255 | Yes	|
| pidm	| int	| | Yes	| set by import routine |

## Academic_Scores$

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FAcademic_Scores_.sql&version=GBmaster)
*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Data Length | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|--------------|
| PIDM	| float	| |Yes	| **NOT** set by import routine |
| Scorer Name	| nvarchar	| 255 | Yes	| |
| Leeds Code	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE English	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE Maths	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE Biology or Science	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE Chemistry or Science	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE other 1	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE other 2	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE other 3	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE other 4	| nvarchar	| 255 | Yes	| |
| Standard entry - GCSE other 5	| nvarchar	| 255 | Yes	| |
| Standard entry - A2	| nvarchar	| 255 | Yes	| |
| Graduate English GCSE	| nvarchar	| 255 | Yes	| |
| Graduate Maths GCSE	| nvarchar	| 255 | Yes	| |
| Graduate Biology GCSE	| nvarchar	| 255 | Yes	| |
| Graduate Chemistry GCSE	| nvarchar	| 255 | Yes	| |
| Graduate GCSE any 1	| nvarchar	| 255 | Yes	| |
| Graduate GCSE Any 2	| nvarchar	| 255 | Yes	| |
| Graduate A-level Biology	| nvarchar	| 255 | Yes	| |
| Graduate A-level Chemistry	| nvarchar	| 255 | Yes	| |
| Graduate Third Subject	| nvarchar	| 255 | Yes	| |
| Graduate Other A-level 1	| nvarchar	| 255 | Yes	| |
| Graduate Other A-level 2	| nvarchar	| 255 | Yes	| |
| Graduate - Degree name	| nvarchar	| 255 | Yes	| |
| Graduate - Degree classification Degree	| nvarchar	| 255 | Yes	| |
| A2HE DHDT only	| nvarchar	| 255 | Yes	| |
| Total	| float	| | Yes	| |

## All MMI Rankings$

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FAll_MMI_Rankings_.sql&version=GBmaster)

*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Data Length | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|--------------|
| Candidate_number	| nvarchar	| 255	| Yes	|
| Candidate_Name	| nvarchar	| 255	| Yes	|
| Course	| nvarchar	| 255	| Yes	|
| Cohort_Ranked_In	| nvarchar	| 255	| Yes	|
| Mean_Task	| float	| 	| Yes	|
| Mean_Rank_Task	| float	| 	| Yes	|
| Offer_Cutoff	| float	| 	| Yes	|
| Mean_Task_Low_score_removed	| float	| 	| Yes	|
| Rank_Task_low_score_removed	| float	| 	| Yes	|
| Rank_Difference	| float	| 	| Yes	|
| Station_1_Mean_Percentile_Rank	| float	| 	| Yes	|
| Station_1_Quartile_Rank	| nvarchar	| 255	| Yes	|
| Station_2_Mean_Percentile_Rank	| float	| 	| Yes	|
| Station_2_Quartile_Rank	| nvarchar	| 255	| Yes	|
| Station_3_Mean_Percentile_Rank	| float	| 	| Yes	|
| Station_3_Quartile_Rank	| nvarchar	| 255	| Yes	|
| Station_4_Mean_Percentile_Rank	| float	| 	| Yes	|
| Station_4_Quartile_Rank	| nvarchar	| 255	| Yes	|
| Station_5_Mean_Percentile_Rank	| float	| 	| Yes	|
| Station_5_Quartile_Rank	| nvarchar	| 255	| Yes	|
| Station_6_Mean_Percentile_Rank	| float	| 	| Yes	|
| Station_6_Quartile_Rank	| nvarchar	| 255	| Yes	|
| Station_7_Mean_Percentile_Rank	| float	| 	| Yes	|
| Station_7_Quartile_Rank	| nvarchar	| 255	| Yes	|
| Station_8_Mean_Percentile_Rank	| float	| 	| Yes	|
| Station_8_Quartile_Rank	| nvarchar	| 255	| Yes	|

## BMAT_Scores$

XLSX import table for BMAT Scores. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FBMAT_Scores_.sql&version=GBmaster)

*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Data Length | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|--------------|
| Centre Number	| nvarchar	| 255 | Yes	|
| Centre Name	| nvarchar	| 255 | Yes	|
| CandidateID	| float	| | Yes	|
| BannerID	| nvarchar	| 255 | Yes	|
| Forenames	| nvarchar	| 255 | Yes	|
| Surname	| nvarchar	| 255 | Yes	|
| Test	| nvarchar	| 255 | Yes	|
| Date of Birth	| datetime |	| Yes	|
| Gender	| nvarchar	| 255 | Yes	|
| Special Considerations	| nvarchar	| 255 | Yes	|
| Section Yes Score	| float	| | Yes	|
| Section 2 Score	| float	| | Yes	|
| Essay Answered	| nvarchar	| 255 | Yes	|
| Section 3 Content	| float	| | Yes	|
| Section 3 English	| nvarchar	| 255 | Yes	|
| Section 3 English Score	| float	| | Yes	|
| Overall Score	| float	| | Yes	|
| Overall Rank	| float	| | Yes	|
| Absent Flag	| nvarchar	| 255 | Yes	|
| UCASID	| float	| | Yes	|
| Institution	| nvarchar	| 255 | Yes	|
| Course Code	| nvarchar	| 255 | Yes	|
| Time Zone	| float	| | Yes	|
| OptionalID	| nvarchar	| 255 | Yes	|

## DHDT_RejFdbkLetter$

XLSX import table for DHDT_RejFdbkLetter$. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FDHDT_RejFdbkLetter_.sql&version=GBmaster)

*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Data Length | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|--------------|
| PERSONAL_ID	| nvarchar	| 255 | Yes	|
| STUDENT_ID	| nvarchar	| 255 | Yes	|
| STUDENT_FIRST_NAME	| nvarchar	| 255 | Yes	|
| STUDENT_LAST_NAME	| nvarchar	| 255 | Yes	|
| EMAIL_ADDRESS	| nvarchar	| 255 | Yes	|
| STREET_ADDRESS_PH_LINEYes	| nvarchar	| 255 | Yes	|
| STREET_ADDRESS_PH_LINE2	| nvarchar	| 255 | Yes	|
| STREET_ADDRESS_PH_LINE3	| nvarchar	| 255 | Yes	|
| CITY_PH	| nvarchar	| 255 | Yes	|
| POSTCODE_PH	| nvarchar	| 255 | Yes	|
| NATION_DESCRIPTION_PH	| nvarchar	| 255 | Yes	|
| Life Experience and Social Awareness:	| nvarchar	| 255 | Yes	|
| Motivation And Insight	| nvarchar	| 255 | Yes	|
| Reflective Skills	| nvarchar	| 255 | Yes	|
| Interests and Achievements	| nvarchar	| 255 | Yes	|

## IFY$

XLSX import table for IFY applicants..  Also used for importing ISFY and PHE applicants Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FIFY_.sql&version=GBmaster)

*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Data Length | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|--------------|
| PIDM_KEY	| float	| | Yes	|
| TERM_CODE_KEY	| float	| | Yes	|
| SELECTOR_CENTRE_CODE	| nvarchar	| 255 | Yes	|
| LEVEL_CODE	| nvarchar	| 255 | Yes	|
| PERSONAL_ID	| nvarchar	| 255 | Yes	|
| SCHEME_CODE	| nvarchar	| 255 | Yes	|
| UCAS_ID_KEY	| nvarchar	| 255 | Yes	|
| STUDENT_ID	| nvarchar	| 255 | Yes	|
| STUDENT_LAST_NAME	| nvarchar	| 255 | Yes	|
| STUDENT_FIRST_NAME	| nvarchar	| 255 | Yes	|
| EMAIL_ADDRESS	| nvarchar	| 255 | Yes	|
| STREET_ADDRESS_PH_LINE1	| nvarchar	| 255 | Yes	|
| STREET_ADDRESS_PH_LINE2	| nvarchar	| 255 | Yes	|
| STREET_ADDRESS_PH_LINE3	| nvarchar	| 255 | Yes	|
| CITY_PH	| nvarchar	| 255 | Yes	|
| POSTCODE_PH	| nvarchar	| 255 | Yes	|
| NATION_DESCRIPTION_PH	| nvarchar	| 255 | Yes	|
| RESIDENCY_CODE	| nvarchar	| 255 | Yes	|
| RESIDENCY_DESC	| nvarchar	| 255 | Yes	|
| UCAS_COURSE_CODE	| nvarchar	| 255 | Yes	|
| PROGRAM_CODE	| nvarchar	| 255 | Yes	|
| DECISION_CODE	| nvarchar	| 255 | Yes	|
| APPLICANT_REPLY	| nvarchar	| 255 | Yes	|
| CONFIRMATION_DECISION	| nvarchar	| 255 | Yes	|
| APPLICANT_RESPONSE	| nvarchar	| 255 | Yes	|
| DECISION_STATUS	| nvarchar	| 255 | Yes	|
| YEAR_OF_ENTRY	| float	| | Yes	|
| DECEASED_INDICATOR	| nvarchar	| 255 | Yes	|
| INSTITUITION_CODE	| nvarchar	| 255 | Yes	|
| CWD_FLG	| nvarchar	| 255 | Yes	|
| BIRTH_DATE	| datetime	|| Yes	|
| CURRENT_AGE	| float	| | Yes	|
| BEEN_IN_CARE	| nvarchar	| 255 | Yes	|
| PARENTAL_EDUCATION	| nvarchar	| 255 | Yes	|

## MMI_Decisions$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FMMI_Decisions_.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|--------------|
| ID	| float	| Yes	| 	| 
| Student ID	| nvarchar	| 255 | Yes	| 	
| Applicant Name	| nvarchar	| 255 | Yes	| 	| 
| MMI Decision	| nvarchar	| 255 | Yes	| 	| 
| CourseFor	| nvarchar	| 255 | Yes	| 	| 
| pidm	| int	|| Yes	| set by importing script	| 

## MMI_Schedule$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FMMI_Schedule_.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|--------------|--------------|
| Student ID	| nvarchar	| 255 | Yes	|
| Firstname	| nvarchar	| 255 | Yes	|
| Surname	| nvarchar	| 255 | Yes	|
| Date	| datetime |	| Yes	|
| Time	| datetime |	| Yes	|
| Colour	| nvarchar	| 255 | Yes	|
| Number	| float |	| Yes	|

## Practique_finalscores$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FPractique_finalscores_.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|--------------|--------------|
| Student_ID	| nvarchar	| 255 | Yes	|
| Name	| nvarchar	| 255 | Yes	|
| LS_1stScorer	| float	| | Yes	|
| LS_2ndScorer	| nvarchar	| 255 | Yes	|
| LS_Final	| float	| | Yes	|
| MI_1stScore	| float	| | Yes	|
| MI_2ndScorer	| nvarchar	| 255 | Yes	|
| MI_Final	| float	| | Yes	|
| Ref_YesstScorer	| float	| | Yes	|
| Ref_2ndScorer	| nvarchar	| 255 | Yes	|
| Ref_Final	| float	| | Yes	|
| IA_1stScorer	| float	| | Yes	|
| IA_2ndScorer	| nvarchar	| 255 | Yes	|
| IA_Final	| float	| | Yes	|
| Admissions team total	| float	| | Yes	|
| MMI_Decision	| nvarchar	| 255 | Yes	|
| Academic staff total	| float	| | Yes	|
| Accept final total for personal statement or rescreen?	| nvarchar	| 255 | Yes	|
| Staff	| nvarchar	| 255 | Yes	|
| Second scorer	| nvarchar	| 255 | Yes	|
| Final checker	| nvarchar	| 255 | Yes	|
| Checked against UCAS list	| nvarchar	| 255 | Yes	|
| BMAT Overall score	| nvarchar	| 255 | Yes	|
| BMAT Overall Rank	| nvarchar	| 255 | Yes	|

## Reject_post_MMI$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FReject_post_MMI_.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|--------------|--------------|
| Candidate number	| nvarchar	| 255 | Yes	| 	| 	|
| Candidate Name	| nvarchar	| 255 | Yes	| 	| 	|
| Course	| nvarchar	| 255 | Yes	| 	| 	|
| Mean Task	| float	| | Yes	| 	| 	|
| Mean Task (+KAT)	| float	| | Yes	| 	| 	|
| Mean Global Score	| float	| | Yes	| 	| 	|
| Mean Rank (Task including KAT)	| float	| | Yes	| 	| 	|
| Mean Rank (Task, KAT and Global)	| float	| | Yes	| 	| 	|
| Mean Rank (Task- Not including KAT)	| float	| | Yes	| 	| 	|
| Rank (low score removed)	| float	| | Yes	| 	| 	|
| Rank (low scored removed- including KAT)	| float	| | Yes	| 	| 	|
| Station 1 Mean Percentile Rank	| float	| | Yes	| 	| 	|
| Station 2 Mean Percentile Rank	| float	| | Yes	| 	| 	|
| Station 3 Mean Percentile Rank	| float	| | Yes	| 	| 	|
| Station 4 Mean Percentile Rank	| float	| | Yes	| 	| 	|
| Station 5 Mean Percentile Rank	| float	| | Yes	| 	| 	|
| Station 6 Mean Percentile Rank	| float	| | Yes	| 	| 	|
| Station 7 Mean Percentile Rank	| float	| | Yes	| 	| 	|
| Station 8 Mean Percentile Rank	| float	| | Yes	| 	| 	|
| KAT Mean Percentile Rank	| float	| | Yes| | |

## ResultsSheet$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FResultsSheet_.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|--------------|--------------|
| Selector Centre	| nvarchar	| 255 | Yes	| 	| 	|  |
| Faculty	| nvarchar	| 255 | Yes	| 		| 	|  |
| School	| nvarchar	| 255 | Yes	| 	| 	|  |
| Year	| nvarchar	| 255 | Yes	| 	| 	|  |
| Level	| nvarchar	| 255 | Yes	| 	| 	|  |
| Fee Code	| nvarchar	| 255 | Yes	| 	| 	|  |
| Surname	| nvarchar	| 255 | Yes	| 	| 	|  |
| First Name	| nvarchar	| 255 | Yes	| 	| 	|  |
| DoB	| datetime |	| Yes	| 	| 	|  |
| Student ID	| nvarchar	| 255 | Yes	| 	| 	|  |
| UCAS ID	| nvarchar	| 255 | Yes	| 	| 	|  |
| App Number	| nvarchar	| 255 | Yes	| 	| 	|  |
| Course	| nvarchar	| 255 | Yes	| 	| 	|  |
| Course Desc	| nvarchar	| 255 | Yes	| 	| 	|  |
| Dec Code	| nvarchar	| 255 | Yes	| 	| 	|  |
| App Reply	| nvarchar	| 255 | Yes	| 	| 	|  |
| Conf Dec	| nvarchar	| 255 | Yes	| 	| 	|  |
| Conf Rep	| nvarchar	| 255 | Yes	| 	| 	|  |
| Full Offer Text	| nvarchar	| 255 | Yes	| 	| 	|  |
| Condition Code	| nvarchar	| 255 | Yes	| 	| 	|  |
| App date	| datetime |	| Yes	| 	| 	|  |
| Age Yesst Oct	| nvarchar	| 255 | Yes	| 	| 	|  |
| Late App	| nvarchar	| 255 | Yes	| 	| 	|  |
| IELTS	| nvarchar	| 255 | Yes	| 	| 	|  |
| A2L	| nvarchar	| 255 | Yes	| 	| 	|  |
| RoP	| nvarchar	| 255 | Yes	| 	| 	|  |
| Full Results	| nvarchar	| 255 | Yes	| 	| 	|  |
| Decision	| nvarchar	| 255 | Yes	| 	| 	|  |
| Result Position	| nvarchar	| 255 | Yes	| 	| 	|  |
| Quality	| nvarchar	| 255 | Yes	| 	| 	|  |
| Notes	| nvarchar	| 255 | Yes	| 	| 	|  |
| Received as CCO	| nvarchar	| 255 | Yes	| 	| 	|  |
| Received from	| nvarchar	| 255 | Yes	| 	| 	|  |
| Old Course Code	| nvarchar	| 255 | Yes	| 	| 	|  |

## UCAS_Scores$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FUCAS_Scores_.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? |
|-----------|----------|--------------|--------------|
| STUDENT_LAST_NAME	| nvarchar	| 255 | Yes	| 	| 	|
| STUDENT_FIRST_NAME	| nvarchar	| 255 | Yes	| 	| 	|
| PERSONAL_ID	| float	| | Yes	| 	| 	|
| STUDENT_ID	| nvarchar	| 255 | Yes	| 	| 	|
| ETHNICITY_DESCRIPTION	| nvarchar	| 255 | Yes	| 	| 	|
| GENDER	| nvarchar	| 255 | Yes	| 	| 	|
| Life Experience and Social Awareness	| nvarchar	| 255 | Yes	| 	| 	|
| Motivation and Insight	| nvarchar	| 255 | Yes	| 	| 	|
| Reflective Skills	| nvarchar	| 255 | Yes	| 	| 	|
| Interests and Achievements	| nvarchar	| 255 | Yes	| 	| 	|
| GLOBAL	| nvarchar	| 255 | Yes	| 	| 	|
| Overall Score (minus Global)	| nvarchar	| 255 | Yes	| 	| 	|
| F13	| nvarchar	| 255 | Yes	| 	| 	|