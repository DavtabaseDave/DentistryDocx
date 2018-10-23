# Stored Procedures

These can be divided into three categories:
- Housekeeping - day to day and periodic management of data
- UI SProcs
- Reporting SProcs 

## Housekeeping

The SProc:: pr_Dntl_Clear_Prev, pr_Dntl_Archive_Applicants , and pr_Clear_Current_Applicants are all used once a year, when rolling over the DB to a new year of applicants to:
1. Delete the previous year's applicant data
0. Archive the last lot of applicant data
0. Clear out the 