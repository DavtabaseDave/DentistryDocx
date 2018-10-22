# Functions

[[_TOC_]]

## fnGetCurTermCode()

This returns the current TermCode from the l_Current_Year_Dates table. Used mainly by
SProc pr_Dntl_Remove_Exceptions to remove previous year's non-UF applications from
Banner extraction. Also used by the Numbers views to build a set of course codes 
mapped to current entry year and a year either side
