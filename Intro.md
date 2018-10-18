# Data Tables

## t\_Dntl\_Applicants

The main applicants table containing Banner derived data and mutable
local data

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| spriden_pidm	| int	| 	| Yes	| 	|  |
| skrsain_applicant_no	| varchar	| 	| 	| 	|  |
| spriden_id	| varchar	| 	| 	| 	|  |
| skrsain_personalid	| varchar	| 	| 	| 	|  |
| spriden_last_name	| nvarchar	| 	| 	| 	|  |
| spriden_first_name	| nvarchar	| 	| 	| 	|  |
| spriden_mi	| nvarchar	| 	| 	| 	|  |
| student_initials	| nvarchar	| 	| 	| 	|  |
| spbpers_name_prefix	| nvarchar	| 	| 	| 	|  |
| spbpers_birth_date	| datetime	| 	| 	| 	|  |
| current_age	| tinyint	| 	| 	| 	|  |
| age_at_entry	| tinyint	| 	| 	| 	|  |
| spbpers_sex	| char	| 	| 	| 	|  |
| eth_code	| varchar	| 	| 	| Yes	| l_stvethn |
| sprmedi_disa_code	| varchar	| 	| 	| Yes	| l_stvdisa |
| skrsain_criminal_conv	| bit	| 	| 	| 	|  |
| skruccr_ssdt_code_home	| bit	| 	| 	| 	|  |
| STREET_ADDRESS_PH_LINE1	| nvarchar	| 	| 	| 	|  |
| STREET_ADDRESS_PH_LINE2	| nvarchar	| 	| 	| 	|  |
| STREET_ADDRESS_PH_LINE3	| nvarchar	| 	| 	| 	|  |
| spraddr_city	| nvarchar	| 	| 	| 	|  |
| nation_description_ph	| nvarchar	| 	| 	| 	|  |
| spraddr_zip	| nvarchar	| 	| 	| 	|  |
| telephone_number_ph	| nvarchar	| 	| 	| 	|  |
| skbspin_natn_code_legal	| varchar	| 	| 	| Yes	| l_stvnatn |
| saradap_resd_code	| char	| 	| 	| 	|  |
| skrsain_appl_date	| datetime	| 	| 	| 	|  |
| email_address	| varchar	| 	| 	| 	|  |
| skbuarf_predictedgrades	| varchar	| 	| 	| 	|  |
| sorhsch_sbgi_code	| int	| 	| 	| Yes	| l_stvsbgi |
| skrsain_ssdt_code_pared	| char	| 	| 	| 	|  |
| skrsain_care	| char	| 	| 	| 	|  |
| isActive	| bit	| 	| 	| 	|  |
| Query_Sent	| bit	| 	| 	| 	|  |
| Query_Deadline	| datetime	| Yes	| 	| 	|  |
| extension_deadline	| datetime	| Yes	| 	| 	|  |
| isExtension	| bit	| 	| 	| 	|  |
| Attending_Open_Day	| bit	| 	| 	| 	|  |
| Offer_Holder_Visit_Date	| datetime	| Yes	| 	| 	|  |
| Attended_Pre_Offer_Day	| bit	| 	| 	| 	|  |
| Attended_Offer_Holder_Day	| bit	| 	| 	| 	|  |
| Attended_Offer_Holder_Visit_Date	| datetime	| Yes	| 	| 	|  |
| Notes	| varchar	| 	| 	| 	|  |
| Form_Received	| bit	| 	| 	| 	|  |
| Email_Ack	| bit	| 	| 	| 	|  |
| Entry_Req	| bit	| 	| 	| 	|  |
| A2L	| bit	| 	| 	| 	|  |
| International_agent	| tinyint	| 	| 	| Yes	| l_International_Agent |
| isSports	| bit	| 	| 	| 	|  |
| isDisability	| bit	| 	| 	| 	|  |
| isFeesAssess	| bit	| 	| 	| 	|  |
| isMature	| bit	| 	| 	| 	|  |
| underYes8	| bit	| 	| 	| 	|  |
| hasDeferred	| bit	| 	| 	| 	|  |
| data_source	| tinyint	| 	| 	| Yes	| l_data_source |
| VS	| timestamp	| 	| 	| 	|  |
| CreatedDate	| smalldatetime	| 	| 	| 	|  |
| LastUser	| varchar	| 	| 	| 	|  |


## Decisions

Contains mostly Banner derived decision data plus some local management data

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
