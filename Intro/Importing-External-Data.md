[[_TOC_]]

Along with the Full Design Spec of the application's UI user guides for importing data
for the different tables can be found [here](https://leeds365.sharepoint.com/teams/ITApplicationsSupport/UG%20Admissions%20Dentistry/Forms/AllItems.aspx). This requires appropriate access privileges
to the Application Support SharePoint site.

This page will roughly:
1. the spreadsheet columns naming, order and any format requirements.
0. details the steps involved for each and 
0. a link to the actual script.

The exact steps in running the Import/Export Wizard will **NOT** detailed here as they
are set out in detail in the User Guides available on the SharePoint site listed above.

## Vital Note
Using Find and replace (CTRL+H) in Excel, delete every parenthesis and square bracket
from the column names row. This mainly applied to A2L Pass List but the import won't work
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

1. Give user the option to clear out the `A2L_Passlist$`(for when they're NOT appending new passes
0. Remove any blank rows
0. Update the PIDM by [Banner ID]
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

1. Give user the option to clear out the `Academic_Scores$`(for when they're NOT appending new passes. 
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
0. Insert into the actual table t_Dntl_BMAT_Scores using Candidate_number.
This is done in two parts - for those who were not marked absent and those who were

## Importing