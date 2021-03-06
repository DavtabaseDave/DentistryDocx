- In order to prevent have to update the entire package at the start of each new academic year
Project Level parameters **MUST** be used so that they can easily be altered
- At the same time should prefer Project parameters to Package variables as these can sometimes
 be ineffective due to accidental name collisions etc..
- As there is a slight chance that another Faculty will want a similar DB and variables and other
names object should clearly indicate by a prefix (*"Dent"*) that they are Faculty specific
- Data being imported from Banner should not "lose" any local data that is part of the same record.
Consequently "holding" table (with a prefix of "h_") should be used as a temporary store for incoming
data before it is merged with that actual user tables.
- To prevent any duplication/confusion, these holding tables should be cleared before the import 
of data from Banner.
- To prevent problems at the merging stage, the Banner queries should include descriptions as well
as codes where the description resides in a lookup table. This applies to such tuples as programme
codes/descriptions, ethnicity code and description. The code that merges the extracted raw data
should first append any missing lookup codes/descriptions so that the merge of the applicant
data will not fail due to missing foreign keys values.
- The Data Flow tasks should extract data for the following DB tables:
  - Applicants - correctly extract applicant's Banner data to append new/update existing data in
the table t_Dent_Applicants (shown [here](https://universityofleeds.visualstudio.com/FAD/_wiki/wikis/FAD.wiki?wikiVersion=GBwikiMaster&pagePath=%2FIntro%2FData%20Dictionary%2FData%20Tables)). Columns are included to insert missing rows into
the lookup tables for disability and school codes (l_stvdisa and l_stvsbgi)
  - Applicant's Decisions - correctly extract applicant's Decisions Banner data to append new
and/or update existing data in the table t_Dent_Decisions (shown [here](https://universityofleeds.visualstudio.com/FAD/_wiki/wikis/FAD.wiki?wikiVersion=GBwikiMaster&pagePath=%2FIntro%2FData%20Dictionary%2FData%20Tables&anchor=decisions)). A column is included
to insert missing rows into the lookup table for programme codes (l_smrprle)
  - Access to Leeds Running Record (A2L_RR) - correctly extract applicant's A2L_RR data from
Banner to append new/update existing data in the table t_Dent_A2L_RR (shown [here](https://universityofleeds.visualstudio.com/FAD/_wiki/wikis/FAD.wiki?wikiVersion=GBwikiMaster&pagePath=%2FIntro%2FData%20Dictionary%2FData%20Tables&anchor=a2l_rr)). 
  - GURMAIL offer codes - these are extracted as the possibility exists that in future Banner
codes will be written to GURMAIL when offer letters are sent out. This is used to update 
columns `date_off_let_sent` and `gurmail_code` in the Decisions table.
  - Applicant's Results - correctly extract applicant's Results Banner data to update existing
column `ACTUAL_RESULTS` in the table t_Dent_Applicants  
  - Nationalities list- extract the full list of nationality codes and descriptions from Banner
table `Skvssdt`
  - Ethnicity list - extract all ethnicity codes and descriptions from Banner table `stvethn`
- Merge the extracted Banner with the actual user tables 
- To prevent and duplication/confusion, these holding tables should be cleared after the import 
of data from Banner.
