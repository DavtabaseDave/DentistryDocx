[[_TOC_]]

**NB: all tables have the prefix t\_Dent\_, this has been removed from the heading as otherwise the ToC doesn't render properly**

## Applicants

The main applicants table containing Banner derived data and mutable
local data. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_Applicants.sql&version=GBmaster)

| Attribute | DataType | Data Length | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|--------------|-------|-------|-------|
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
| A2L	| bit	| 	| 	| 	| Computed column, see [here](/Intro/Data-Dictionary/Functions)  |
| International_agent	| tinyint	| 	| 	| Yes	| l_International_Agent |
| isSports	| bit	| 	| 	| 	|  |
| isDisability	| bit	| 	| 	| 	|  |
| isFeesAssess	| bit	| 	| 	| 	|  |
| isMature	| bit	| 	| 	| 	|  |
| under18	| bit	| 	| 	| 	|  |
| hasDeferred	| bit	| 	| 	| 	| updated by the Banner merge SProc |
| data_source	| tinyint	| 	| 	| Yes	| l_data_source, defaults to 0 (UCAS) |
| VS	| timestamp	| 	| 	| 	|  |
| CreatedDate	| smalldatetime	| 	| 	| 	| defaults to `getdate()` |
| LastUser	| varchar	| 	| 	| 	|  |

## Decisions

Contains mostly Banner derived decision data plus some local management data. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_Decisions.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| skruccr_pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| skruccr_choice_type_no	| varchar	| 	| Yes	| 	|  |
| skruccr_ssdt_code_crse	| varchar	| 	| 	| 	|  |
| DEGC_CODE	| varchar	| 	| 	| 	|  |
| skrutop_program	| varchar	| 	| 	| Yes	| l_smrprle |
| skruccr_ssdt_code_decn	| varchar	| 	| 	| 	|  |
| skruccr_decision_date	| datetime	| Yes	| 	| 	|  |
| skruccr_ssdt_code_reply	| varchar	| Yes	| 	| 	|  |
| skruccr_ssdt_code_cf_decn	| varchar	| Yes	| 	| 	|  |
| skruccr_ssdt_code_ap_resp	| varchar	| Yes	| 	| 	|  |
| skruccr_prop_entry_yr	| smallint	| 	| Yes	| 	|  |
| skruccr_prop_entry_mth	| smallint	| 	| 	| 	|  |
| skruccr_conditions	| varchar	| Yes	| 	| 	|  |
| skruccr_ssdt_code_entry	| varchar	| 	| 	| 	|  |
| date_off_let_sent	| datetime	| Yes	| 	| 	|  |
| gurmail_code	| varchar	| 	| 	| 	|  |
| predicted_grade	| tinyint	| 	| 	| Yes	| l_Predicted_Grade |
| achieved_grade	| tinyint	| 	| 	| Yes	| l_Achieved_Grade |
| reason_for_rejection	| tinyint	| 	| 	| Yes	| l_Reason_Rej |
| Reason_For_Rej_Notes	| varchar	| 	| 	| 	|  |
| VS	| timestamp	| 	| 	| 	|  |
| CreatedDate	| smalldatetime	| 	| 	| 	|  |
| LastUser	| varchar	| 	| 	| 	|  |

## A2L_RR

The only other Banner derived data - Access to Leeds Running Record. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_A2L_RR.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| sarchrt_pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| spriden_id	| varchar	| 	| 	| 	|  |
| skrsain_personalid	| varchar	| 	| 	| 	|  |
| spriden_first_name	| nvarchar	| 	| 	| 	|  |
| spriden_last_name	| nvarchar	| 	| 	| 	|  |
| skruccr_ssdt_code_crse	| varchar	| 	| Yes	| 	|  |
| Programme	| varchar	| 	| 	| 	|  |
| A2L_Eligibility_Decision	| varchar	| 	| 	| 	|  |
| saradap_term_code_entry	| varchar	| 	| 	| 	|  |
| Number_Courses_Applied_For	| tinyint	| 	| 	| 	|  |
| A2L_Route	| varchar	| 	| 	| 	|  |
| A2L_Application_Received	| datetime	| Yes	| 	| 	|  |
| A2L_Decision_Date	| datetime	| Yes	| 	| 	|  |

## Academic_Scores

