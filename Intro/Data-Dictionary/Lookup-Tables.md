[[_TOC_]]

When using the lookup tables in a query, they should be joined by the PK field to the referencing column in the data table. The description field (ends "_desc") should be used in your output or to check for a particular value in a "where" clause.

## l_Achieved_Grade

Populates the "Achieved Grade" menu on the Decisions tab. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_Achieved_Grade.sql&version=GBmaster)
| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| achieved_code	| tinyint	| |  | Yes |
| achieved_desc	| varchar	| 75| |  |

## x_Documents

This holds the actual documents that can either be customized by the client program or used "as is". Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fx_Documents.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? | Ref Table |
|-----------|----------|--------------|--------------|-------|-------|
| fileID	| smallint	| |	| Yes	| 	|
| filename	| varchar	| 127 |	| 	| 	|
| customize	| bit	| |	| 	| 	|
| thefile	| varbinary	| |Yes	| 	| binary representation of<br /> the file in text	|
| Last Modified	| datetime	| | | |

## l_course_email

This controls the generation of different acknowledgement emails. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%l_course_email.sql&version=GBmaster)

NB: the FK to the entry in x_Documents means that the entry must be present in that table before adding an equivalent here and that a row can't be deleted from x_Documents without 
removing the corresponding one here first.

| Attribute | DataType | Data Length | Allow Nulls? | PKey? | FKey? | Ref Table |
|-----------|----------|--------------|--------------|-------|-------|-------|
| skvcrse_code	| char	| 4| 	| Yes	| 	|  |
| skvcrse_desc	| varchar	| 30| 	| 	| 	|  |
| fileID	| smallint	| | 	| 	| Yes	| x_Documents |
| subject_line	| varchar	| 100| 	| 	| 	|  |
| from_email	| varchar	| 60 | | | 


## l_Current_Year_Dates

Holds the *current* termcode and term dates (*NOT* the term of entry). The former is used by the function fnGetCurTermCode to weed out previous year's decisions when extracting data from Banner. May contain only two rows, only one of which can be "active". Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_Current_Year_Dates.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| Active	| bit	| |	| Yes	| 	|
| term_code	| varchar	| 6 |	| 	| 	|
| start_date	| datetime	| |	| 	| 	|
| end_date	| datetime	| |	| 	| 	|

## l_data_source

Denotes where the applicant data was derived from. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_data_source.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| data_source	| tinyint	| |	| Yes	| 	|
| data_desc	| varchar	| 75| 	| 	| 	|

## l_Dntl_Exceptions

This permits the exclusion of applicants from the import from Banner by PIDM. Typically this is only applicants who've
ticked the live at home box and at college thus duplicating their record so that the merge fails. The statement at line 56
(near end of SProc) deletes the live at home dupe [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FStored%20Procedures%2Fpr_Dntl_Remove_Exceptions.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? | FKey? | Ref Table |
|-----------|----------|--------------|--------------|-------|-------|-------|
| SPRIDEN_PIDM	| int	| 	| 	| Yes	| 	| not specifically specified as used to exclude from ETL |
| Reason	| varchar	| 10	| 	| 	| 	|  |

## l_International_Agent

Populates the "International Agent" menu in the status area. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_International_Agent.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| agent_code	| tinyint	| | | Yes |  |
| agent_desc	| varchar	| 20 | |  |  |

## l_MMI_Decision

Populates the MMI Decision menu against the applicant's decision. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_MMI_Decision.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| MMI_dec_code	| tinyint	| |	| Yes	|
| MMI_dec_desc	| varchar	| 35 |	| 	| 

## l_Predicted_Grade

Populates the "Predicted Grade" menu on the Decisions tab. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_Predicted_Grade.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| predicted_code	| tinyint	| |  | Yes |
| predicted_desc	| varchar	| 75 | Yes |  |

## l_Quartile_Rank

Holds common text for repeating fields in MMI common rankings. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_Quartile_Rank.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| rank_code	| tinyint	| |	| Yes	|
| rank_desc	| varchar	| 30 | 	| 	|

## l_Reason_Rej

Populates the "Reason for Rejection" menu on the Decisions tab. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_Reason_Rej.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| rej_code	| tinyint	| | | Yes |  |
| Reason	| varchar	| 75| |  |  |

## l_smrprle

Lists programme descriptions by Banner codes, e.g. "BA-ECON". Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_smrprle.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? |
|-----------|----------|--------------|--------------|-------|
| smrprle_program	| varchar	| 12 | | Yes | Prog Code |
| smrprle_program_desc	| varchar	| 150 |  |  | Programme |

## l_stvdisa

List Disability by Banner code. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_stvdisa.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | 
|-----------|----------|--------------|-------|-------|
| stvdisa_code| varchar	|  | Yes | Banner code |
| stvdisa_desc| varchar	|  |  | Disability |

## l_stvethn

List Ethnicity by Banner code. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_stvethn.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | 
|-----------|----------|--------------|-------|-------|
| stvethn_code| varchar	|  | Yes | Banner code |
| stvethn_desc| varchar	|  |  | Ethnicity|

## l_stvnatn

List nations by Banner code. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_stvnatn.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | 
|-----------|----------|--------------|-------|-------|
| skvssdt_sdat_code_opt_1	| varchar	|  | Yes | Banner code |
| skvssdt_short_title	| varchar	|  |  | Nation |

## l_stvsbgi

Lists Banner codes for the different schools. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Fl_stvsbgi.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | 
|-----------|----------|--------------|-------|-------|
| stvsbgi_code	| int	|  | Yes | Banner Code |
| stvsbgi_desc	| varchar	| Yes |  | School name |
