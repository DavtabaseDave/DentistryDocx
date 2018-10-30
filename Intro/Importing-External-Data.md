[[_TOC_]]

Along with the Full Design Spec of the application's UI user guides for importing data
for the different tables can be found [here](https://leeds365.sharepoint.com/teams/ITApplicationsSupport/UG%20Admissions%20Dentistry/Forms/AllItems.aspx). This requires appropriate access privileges
to the Application Support SharePoint site.

This page will roughly set out:
1. the spreadsheet columns naming, order and any format requirements.
0. details the steps involved for each and 
0. a link to the actual script.

The exact steps in running the Import/Export Wizard will **NOT** detailed here as they
are set out in detail in the User Guides available on the SharePoint site listed above.

## Vital Note
Using Find and replace (CTRL+H) in Excel, delete every parenthesis and square bracket
from the **column names row**. This mainly applies to A2L Pass List but the import won't work
if any of these are present in column names.

## Importing A2L Pass List

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [First Name]
0. [Surname]
0. [UCAS ID]
0. [Banner ID]
0. [Route]
0. [Course Code]
0. [Programme]
0. [Offer status]
0. [Study Skills Pass]
0. [Subject Mark]
0. [A2L Pass]

**First ensure that the BannerID column is formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `A2L_Passlist` would be best – the holding table is named `A2L_Passlist$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20A2L%20Pass%20List.sql&version=GBmaster)

1. Give user the option to clear out the `A2L_Passlist$`(for when they're NOT appending new passes)
0. Remove any blank rows
0. Update the PIDM column by [Banner ID]
0. Update the actual table t_Dntl_Decisions using Pidm and Course Code

## Importing Academic Scores

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [PIDM]
0. [DoB]
0. [Leeds Code]
0. [Scorer initials]
0. [Standard entry - GCSE English]
0. [Standard entry - GCSE Maths]
0. [Standard entry - GCSE Biology or Science]
0. [Standard entry - GCSE Chemistry or Science]
0. [Standard entry - GCSE other 1]
0. [Standard entry - GCSE other 2]
0. [Standard entry - GCSE other 3]
0. [Standard entry - GCSE other 4]
0. [Standard entry - GCSE other 5]
0. [Standard entry - A2]
0. [Graduate English GCSE]
0. [Graduate Maths GCSE]
0. [Graduate Biology GCSE]
0. [Graduate Chemistry GCSE]
0. [Graduate GCSE any 1]
0. [Graduate GCSE Any 2]
0. [Graduate GCSE total]
0. [Graduate - Degree name]
0. [Graduate - Degree classification Degree]
0. [total GCSE]
0. [Reference statement?]
0. [Notes]
0. [Total]

The imported table in SQL Server will take the name of the worksheet so something
succinct like `Academic_Scores` would be best – the holding table is named `Academic_Scores$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20Academic%20Scores.sql&version=GBmaster)