Data imported for the different GCSE scores. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_Academic_Scores.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| PIDM	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| Scorer Name	| varchar	| 	| 	| 	|  |
| Leeds_Code	| char	| 	| 	| 	|  |
| Std_entry_GCSE_English	| varchar	| 	| 	| 	|  |
| Std_entry_GCSE_Maths	| varchar	| 	| 	| 	|  |
| Std_entry_GCSE_Biology_or_Science	| varchar	| 	| 	| 	|  |
| Std_entry_GCSE_Chemistry_or_Science	| varchar	| 	| 	| 	|  |
| Std_entry_GCSE_other_1	| varchar	| 	| 	| 	|  |
| Std_entry_GCSE_other_2	| varchar	| 	| 	| 	|  |
| Std_entry_GCSE_other_3	| varchar	| 	| 	| 	|  |
| Std_entry_GCSE_other_4	| varchar	| 	| 	| 	|  |
| Std_entry_GCSE_other_5	| varchar	| 	| 	| 	|  |
| Std_entry_A2	| tinyint	| 	| 	| 	|  |
| Grad_English_GCSE	| varchar	| 	| 	| 	|  |
| Grad_Maths_GCSE	| varchar	| 	| 	| 	|  |
| Grad_Biology_GCSE	| varchar	| 	| 	| 	|  |
| Grad_Chemistry_GCSE	| varchar	| 	| 	| 	|  |
| Grad_GCSE_Any_1	| varchar	| 	| 	| 	|  |
| Grad_GCSE_Any_2	| varchar	| 	| 	| 	|  |
| Grad_A_Level_Biology	| varchar	| 	| 	| 	|  |
| Grad_A_Level_Chemistry	| varchar	| 	| 	| 	|  |
| Grad_3rd_Subject	| varchar	| 	| 	| 	|  |
| Grad_Other_A_Level_1	| varchar	| 	| 	| 	|  |
| Grad_Other_A_Level_2	| varchar	| 	| 	| 	|  |
| Grad_Degree_Name	| varchar	| 	| 	| 	|  |
| Grad_Degree_Classification_Degree	| varchar	| 	| 	| 	|  |
| A2HE_DHDT_only	| varchar	| 	| 	| 	|  |
| Total	| tinyint	| 	| 	| 	|  |

## All_MMI_Rankings

Data imported for the different MMI rankings. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_All_MMI_Rankings.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| prog_code	| varchar	| 	| Yes	| 	|  |
| Mean_Rank_Task	| float	| 	| 	| 	|  |
| Offer_Cutoff	| float	| 	| 	| 	|  |
| Station_1_Mean_Percentile_Rank	| tinyint	| 	| 	| 	|  |
| Station_1_Quartile_Rank	| tinyint	| 	| 	| Yes	| l_Quartile_Rank |
| Station_2_Mean_Percentile_Rank	| tinyint	| 	| 	| 	|  |
| Station_2_Quartile_Rank	| tinyint	| 	| 	| Yes	| l_Quartile_Rank |
| Station_3_Mean_Percentile_Rank	| tinyint	| 	| 	| 	|  |
| Station_3_Quartile_Rank	| tinyint	| 	| 	| Yes	| l_Quartile_Rank |
| Station_4_Mean_Percentile_Rank	| tinyint	| 	| 	| 	|  |
| Station_4_Quartile_Rank	| tinyint	| 	| 	| Yes	| l_Quartile_Rank |
| Station_5_Mean_Percentile_Rank	| tinyint	| 	| 	| 	|  |
| Station_5_Quartile_Rank	| tinyint	| 	| 	| Yes	| l_Quartile_Rank |
| Station_6_Mean_Percentile_Rank	| tinyint	| 	| 	| 	|  |
| Station_6_Quartile_Rank	| tinyint	| 	| 	| Yes	| l_Quartile_Rank |
| Station_7_Mean_Percentile_Rank	| tinyint	| 	| 	| 	|  |
| Station_7_Quartile_Rank	| tinyint	| 	| 	| Yes	| l_Quartile_Rank |
| Station_8_Mean_Percentile_Rank	| tinyint	| 	| 	| 	|  |
| Station_8_Quartile_Rank	| tinyint	| 	| 	| Yes	| l_Quartile_Rank |

## BMAT_Scores

BMAT scores after being imported and matched with an applicant record. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_BMAT_Scores.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| 	Yes	| t_Dntl_Applicants |
| Section Yes Score	| float	| 	| 	| 	|  |
| Section 2 Score	| float	| 	| 	| 	|  |
| Essay Answered	| varchar	| 	| 	| 	|  |
| Section 3 Content	| float	| 	| 	| 	|  |
| Section 3 English	| varchar	| 	| 	| 	|  |
| Section 3 English Score	| float	| 	| 	| 	|  |
| Overall Rank	| float	| 	| 	| 	|  |

## Definitive_List_Prev

Instead of keeping separate tables for each of the previous year's applicant data that has been uploaded a single table has been put together to store all this data in one location. This aggregates the different scores etc and as a consequence many of the fields are null-able.

