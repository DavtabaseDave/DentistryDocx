# Stored Procedures

[[_TOC_]]

These can be divided into three categories:
- Housekeeping - day to day and periodic management of data
- UI SProcs
- Reporting SProcs 

## Housekeeping

### Year End SProcs

The SProcs: pr_Dntl_Clear_Prev, pr_Dntl_Archive_Applicants, and pr_Clear_Current_Applicants are all used once a year, when rolling over the DB to a new year of applicants to:
1. Delete the previous year's applicant data, source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FStored%20Procedures%2Fpr_Dntl_Clear_Prev.sql&version=GBmaster)
0. Archive the last lot of applicant data, source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FStored%20Procedures%2Fpr_Dntl_Archive_Applicants.sql&version=GBmaster)
0. Clear out the current applicants data in preparation for the next year's applicants, source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FStored%20Procedures%2Fpr_Clear_Current_Applicants.sql&version=GBmaster)

The other two housekeeping SProcs are used by the daily ETL from Banner by the SQL Server Integration Services (SSIS) package, Dntl_Ad_INB_Extractions.dtsx (which is run daily by SQL Agent).

### Merge Banner data from holding tables
The SProc pr_Dntl_INB_Extraction_Merges is called as part of its penultimate step to merge the raw data it has acquired from Banner in the holding tables (**NOT** the ones used for importing XSLX data) into the standard user tables.

#### pr_Dntl_Remove_Exceptions

An SProc that removes a variety of unwanted data such as the previous year's non-UF applicants and their decisions and generally corrects any faulty data that would otherwise cause the merges to fail

#### pr_Dntl_INB_Extraction_Merges

This as its first step calls pr_Dntl_Remove_Exceptions 