1. Give user the option to clear out the `Academic_Scores$`(for when they're NOT appending new scores). 
Also to clear out the User table
0. Update the actual table t_Dntl_Academic_Scores using Pidm 

## Importing ALL MMI Rankings

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [Candidate_number]
0. [Candidate_Name]
0. [Course]
0. [Cohort_Ranked_In]
0. [Mean_Task]
0. [Mean_Rank_Task]
0. [Offer_Cutoff]
0. [Mean_Task_Low_score_removed]
0. [Rank_Task_low_score_removed]
0. [Rank_Difference]
0. [Station_1_Mean_Percentile_Rank]
0. [Station_1_Quartile_Rank]
0. [Station_2_Mean_Percentile_Rank]
0. [Station_2_Quartile_Rank]
0. [Station_3_Mean_Percentile_Rank]
0. [Station_3_Quartile_Rank]
0. [Station_4_Mean_Percentile_Rank]
0. [Station_4_Quartile_Rank]
0. [Station_5_Mean_Percentile_Rank]
0. [Station_5_Quartile_Rank]
0. [Station_6_Mean_Percentile_Rank]
0. [Station_6_Quartile_Rank]
0. [Station_7_Mean_Percentile_Rank]
0. [Station_7_Quartile_Rank]
0. [Station_8_Mean_Percentile_Rank]
0. [Station_8_Quartile_Rank]

**VITAL: First ensure that the Candidate_number column is formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `All_MMI_Rankings` would be best – the holding table is named `All_MMI_Rankings$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20All%20MMI%20Rankings.sql&version=GBmaster)

1. Give user the option to clear out the `All_MMI_Rankings$`(for when they're NOT appending new passes. 
Also to clear out the User table
0. Update the actual table t_Dntl_All_MMI_Rankings using Candidate_number

## Importing BMAT Scores

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [Centre Number]
0. [Centre Name]
0. [CandidateID]
0. [BannerID]
0. [Forenames]
0. [Surname]
0. [Test]
0. [Date of Birth]
0. [Gender]
0. [Special Considerations]
0. [Section 1 Score]
0. [Section 2 Score]
0. [Essay Answered]
0. [Section 3 Content]
0. [Section 3 English]
0. [Section 3 English Score]
0. [Overall Score]
0. [Overall Rank]
0. [Absent Flag]
0. [UCASID]
0. [Institution]
0. [Course Code]
0. [Time Zone]
0. [OptionalID]

**First ensure that the BannerID column is formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `BMAT_Scores` would be best – the holding table is named `BMAT_Scores$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20BMAT%20Scores.sql&version=GBmaster)

1. Give user the option to clear out the `All_MMI_Rankings$`(for when they're NOT appending new passes. 
Also to clear out the User table
0. Insert into the actual table t_Dntl_BMAT_Scores using Candidate_number.
This is done in two parts - for those who were not marked absent and those who were

## Importing DHDT Reject with feedback

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [PERSONAL_ID]
0. [STUDENT_ID]
0. [STUDENT_FIRST_NAME]
0. [STUDENT_LAST_NAME]
0. [EMAIL_ADDRESS]
0. [STREET_ADDRESS_PH_LINE1]
0. [STREET_ADDRESS_PH_LINE2]
0. [STREET_ADDRESS_PH_LINE3]
0. [CITY_PH]
0. [POSTCODE_PH]
0. [NATION_DESCRIPTION_PH]
0. [Life Experience and Social Awareness:]
0. [Motivation And Insight]
0. [Reflective Skills]
0. [Interests and Achievements]

**First ensure that the STUDENT_ID column is formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `DHDT_RejFdbkLetter` would be best – the holding table is named `DHDT_RejFdbkLetter$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20DHDT_RejFdbk.sql&version=GBmaster)

1. Give user the option to clear out the `DHDT_RejFdbkLetter$`(for when they're NOT appending new passes. 
0. Insert into the actual table t_Dntl_RejFdbkLetter using STUDENT_ID_number.

## Importing IFY, ISPY, & PHE Applicants

This is slightly different to the others in that this provides a route for importing non-UCAS
Applicants and their decisions. The same import table, `IFY$` is used to import the different
types of non-UCAS applicants. 


### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [PIDM_KEY]
0. [TERM_CODE_KEY]
0. [SELECTOR_CENTRE_CODE]
0. [LEVEL_CODE]
0. [PERSONAL_ID]
0. [SCHEME_CODE]
0. [UCAS_ID_KEY]
0. [STUDENT_ID]
0. [STUDENT_LAST_NAME]
0. [STUDENT_FIRST_NAME]
0. [EMAIL_ADDRESS]
0. [STREET_ADDRESS_PH_LINE1]
0. [STREET_ADDRESS_PH_LINE2]
0. [STREET_ADDRESS_PH_LINE3]
0. [CITY_PH]
0. [POSTCODE_PH]
0. [NATION_DESCRIPTION_PH]
0. [RESIDENCY_CODE]
0. [RESIDENCY_DESC]
0. [UCAS_COURSE_CODE]
0. [PROGRAM_CODE]
0. [DECISION_CODE]
0. [APPLICANT_REPLY]
0. [CONFIRMATION_DECISION]
0. [APPLICANT_RESPONSE]
0. [DECISION_STATUS]
0. [YEAR_OF_ENTRY]
0. [DECEASED_INDICATOR]
0. [INSTITUITION_CODE]
0. [CWD_FLG]
0. [GENDER]
0. [BIRTH_DATE]
0. [CURRENT_AGE]
0. [BEEN_IN_CARE]
0. [PARENTAL_EDUCATION]

**First ensure that the STUDENT_ID, UCAS_ID_KEY, and PERSONAL_ID columns are formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `IFY` would be best – the holding table is named `IFY$`

The user must supply their own PIDM for these applicants. These can begin at 1 

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20IFYs%20from%20IFY%24.sql&version=GBmaster)

1. Give user the option to clear out the `IFY$` (for when they're NOT appending). 
0. Insert applicants into the actual table t_Dntl_Applicants.
The uses can alter the data_source code to be 1, 2, or 3 (IFY, ISFY, and PHE respectively)
0. Insert their decisions into the actual table t_Dntl_Decisions

## Importing MMI Decisions

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [ID]
0. [Student ID]
0. [Applicant Name]
0. [MMI Decision]
0. [CourseFor]

**First ensure that the Student ID column is formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `MMI_Decisions` would be best – the holding table is named `MMI_Decisions$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20MMI%20Decisions.sql&version=GBmaster)

