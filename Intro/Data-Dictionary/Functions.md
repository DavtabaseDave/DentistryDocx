# Functions

[[_TOC_]]

## fnGetCurTermCode()

This returns the current TermCode from the l_Current_Year_Dates table. Used mainly by
SProc pr_Dntl_Remove_Exceptions to remove previous year's non-UF applications from
Banner extraction. Also used by the Numbers views to build a set of course codes 
mapped to current entry year and a year either side. Source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FFunctions%2FfnGetCurTermCode.sql&version=GBmaster)

## fnGetSecInt()

This, based on the user's membership of role groups, returns an Integer that encodes their
role membership. This has been superseded by the SProc, pr_GetGroupMembership, which
does much the same things but returns comma separated role names. This function is kept
for historical purposes (!). Source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FFunctions%2FfnGetSecInt.sql&version=GBmaster)

## fnIsA2L()

For use in a computed column in the Applicants table, this returns 1 where the applicant has an A2L record, 0 otherwise. Source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FFunctions%2FfnIsA2L.sql&version=GBmaster)