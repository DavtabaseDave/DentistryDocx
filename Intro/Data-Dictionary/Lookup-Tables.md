# Lookup Tables

When using the lookup tables in a query, they should be joined by the PK field to the referencing column in the data table. The description field (ends "_desc") should be used in your output or to check for a particular value in a "where" clause.

## l_Achieved_Grade

Populates the "Achieved Grade" menu on the Decisions tab
| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| achieved_code	| tinyint	|  | Yes |
| achieved_desc	| varchar	| |  |

## x_Documents

This holds the actual documents that can either be customized by the client program or used "as is"

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| fileID	| smallint	| 	| Yes	| 	|
| filename	| varchar	| 	| 	| 	|
| customize	| bit	| 	| 	| 	|
| thefile	| varbinary	| Yes	| 	| 	|

## l_course_email

This controls the generation of different acknowledgement emails 

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Ref Table |
|-----------|----------|--------------|-------|-------|-------|
| skvcrse_code	| char	| 	| Yes	| 	|  |
| skvcrse_desc	| varchar	| 	| 	| 	|  |
| fileID	| smallint	| 	| 	| Yes	| x_Documents |
| subject_line	| varchar	| 	| 	| 	|  |


## l_Current_Year_Dates

Holds the *current* termcode and term dates (*NOT* the term of entry). The former is used by the function fnGetCurTermCode to weed out previous year's decisions when extracting data from Banner

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| Active	| bit	| 	| Yes	| 	|
| term_code	| varchar	| 	| 	| 	|
| start_date	| datetime	| 	| 	| 	|
| end_date	| datetime	| 	| 	| 	|

## l_data_source

Denotes where the applicant data was derived from

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| data_source	| tinyint	| 	| Yes	| 	|
| data_desc	| varchar	| 	| 	| 	|


## l_International_Agent

Populates the "International Agent" menu in the status area 

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| agent_code	| tinyint	|  | Yes |  |
| agent_desc	| varchar	|  |  |  |

## l_Predicted_Grade

Populates the "Predicted Grade" menu on the Decisions tab

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| predicted_code	| tinyint	|  | Yes |  |
| predicted_desc	| varchar	| Yes |  |  |

## l_Reason_Rej

Populates the "Reason for Rejection" menu on the Decisions tab

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| rej_code	| tinyint	|  | Yes |  |
| Reason	| varchar	| Yes |  |  |

## l_smrprle

Lists programme descriptions by Banner codes, e.g. "BA-ECON"

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | 
|-----------|----------|--------------|-------|-------|
| smrprle_program	| varchar	|  | Yes | Prog Code |
| smrprle_program_desc	| varchar	|  |  | Programme |

## l_stvdisa

List Disability by Banner code

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | 
|-----------|----------|--------------|-------|-------|
| stvdisa_code| varchar	|  | Yes | Banner code |
| stvdisa_desc| varchar	|  |  | Disability |

## l_stvethn

List Ethnicity by Banner code

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| stvethn_code| varchar	|  | Yes | Banner code |
| stvethn_desc| varchar	|  |  | Ethnicity|

## l_stvnatn

List nations by Banner code

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| skvssdt_sdat_code_opt_1	| varchar	|  | Yes | Banner code |
| skvssdt_short_title	| varchar	|  |  | Nation |

## l_Ad_stvsbgi

Lists Banner codes for the different schools

| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| stvsbgi_code	| int	|  | Yes | Banner Code |
| stvsbgi_desc	| varchar	| Yes |  | School name |
