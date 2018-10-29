[[_TOC_]]

# SSIS Import Holding Tables

## h_Applicants

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| SPRIDEN_PIDM	| numeric	| 	| 
| SARADAP_TERM_CODE_ENTRY	| nvarchar	| 	| 
| SKRSAIN_APPLICANT_NO	| nvarchar	| 	| 
| SPRIDEN_ID	| nvarchar	| 	| 
| SARADAP_APPL_NO	| numeric	| 	| 
| SKRSAIN_PERSONALID	| nvarchar	| Yes	|
| SPRIDEN_LAST_NAME	| nvarchar	| 	| 
| SPRIDEN_FIRST_NAME	| nvarchar	| Yes	| 
| SPRIDEN_MI	| nvarchar	| Yes	|
| STUDENT_INITIALS	| nvarchar	| Yes	|
| SPBPERS_NAME_PREFIX	| nvarchar	| Yes	|
| SPBPERS_BIRTH_DATE	| datetime2	| Yes	|
| CURRENT_AGE	| nvarchar	| Yes	|
| AGE_AT_ENTRY	| nvarchar	| Yes	|
| SPBPERS_SEX	| nvarchar	| Yes	|
| SPRMEDI_DISA_CODE	| nvarchar	| Yes	|
| SKRSAIN_CRIMINAL_CONV	| nvarchar	| Yes	|
| SKRUCCR_SSDT_CODE_HOME	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINE1	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINE2	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINE3	| nvarchar	| Yes	|
| SPRADDR_CITY	| nvarchar	| Yes	|
| SPRADDR_ZIP	| nvarchar	| Yes	|
| NATION_DESCRIPTION_PH	| nvarchar	| Yes	|
| TELEPHONE_NUMBER_PH	| nvarchar	| Yes	|
| SKBSPIN_NATN_CODE_LEGAL	| nvarchar	| Yes	|
| SARADAP_RESD_CODE	| nvarchar	| 	| 
| SKRSAIN_APPL_DATE	| datetime2	| Yes	|
| EMAIL_ADDRESS	| nvarchar	| Yes	|
| SKBUARF_PREDICTEDGRADES	| nvarchar	| Yes	|
| SKBUARF_ACTIVITY_DATE	| datetime2	| Yes	|
| SORHSCH_SBGI_CODE	| nvarchar	| Yes	|
| HIGH_SCHOOL_NAME	| nvarchar	| Yes	|
| ETH_CODE	| nvarchar	| Yes	|
| STVDISA_DESC	| nvarchar	| Yes	|
| SKRSAIN_SSDT_CODE_PARED	| nvarchar	| Yes	|
| skrsain_care	| nvarchar	| Yes	|

## h_Decisions

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| SKRUCCR_PIDM	| numeric	| 	| 
| SKRUCCR_APPLICANT_NO	| nvarchar	| 	| 
| SKRUCCR_CHOICE_TYPE_NO	| nvarchar	| 	| 
| SKRUCCR_SSDT_CODE_CRSE	| nvarchar	| Yes	|
| PROGRAM_CODE	| nvarchar	| Yes	|
| PROGRAM_DESC	| nvarchar	| Yes	|
| SKRSAIN_SSDT_CODE_CWD_FLG	| nvarchar	| Yes	|
| SKRUCCR_SSDT_CODE_DECN	| nvarchar	| Yes	|
| SKRUCCR_DECISION_DATE	| datetime2	| Yes	|
| SKRUDEC_TRANS_STATUS	| nvarchar	| Yes	|
| SKRUCCR_SSDT_CODE_REPLY	| nvarchar	| Yes	|
| SKRUCCR_SSDT_CODE_CF_DECN	| nvarchar	| Yes	|
| SKRUCCR_SSDT_CODE_AP_RESP	| nvarchar	| Yes	|
| SKRUCCR_PROP_ENTRY_YR	| numeric	| Yes	|
| SKRUCCR_PROP_ENTRY_MTH	| numeric	| Yes	|
| SKRUCCR_CONDITIONS	| nvarchar	| Yes	|
| SKRUCCR_SSDT_CODE_ENTRY	| nvarchar	| Yes	|
| isDeferred	| bit	| Yes	|
## h_A2L_RR

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| sarchrt_pidm	| int	| 	| 
| spriden_id	| nvarchar	| 	| 
| skrsain_personalid	| nvarchar	| 	| 
| spriden_first_name	| nvarchar	| 	| 
| spriden_last_name	| nvarchar	| 	| 
| skruccr_ssdt_code_crse	| nvarchar	| 	| 
| Programme	| nvarchar	| 	| 
| A2L_Eligibility_Decision	| nvarchar	| 	| 
| saradap_term_code_entry	| nvarchar	| 	| 
| Number_Courses_Applied_For	| tinyint	| 	| 
| A2L_Route	| nvarchar	| 	| 
| A2L_Application_Received	| datetime	| Yes	| 
| A2L_Decision_Date	| datetime	| Yes	| 