As the t_Dntl_All_MMI_Rankings table may contain multiple entries for an applicant that has applied for both courses a compromise had to be implemented that took only the "minimum" course code. This is to enable the t_Dntl_Definitive_List_Prev to be directly linked to the Previous Applicant and thus be able to be displayed properly in the .NET client application.

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_Definitive_List_Prev.sql&version=GBmaster)
| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| spriden_pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants_Prev |
| A2L_Eligibility_Decision	| varchar	| 	| 	| 	|  |
| A2L_Mark	| varchar	| 	| 	| 	|  |
| A2L_Pass	| varchar	| 	| 	| 	|  |
| hasBMAT	| varchar	| 	| 	| 	|  |
| LS_1stScorer	| tinyint	| Yes	| 	| 	|  |
| LS_2ndScorer	| tinyint	| Yes	| 	| 	|  |
| LS_Final	| tinyint	| Yes	| 	| 	|  |
| MI_1stScore	| tinyint	| Yes	| 	| 	|  |
| MI_2ndScorer	| tinyint	| Yes	| 	| 	|  |
| MI_Final	| tinyint	| Yes	| 	| 	|  |
| Ref_1stScorer	| tinyint	| Yes	| 	| 	|  |
| Ref_2ndScorer	| tinyint	| Yes	| 	| 	|  |
| Ref_Final	| tinyint	| Yes	| 	| 	|  |
| IA_1stScorer	| tinyint	| Yes	| 	| 	|  |
| IA_2ndScorer	| tinyint	| Yes	| 	| 	|  |
| IA_Final	| tinyint	| Yes	| 	| 	|  |
| Section 1 Score	| float	| Yes	| 	| 	|  |
| Section 2 Score	| float	| Yes	| 	| 	|  |
| Essay Answered	| varchar	| 	| 	| 	|  |
| Section 3 Content	| float	| Yes	| 	| 	|  |
| Section 3 English	| varchar	| 	| 	| 	|  |
| Section 3 English Score	| float	| Yes	| 	| 	|  |
| Overall Rank	| float	| Yes	| 	| 	|  |
| Mean_Rank_Task	| float	| Yes	| 	| 	|  |
| Offer_Cutoff	| float	| Yes	| 	| 	|  |
| Station_1_Mean_Percentile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_1_Quartile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_2_Mean_Percentile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_2_Quartile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_3_Mean_Percentile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_3_Quartile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_4_Mean_Percentile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_4_Quartile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_5_Mean_Percentile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_5_Quartile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_6_Mean_Percentile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_6_Quartile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_7_Mean_Percentile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_7_Quartile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_8_Mean_Percentile_Rank	| tinyint	| Yes	| 	| 	|  |
| Station_8_Quartile_Rank	| tinyint	| Yes	| 	| 	|  |
| MMI_Date	| datetime	| Yes	| 	| 	|  |
| MMI_Time	| time	| Yes	| 	| 	|  |
| MMI_Colour	| varchar	| Yes	| 	| 	|  |
| MMI_Number	| tinyint	| Yes	| 	| 	|  |
| Life_And_Social	| varchar	| Yes	| 	| 	|  |
| Motivation_And_Insight	| varchar	| Yes	| 	| 	|  |
| Reflective_Skills	| varchar	| Yes	| 	| 	|  |
| Interests_And_Achievements	| varchar	| Yes	| 	| 	|  |
| GLOBAL	| varchar	| Yes	| 	| 	|  |
| Overall_Score	| varchar	| Yes	| 	| 	|  |
| Scorer Name	| varchar	| Yes	| 	| 	|  |
| Leeds_Code	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_English	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_Maths	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_Biology_or_Science	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_Chemistry_or_Science	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_1	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_2	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_3	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_4	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_5	| varchar	| Yes	| 	| 	|  |
| Std_entry_A2	| tinyint	| Yes	| 	| 	|  |
| Grad_English_GCSE	| varchar	| Yes	| 	| 	|  |
| Grad_Maths_GCSE	| varchar	| Yes	| 	| 	|  |
| Grad_Biology_GCSE	| varchar	| Yes	| 	| 	|  |
| Grad_Chemistry_GCSE	| varchar	| Yes	| 	| 	|  |
| Grad_GCSE_Any_1	| varchar	| Yes	| 	| 	|  |
| Grad_GCSE_Any_2	| varchar	| Yes	| 	| 	|  |
| Grad_A_Level_Biology	| varchar	| Yes	| 	| 	|  |
| Grad_A_Level_Chemistry	| varchar	| Yes	| 	| 	|  |
| Grad_3rd_Subject	| varchar	| Yes	| 	| 	|  |
| Grad_Other_A_Level_1	| varchar	| Yes	| 	| 	|  |
| Grad_Other_A_Level_2	| varchar	| Yes	| 	| 	|  |
| Grad_Degree_name	| varchar	| Yes	| 	| 	|  |
| Grad_Degree_classification_Degree	| varchar	| Yes	| 	| 	|  |
| A2HE_DHDT_only	| varchar	| Yes	| 	| 	|  |
| Total	| tinyint	| Yes	| 	| 	|  |