1. Give user the option to clear out the `MMI_Decisions$`(for when they're NOT appending new passes
0. Remove any blank rows
0. Update the PIDM by [Student ID]
0. Update the actual table t_Dntl_Decisions using Pidm and Course Code

## Importing MMI Schedule

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [Student ID]
0. [Firstname]
0. [Surname]
0. [Date]
0. [Time]
0. [Colour]
0. [Number]

**First ensure that the Student ID column is formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `MMI_Schedule` would be best – the holding table is named `MMI_Schedule$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20MMI%20Schedules.sql&version=GBmaster)

1. Give user the option to clear out the `MMI_Schedule$`(for when they're NOT appending new passes
0. Insert MMI Schedule rows into t_Dntl_MMI_Schedule by [Student ID]
0. Display any that are not matched

## Importing MMI Scores & Rankings (aka Reject_post_MMI)

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [Candidate number]
0. [Candidate Name]
0. [Course]
0. [Mean Task]
0. [Mean Task (+KAT)]
0. [Mean Global Score]
0. [Mean Rank (Task including KAT)]
0. [Mean Rank (Task, KAT and Global)]
0. [Mean Rank (Task- Not including KAT)]
0. [Rank (low score removed)]
0. [Rank (low scored removed- including KAT)]
0. [Station 1 Mean Percentile Rank]
0. [Station 2 Mean Percentile Rank]
0. [Station 3 Mean Percentile Rank]
0. [Station 4 Mean Percentile Rank]
0. [Station 5 Mean Percentile Rank]
0. [Station 6 Mean Percentile Rank]
0. [Station 7 Mean Percentile Rank]
0. [Station 8 Mean Percentile Rank]
0. [KAT Mean Percentile Rank]

**First ensure that the Candidate number column is formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `Reject_post_MMI` would be best – the holding table is named `Reject_post_MMI$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20MMI%20Scores%20%26%20Rankings.sql&version=GBmaster)