## h_Offers

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|

## h_Results

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|

## h_stvethn

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|

## h_stvnatn

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|

# XSLX Import Holding Tables

These table are *NOT* standard user visible, they are for administrative use only. They are intended for importing data from XLSX files before being transformed into user visible tables. Unlike normal tables they don't have Primary Keys as the data is not guaranteed to be in any "normal" form. Also, as the importer program may include the odd blank row all the fields must be null-able :(

## A2L_Passlist$

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FA2L_Passlist_.sql&version=GBmaster)
*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|
| First Name	| nvarchar	| Yes	|
| Surname	| nvarchar	| Yes	|
| UCAS ID	| float	| Yes	|
| Banner ID	| nvarchar	| Yes	|
| Route	| float	| Yes	|
| Course Code	| nvarchar	| Yes	|
| Programme	| nvarchar	| Yes	|
| Offer status	| nvarchar	| Yes	|
| Study Skills Pass	| nvarchar	| Yes	|
| Subject Mark	| nvarchar	| Yes	|
| A2L Pass	| nvarchar	| Yes	|
| pidm	| int	| Yes	| set by import routine |

## Academic_Scores$

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FAcademic_Scores_.sql&version=GBmaster)
*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|
| PIDM	| float	| Yes	| set by import routine |
| Scorer initials	| nvarchar	| Yes	|
| Standard entry - GCSE English	| nvarchar	| Yes	|
| Standard entry - GCSE Maths	| nvarchar	| Yes	|
| Standard entry - GCSE Biology or Science	| nvarchar	| Yes	|
| Standard entry - GCSE Chemistry or Science	| nvarchar	| Yes	|
| Standard entry - GCSE other 1	| nvarchar	| Yes	|
| Standard entry - GCSE other 2	| nvarchar	| Yes	|
| Standard entry - GCSE other 3	| nvarchar	| Yes	|
| Standard entry - GCSE other 4	| nvarchar	| Yes	|
| Standard entry - GCSE other 5	| nvarchar	| Yes	|
| Standard entry - A2	| float	| Yes	|
| Graduate English GCSE	| nvarchar	| Yes	|
| Graduate Maths GCSE	| nvarchar	| Yes	|
| Graduate Biology GCSE	| nvarchar	| Yes	|
| Graduate Chemistry GCSE	| nvarchar	| Yes	|
| Graduate GCSE any 1	| nvarchar	| Yes	|
| Graduate GCSE Any 2	| nvarchar	| Yes	|
| Graduate GCSE total	| nvarchar	| Yes	|
| Graduate - Degree name	| nvarchar	| Yes	|
| Graduate - Degree classification Degree	| nvarchar	| Yes	|
| total GCSE	| float	| Yes	|
| Reference statement?	| nvarchar	| Yes	|
| Notes	| nvarchar	| Yes	|
| Total	| float	| Yes	|

## All MMI Rankings$

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FAll_MMI_Rankings_.sql&version=GBmaster)

