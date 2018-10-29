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

The imported table in SQL Server will take the name of the worksheet so something
succinct like `A2L_Passlist` would be best – the holding table is named `A2L_Passlist$`

### Script & Link

See [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD?path=%2FFAD%20Add%20A2L%20Pass%20List.sql&version=GBmaster)

1. Give user the option to clear out the `A2L_Passlist$`(for when they're NOT appending new passes
0. Remove any blank rows
0. Update the PIDM by [Banner ID]
0. Update the actual table t_Dntl_Decisions using Pidm and Course Code


