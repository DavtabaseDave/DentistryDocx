# Holding Tables

[[_TOC_]]

These table are *NOT* standard user visible, they are for administrative use only. They are intended for importing data from XLSX files before being transformed into user visible tables. Unlike normal tables they don't have Primary Keys as the data is not guaranteed to be in any "normal" form. Also, as the importer program may include the odd blank row all the fields must be null-able :(

## Academic_Scores$


*ALL* of these columns must be present in the spreadsheet otherwise the import will fail

| Attribute | DataType | Allow Nulls? |
|-----------|----------|--------------|
| PIDM	| float	| Yes	|
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

## BMAT_Scores$

XLSX import table for BMAT Scores

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

XLSX import table for DHDT_RejFdbkLetter$

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

XLSX import table for IFY applicants

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

## MMI_Schedule$

|_.Attribute |_.DataType |_.Allow Nulls? |_.PKey? |_.Notes |
| Student ID	| nvarchar	| Yes	| 	| 	|
| Firstname	| nvarchar	| Yes	| 	| 	|
| Surname	| nvarchar	| Yes	| 	| 	|
| Date	| datetime	| Yes	| 	| 	|
| Time	| datetime	| Yes	| 	| 	|
| Colour	| nvarchar	| Yes	| 	| 	|
| Number	| float	| Yes	| 	| 	|

## Reject_post_MMI$

|_.Attribute |_.DataType |_.Allow Nulls? |_.PKey? |_.Notes |
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

## UCAS_Scores$

|_.Attribute |_.DataType |_.Allow Nulls? |_.PKey? |_.Notes |
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