*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| Candidate_number	| nvarchar	| Yes	|
| Candidate_Name	| nvarchar	| Yes	|
| Course	| nvarchar	| Yes	|
| Cohort_Ranked_In	| nvarchar	| Yes	|
| Mean_Task	| float	| Yes	|
| Mean_Rank_Task	| float	| Yes	|
| Offer_Cutoff	| float	| Yes	|
| Mean_Task_Low_score_removed	| float	| Yes	|
| Rank_Task_low_score_removed	| float	| Yes	|
| Rank_Difference	| float	| Yes	|
| Station_Yes_Mean_Percentile_Rank	| float	| Yes	|
| Station_Yes_Quartile_Rank	| nvarchar	| Yes	|
| Station_2_Mean_Percentile_Rank	| float	| Yes	|
| Station_2_Quartile_Rank	| nvarchar	| Yes	|
| Station_3_Mean_Percentile_Rank	| float	| Yes	|
| Station_3_Quartile_Rank	| nvarchar	| Yes	|
| Station_4_Mean_Percentile_Rank	| float	| Yes	|
| Station_4_Quartile_Rank	| nvarchar	| Yes	|
| Station_5_Mean_Percentile_Rank	| float	| Yes	|
| Station_5_Quartile_Rank	| nvarchar	| Yes	|
| Station_6_Mean_Percentile_Rank	| float	| Yes	|
| Station_6_Quartile_Rank	| nvarchar	| Yes	|
| Station_7_Mean_Percentile_Rank	| float	| Yes	|
| Station_7_Quartile_Rank	| nvarchar	| Yes	|
| Station_8_Mean_Percentile_Rank	| float	| Yes	|
| Station_8_Quartile_Rank	| nvarchar	| Yes	|

## BMAT_Scores$

XLSX import table for BMAT Scores. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FBMAT_Scores_.sql&version=GBmaster)

*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| Centre Number	| nvarchar	| Yes	|
| Centre Name	| nvarchar	| Yes	|
| CandidateID	| float	| Yes	|
| BannerID	| nvarchar	| Yes	|
| Forenames	| nvarchar	| Yes	|
| Surname	| nvarchar	| Yes	|
| Test	| nvarchar	| Yes	|
| Date of Birth	| datetime	| Yes	|
| Gender	| nvarchar	| Yes	|
| Special Considerations	| nvarchar	| Yes	|
| Section Yes Score	| float	| Yes	|
| Section 2 Score	| float	| Yes	|
| Essay Answered	| nvarchar	| Yes	|
| Section 3 Content	| float	| Yes	|
| Section 3 English	| nvarchar	| Yes	|
| Section 3 English Score	| float	| Yes	|
| Overall Score	| float	| Yes	|
| Overall Rank	| float	| Yes	|
| Absent Flag	| nvarchar	| Yes	|
| UCASID	| float	| Yes	|
| Institution	| nvarchar	| Yes	|
| Course Code	| nvarchar	| Yes	|
| Time Zone	| float	| Yes	|
| OptionalID	| nvarchar	| Yes	|

## DHDT_RejFdbkLetter$

XLSX import table for DHDT_RejFdbkLetter$. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FDHDT_RejFdbkLetter_.sql&version=GBmaster)

*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| PERSONAL_ID	| nvarchar	| Yes	|
| STUDENT_ID	| nvarchar	| Yes	|
| STUDENT_FIRST_NAME	| nvarchar	| Yes	|
| STUDENT_LAST_NAME	| nvarchar	| Yes	|
| EMAIL_ADDRESS	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINEYes	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINE2	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINE3	| nvarchar	| Yes	|
| CITY_PH	| nvarchar	| Yes	|
| POSTCODE_PH	| nvarchar	| Yes	|
| NATION_DESCRIPTION_PH	| nvarchar	| Yes	|
| Life Experience and Social Awareness:	| nvarchar	| Yes	|
| Motivation And Insight	| nvarchar	| Yes	|
| Reflective Skills	| nvarchar	| Yes	|
| Interests and Achievements	| nvarchar	| Yes	|

## IFY$

XLSX import table for IFY applicants..  Also used for importing ISFY and PHE applicants Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FIFY_.sql&version=GBmaster)

