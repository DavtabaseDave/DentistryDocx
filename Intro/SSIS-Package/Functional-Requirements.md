# Functional Requirements

- In order to prevent have to update the entire package at the start of each new academic year
Project Level parameters **MUST** be used so that they can easily be altered
- As there is a slight chance that another Faculty will want a similar DB and variables and other
names object should clearly indicate by a prefix (*"Dent"*) that they are Faculty specific
- At the same time should prefer Project parameters to Package variables as these can sometimes
 be ineffective due to accidental name collisions etc..
- Data being imported from Banner should not "lose" any local data that is part of the same record.
Consequently "holding" table (with a prefix of "h_") should be used as a temporary store for incoming
data before it is merged with that actual user tables.
- To prevent and duplication/confusion, these holding tables should be cleared both before and after
the import of data from Banner.
- To prevent problems at the merging stage, the Banner queries should include descriptions as well
as codes where the description resides in a lookup table. This applies to such tuples as programme
codes/descriptions, ethnicity code and description. The code that merges the extracted raw data
should first append any missing lookup codes/descriptions so that the merge of the applicant
data will not fail due to missing foreign keys values.