## MMI_Schedule

MMI Schedule after being imported and matched with an applicant record. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_MMI_Schedule.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| Date	| datetime	| 	| 	| 	|  |
| Time	| datetime	| 	| 	| 	|  |
| Colour	| varchar	| 	| 	| 	|  |
| Number	| tinyint	| Yes	| 	| 	|  |

## Practique_finalscores

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_Practique_finalscores.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| LS_1stScorer	| tinyint	| 	| 	| 	|  |
| LS_2ndScorer	| tinyint	| 	| 	| 	|  |
| LS_Final	| tinyint	| 	| 	| 	|  |
| MI_1stScore	| tinyint	| 	| 	| 	|  |
| MI_2ndScorer	| tinyint	| 	| 	| 	|  |
| MI_Final	| tinyint	| 	| 	| 	|  |
| Ref_1stScorer	| tinyint	| 	| 	| 	|  |
| Ref_2ndScorer	| tinyint	| 	| 	| 	|  |
| Ref_Final	| tinyint	| 	| 	| 	|  |
| IA_1stScorer	| tinyint	| 	| 	| 	|  |
| IA_2ndScorer	| tinyint	| 	| 	| 	|  |
| IA_Final	| tinyint	| 	| 	| 	|  |

## Reject_post_MMI

Rejecttion post MMI after being imported and matched with an applicant record. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_Reject_post_MMI.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| StudentID	| varchar	| 	| 	| 	|  |
| Station 1 Mean Percentile Rank	| float	| 	| 	| 	|  |
| Station 2 Mean Percentile Rank	| float	| 	| 	| 	|  |
| Station 3 Mean Percentile Rank	| float	| 	| 	| 	|  |
| Station 4 Mean Percentile Rank	| float	| 	| 	| 	|  |
| Station 5 Mean Percentile Rank	| float	| 	| 	| 	|  |
| Station 6 Mean Percentile Rank	| float	| 	| 	| 	|  |
| Station 7 Mean Percentile Rank	| float	| 	| 	| 	|  |
| Station 8 Mean Percentile Rank	| float	| 	| 	| 	|  |
| Overall_Rank	| float	| 	| 	| 	|  |

## RejFdbkLetter

Data for reject with feedback emails. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_RejFdbkLetter.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| Life_And_Social	| varchar	| 	| 	| 	|  |
| Motivation_And_Insight	| varchar	| 	| 	| 	|  |
| Reflective_Skills	| varchar	| 	| 	| 	|  |
| Interests_And_Achievements	| varchar	| 	| 	| 	|  |

## Results_Sheet

Results sheet data after being imported and matched with an applicant's decision record. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_Results_Sheet.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Decisions |
| choice_type_no	| varchar	| 	| Yes	| Yes	| t_Dntl_Decisions |
| prop_entry_yr	| smallint	| 	| Yes	| Yes	| t_Dntl_Decisions |
| Full_Offer_Text	| varchar	| 	| 	| 	|  |
| Condition_Code	| varchar	| 	| 	| 	|  |
| Late_App	| bit	| 	| 	| 	|  |
| IELTS	| bit	| 	| 	| 	|  |
| RoP	| bit	| 	| 	| 	|  |
| Full_Results	| varchar	| 	| 	| 	|  |
| Decision	| varchar	| 	| 	| 	|  |
| Result_Position	| varchar	| 	| 	| 	|  |
| Quality	| varchar	| 	| 	| 	|  |
| Notes	| varchar	| 	| 	| 	|  |
| Received_as_CCO	| varchar	| 	| 	| 	|  |
| Received_from	| varchar	| 	| 	| 	|  |
| Old_Course_Code	| varchar	| 	| 	| 	|  |

## UCAS_Scores

UCAS Score data after being imported and matched with an applicant record. Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FTables%2Ft_Dntl_UCAS_Scores.sql&version=GBmaster)

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| Life_And_Social	| varchar	| 	| 	| 	|  |
| Motivation_And_Insight	| varchar	| 	| 	| 	|  |
| Reflective_Skills	| varchar	| 	| 	| 	|  |
| Interests_And_Achievements	| varchar	| 	| 	| 	|  |
| GLOBAL	| varchar	| 	| 	| 	|  |
| Overall_Score	| varchar	| 	| 	| 	|  |