*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| PIDM_KEY	| float	| Yes	|
| TERM_CODE_KEY	| float	| Yes	|
| SELECTOR_CENTRE_CODE	| nvarchar	| Yes	|
| LEVEL_CODE	| nvarchar	| Yes	|
| PERSONAL_ID	| nvarchar	| Yes	|
| SCHEME_CODE	| nvarchar	| Yes	|
| UCAS_ID_KEY	| nvarchar	| Yes	|
| STUDENT_ID	| nvarchar	| Yes	|
| STUDENT_LAST_NAME	| nvarchar	| Yes	|
| STUDENT_FIRST_NAME	| nvarchar	| Yes	|
| EMAIL_ADDRESS	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINE1	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINE2	| nvarchar	| Yes	|
| STREET_ADDRESS_PH_LINE3	| nvarchar	| Yes	|
| CITY_PH	| nvarchar	| Yes	|
| POSTCODE_PH	| nvarchar	| Yes	|
| NATION_DESCRIPTION_PH	| nvarchar	| Yes	|
| RESIDENCY_CODE	| nvarchar	| Yes	|
| RESIDENCY_DESC	| nvarchar	| Yes	|
| UCAS_COURSE_CODE	| nvarchar	| Yes	|
| PROGRAM_CODE	| nvarchar	| Yes	|
| DECISION_CODE	| nvarchar	| Yes	|
| APPLICANT_REPLY	| nvarchar	| Yes	|
| CONFIRMATION_DECISION	| nvarchar	| Yes	|
| APPLICANT_RESPONSE	| nvarchar	| Yes	|
| DECISION_STATUS	| nvarchar	| Yes	|
| YEAR_OF_ENTRY	| float	| Yes	|
| DECEASED_INDICATOR	| nvarchar	| Yes	|
| INSTITUITION_CODE	| nvarchar	| Yes	|
| CWD_FLG	| nvarchar	| Yes	|
| BIRTH_DATE	| datetime	| Yes	|
| CURRENT_AGE	| float	| Yes	|
| BEEN_IN_CARE	| nvarchar	| Yes	|
| PARENTAL_EDUCATION	| nvarchar	| Yes	|

## MMI_Decisions$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FMMI_Decisions_.sql&version=GBmaster)
| Attribute | DataType | Allow Nulls? | Notes |
|-----------|----------|--------------|--------------|
| ID	| float	| Yes	| 	| 
| Student ID	| nvarchar	| Yes	| 	
| Applicant Name	| nvarchar	| Yes	| 	| 
| MMI Decision	| nvarchar	| Yes	| 	| 
| CourseFor	| nvarchar	| Yes	| 	| 
| pidm	| int	| Yes	| set by importing script	| 

## MMI_Schedule$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FMMI_Schedule_.sql&version=GBmaster)
| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| Student ID	| nvarchar	| Yes	|
| Firstname	| nvarchar	| Yes	|
| Surname	| nvarchar	| Yes	|
| Date	| datetime	| Yes	|
| Time	| datetime	| Yes	|
| Colour	| nvarchar	| Yes	|
| Number	| float	| Yes	|

## Practique_finalscores$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FPractique_finalscores_.sql&version=GBmaster)
| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| ID	| float	| Yes	|
| Student_ID	| nvarchar	| Yes	|
| Name	| nvarchar	| Yes	|
| LS_1stScorer	| float	| Yes	|
| LS_2ndScorer	| nvarchar	| Yes	|
| LS_Final	| float	| Yes	|
| MI_1stScore	| float	| Yes	|
| MI_2ndScorer	| nvarchar	| Yes	|
| MI_Final	| float	| Yes	|
| Ref_YesstScorer	| float	| Yes	|
| Ref_2ndScorer	| nvarchar	| Yes	|
| Ref_Final	| float	| Yes	|
| IA_1stScorer	| float	| Yes	|
| IA_2ndScorer	| nvarchar	| Yes	|
| IA_Final	| float	| Yes	|
| Admissions team total	| float	| Yes	|
| MMI_Decision	| nvarchar	| Yes	|
| Academic staff total	| float	| Yes	|
| Accept final total for personal statement or rescreen?	| nvarchar	| Yes	|
| Staff	| nvarchar	| Yes	|
| Second scorer	| nvarchar	| Yes	|
| Final checker	| nvarchar	| Yes	|
| Checked against UCAS list	| nvarchar	| Yes	|
| BMAT Overall score	| nvarchar	| Yes	|
| BMAT Overall Rank	| nvarchar	| Yes	|

## Reject_post_MMI$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FReject_post_MMI_.sql&version=GBmaster)
| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| Candidate number	| nvarchar	| Yes	| 	| 	|
| Candidate Name	| nvarchar	| Yes	| 	| 	|
| Course	| nvarchar	| Yes	| 	| 	|
| Mean Task	| float	| Yes	| 	| 	|
| Mean Task (+KAT)	| float	| Yes	| 	| 	|
| Mean Global Score	| float	| Yes	| 	| 	|
| Mean Rank (Task including KAT)	| float	| Yes	| 	| 	|
| Mean Rank (Task, KAT and Global)	| float	| Yes	| 	| 	|
| Mean Rank (Task- Not including KAT)	| float	| Yes	| 	| 	|
| Rank (low score removed)	| float	| Yes	| 	| 	|
| Rank (low scored removed- including KAT)	| float	| Yes	| 	| 	|
| Station 1 Mean Percentile Rank	| float	| Yes	| 	| 	|
| Station 2 Mean Percentile Rank	| float	| Yes	| 	| 	|
| Station 3 Mean Percentile Rank	| float	| Yes	| 	| 	|
| Station 4 Mean Percentile Rank	| float	| Yes	| 	| 	|
| Station 5 Mean Percentile Rank	| float	| Yes	| 	| 	|
| Station 6 Mean Percentile Rank	| float	| Yes	| 	| 	|
| Station 7 Mean Percentile Rank	| float	| Yes	| 	| 	|
| Station 8 Mean Percentile Rank	| float	| Yes	| 	| 	|
| KAT Mean Percentile Rank	| float	| yes| | |