1. Give user the option to clear out the `Reject_post_MMI$` (for when they're NOT appending new data)
0. Insert MMI Schedule rows into t_Dntl_Reject_post_MMI by [Candidate number]
0. Display any that are not matched

## Importing Practique finalscores

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [ID]
0. [Student_ID]
0. [Name]
0. [LS_1stScorer]
0. [LS_2ndScorer]
0. [LS_Final]
0. [MI_1stScore]
0. [MI_2ndScorer]
0. [MI_Final]
0. [Ref_1stScorer]
0. [Ref_2ndScorer]
0. [Ref_Final]
0. [IA_1stScorer]
0. [IA_2ndScorer]
0. [IA_Final]
0. [Admissions team total]
0. [MMI_Decision] **VITAL: Change this from [Field16]**
0. [Academic staff total]
0. [Accept final total for personal statement or rescreen?]
0. [Staff] **VITAL: Change this from [Field19]**
0. [Second scorer]
0. [Final checker]
0. [Checked against UCAS list]
0. [BMAT Overall score]
0. [BMAT Overall Rank]

**First ensure that the Student ID column is formatted as text in Excel –
if not ensure that the whole column is formatted as text and resave the file before proceeding.**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `Practique_finalscores` would be best – the holding table is named `Practique_finalscores$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20Practique%20finalscores.sql&version=GBmaster)

1. Give user the option to clear out the `Practique_finalscores$` (for when they're NOT appending new passes).
Also to clear out the User table
0. Update the actual table t_Dntl_Practique_finalscores using Student_ID_number

## Importing Practique finalscores

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [Selector Centre]
0. [Faculty]
0. [School]
0. [Year]
0. [Level]
0. [Fee Code]
0. [Surname]
0. [First Name]
0. [DoB]
0. [Student ID]
0. [UCAS ID]
0. [App Number]
0. [Course]
0. [Course Desc]
0. [Dec Code]
0. [App Reply]
0. [Conf Dec]
0. [Conf Rep]
0. [Full Offer Text]
0. [Condition Code]
0. [App date]
0. [Age 1st Oct]
0. [Late App]
0. [IELTS]
0. [A2L]
0. [RoP]
0. [Full Results]
0. [Decision]
0. [Result Position]
0. [Quality]
0. [Notes]
0. [Received as CCO]
0. [Received from]
0. [Old Course Code]

#### Vital notes
Ignore at your peril
1. If the XLSX has been protected with a password, open it and copy and paste the data
& column headings into a new workbook as the import wizard cannot cope with a
protected XLSX. Name the worksheet `ResultsSheet`
0. Ensure the dates are formatted as dates and not text – the dates may occasionally lose
their formatting and appear a number of days elapsed since 1-JAN-70.
If this becomes a problem neither of the dates in this data are important so you can fill
with valid but meaningless dates
0. First ensure that the Student ID column is formatted as text in Excel – if not ensure that
the whole column is formatted as text and resave the file before proceeding
0. Ensure that the column names match those of the table [dbo].[ResultsSheet$] otherwise
you will be forced to match those by hand. For those that are missing that are non-essential
(such as candidate number) can simply be added as a heading alone.

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20Results%20Data%20Sheet.sql&version=GBmaster)

1. Give user the option to clear out the `ResultsSheet$` (for when they're NOT appending new data)
Also to clear out the User table
0. Insert ResultsSheet rows into t_Dntl_Results_Sheet by [Student ID], 12.[App Number], and 4.[Year]


## Importing UCAS Scores

### Format of XLSX and worksheet name
The columns should be named (and preferably appear in this order) (sans square brackets):
1. [STUDENT_LAST_NAME]
0. [STUDENT_FIRST_NAME]
0. [PERSONAL_ID]
0. [STUDENT_ID]
0. [ETHNICITY_DESCRIPTION]
0. [GENDER]
0. [Life Experience and Social Awareness]
0. [Motivation and Insight]
0. [Reflective Skills]
0. [Interests and Achievements]
0. [GLOBAL]
0. [Overall Score (minus Global)]
0. [F13]

**First ensure that the Student ID column is formatted as text in Excel – if not ensure that
the whole column is formatted as text and resave the file before proceeding**

The imported table in SQL Server will take the name of the worksheet so something
succinct like `UCAS_Scores` would be best – the holding table is named `UCAS_Scores$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20UCAS%20Scores.sql&version=GBmaster)

1. Give user the option to clear out the `UCAS_Scores$` (for when they're NOT appending new data)
Also to clear out the User table
0. Insert UCAS_Scores rows into t_Dntl_UCAS_Scores by [Student ID]

