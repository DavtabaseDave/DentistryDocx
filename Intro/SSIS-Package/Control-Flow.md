# Control Flow

[[_TOC_]]

Can best be depicted pictorially:
 ![Control_Flow.png](/.attachments/Control_Flow-58d77829-9354-4d02-b523-37a460f9f0af.png)
The green arrows represent order of execution flow on success of a previous step. Any
failures terminate the process

NB: all OLEDB targets use the connection manager `Target FAD.conmgr` and Banner sources `INB_PROD.LUBSTXFR.conmgr`

## Truncate Holding Tables, before & after

Both Execute SQL Tasks `EXECUTE` the DB niladic SProc `pr_Dntl_Truncate_HoldingTables` (code [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FStored%20Procedures%2Fpr_Dntl_Truncate_HoldingTables.sql&version=GBmaster)) using the following settings:
 ![Dentatl_admish_trunc_H_Table.PNG](/.attachments/Dentatl_admish_trunc_H_Table-648b7c5b-56a3-42a5-8806-2ad305fa1e42.PNG).

## Banner Extractions

This will be described in greater detail [here](/Intro/SSIS-Package/Logical-Data-Map)

## Merges

This Execute SQL Task runs the following SQL (other settings as above):
``` sql
-- begin TX
begin transaction Dental_Admish_DailyUpdate with MARK N'Daily update of Dental Admissions data';

------------------------------------------------------------
-- MERGE the data from the holding tables into the actual tables
------------------------------------------------------------
EXECUTE dbo.pr_Dntl_INB_Extraction_Merges

-- finally, commit it
commit transaction Dental_Admish_DailyUpdate;
```

As is self-evident this simply wraps a call to `dbo.pr_Dntl_INB_Extraction_Merges
` in a transaction. Source [here](https://universityofleeds.visualstudio.com/FAD/_wiki/wikis/FAD.wiki?wikiVersion=GBwikiMaster&pagePath=%2FIntro%2FData%20Dictionary%2FStored%20Procedures&anchor=pr_dntl_inb_extraction_merges)