## ResultsSheet$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FResultsSheet_.sql&version=GBmaster)
| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| Selector Centre	| nvarchar	| Yes	| 	| 	|  |
| Faculty	| nvarchar	| Yes	| 		| 	|  |
| School	| nvarchar	| Yes	| 	| 	|  |
| Year	| nvarchar	| Yes	| 	| 	|  |
| Level	| nvarchar	| Yes	| 	| 	|  |
| Fee Code	| nvarchar	| Yes	| 	| 	|  |
| Surname	| nvarchar	| Yes	| 	| 	|  |
| First Name	| nvarchar	| Yes	| 	| 	|  |
| DoB	| datetime	| Yes	| 	| 	|  |
| Student ID	| nvarchar	| Yes	| 	| 	|  |
| UCAS ID	| nvarchar	| Yes	| 	| 	|  |
| App Number	| nvarchar	| Yes	| 	| 	|  |
| Course	| nvarchar	| Yes	| 	| 	|  |
| Course Desc	| nvarchar	| Yes	| 	| 	|  |
| Dec Code	| nvarchar	| Yes	| 	| 	|  |
| App Reply	| nvarchar	| Yes	| 	| 	|  |
| Conf Dec	| nvarchar	| Yes	| 	| 	|  |
| Conf Rep	| nvarchar	| Yes	| 	| 	|  |
| Full Offer Text	| nvarchar	| Yes	| 	| 	|  |
| Condition Code	| nvarchar	| Yes	| 	| 	|  |
| App date	| datetime	| Yes	| 	| 	|  |
| Age Yesst Oct	| nvarchar	| Yes	| 	| 	|  |
| Late App	| nvarchar	| Yes	| 	| 	|  |
| IELTS	| nvarchar	| Yes	| 	| 	|  |
| A2L	| nvarchar	| Yes	| 	| 	|  |
| RoP	| nvarchar	| Yes	| 	| 	|  |
| Full Results	| nvarchar	| Yes	| 	| 	|  |
| Decision	| nvarchar	| Yes	| 	| 	|  |
| Result Position	| nvarchar	| Yes	| 	| 	|  |
| Quality	| nvarchar	| Yes	| 	| 	|  |
| Notes	| nvarchar	| Yes	| 	| 	|  |
| Received as CCO	| nvarchar	| Yes	| 	| 	|  |
| Received from	| nvarchar	| Yes	| 	| 	|  |
| Old Course Code	| nvarchar	| Yes	| 	| 	|  |

## UCAS_Scores$
Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2FUCAS_Scores_.sql&version=GBmaster)
| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| STUDENT_LAST_NAME	| nvarchar	| Yes	| 	| 	|
| STUDENT_FIRST_NAME	| nvarchar	| Yes	| 	| 	|
| PERSONAL_ID	| float	| Yes	| 	| 	|
| STUDENT_ID	| nvarchar	| Yes	| 	| 	|
| ETHNICITY_DESCRIPTION	| nvarchar	| Yes	| 	| 	|
| GENDER	| nvarchar	| Yes	| 	| 	|
| Life Experience and Social Awareness	| nvarchar	| Yes	| 	| 	|
| Motivation and Insight	| nvarchar	| Yes	| 	| 	|
| Reflective Skills	| nvarchar	| Yes	| 	| 	|
| Interests and Achievements	| nvarchar	| Yes	| 	| 	|
| GLOBAL	| nvarchar	| Yes	| 	| 	|
| Overall Score (minus Global)	| nvarchar	| Yes	| 	| 	|
| F13	| nvarchar	| Yes	| 	| 	|