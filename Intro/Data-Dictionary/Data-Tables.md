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

## t\_Dent\_Decisions

Contains mostly Banner derived decision data plus some local management data

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

## t_Dntl_A2L_RR

The only other Banner derived data - Access to Leeds Running Record

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

## t_Dntl_Academic_Scores

Data imported for the different GCSE scores
| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| PIDM	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| Scorer initials	| varchar	| 		| 	| 	|  |
| Std_entry_GCSE_English	| char	| 	| 	| 	|  |
| Std_entry_GCSE_Maths	| char	| 	| 	| 	|  |
| Std_entry_GCSE_Biology_or_Science	| char	| 	| 	| 	|  |
| Std_entry_GCSE_Chemistry_or_Science	| char	| 	| 	| 	|  |
| Std_entry_GCSE_other_1	| char	| 	| 	| 	|  |
| Std_entry_GCSE_other_2	| char	| 	| 	| 	|  |
| Std_entry_GCSE_other_3	| char	| 	| 	| 	|  |
| Std_entry_GCSE_other_4	| char	| 	| 	| 	|  |
| Std_entry_GCSE_other_5	| char	| 	| 	| 	|  |
| Std_entry_A2	| tinyint	| 	| 	| 	|  |
| Grad_English_GCSE	| char	| 	| 	| 	|  |
| Grad_Maths_GCSE	| char	| 	| 	| 	|  |
| Grad_Biology_GCSE	| char	| 	| 	| 	|  |
| Grad_Chemistry_GCSE	| char	| 	| 	| 	|  |
| Grad_GCSE_any_1	| char	| 	| 	| 	|  |
| Grad_GCSE_Any_2	| char	| 	| 	| 	|  |
| Grad_GCSE_total	| varchar	| 	| 	| 	|  |
| Grad_Degree_name	| char	| 	| 	| 	|  |
| Grad_Degree_classification_Degree	| char	| 	| 	| 	|  |
| total_GCSE	| tinyint	| 	| 	| 	|  |
| Reference_statement?	| varchar	| 	| 	| 	|  |
| Notes	| varchar	| 	| 	| 	|  |
| Total	| tinyint	| 	| 	| 	|  |

## t_Dntl_All_MMI_Rankings

Data imported for the different MMI rankings
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

## t_Dntl_BMAT_Scores

BMAT scores after being imported and matched with an applicant record

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

## t_Dntl_Definitive_List_Prev

Instead of keeping separate tables for each of the previous year's applicant data that has been uploaded a single table has been put together to store all this data in one location. This aggregates the different scores etc and as a consequence many of the fields are null-able.

As the t_Dntl_All_MMI_Rankings table may contain multiple entries for an applicant that has applied for both courses a compromise had to be implemented that took only the "minimum" course code. This is to enable the t_Dntl_Definitive_List_Prev to be directly linked to the Previous Applicant and thus be able to be displayed properly in the .NET client application.


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
| Leeds_Code	| char	| Yes	| 	| 	|  |
| Scorer_initials	| varchar	| Yes	| 	| 	|  |
| Std_entry_GCSE_English	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_Maths	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_Biology_or_Science	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_Chemistry_or_Science	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_1	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_2	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_3	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_4	| char	| Yes	| 	| 	|  |
| Std_entry_GCSE_other_5	| char	| Yes	| 	| 	|  |
| Std_entry_A2	| tinyint	| Yes	| 	| 	|  |
| Grad_English_GCSE	| char	| Yes	| 	| 	|  |
| Grad_Maths_GCSE	| char	| Yes	| 	| 	|  |
| Grad_Biology_GCSE	| char	| Yes	| 	| 	|  |
| Grad_Chemistry_GCSE	| char	| Yes	| 	| 	|  |
| Grad_GCSE_any_1	| char	| Yes	| 	| 	|  |
| Grad_GCSE_Any_2	| char	| Yes	| 	| 	|  |
| Grad_GCSE_total	| varchar	| Yes	| 	| 	|  |
| Grad_Degree_name	| char	| Yes	| 	| 	|  |
| Grad_Degree_classification_Degree	| char	| Yes	| 	| 	|  |
| total_GCSE	| tinyint	| Yes	| 	| 	|  |
| Reference_statement?	| varchar	| Yes	| 	| 	|  |
| Notes	| varchar	| Yes	| 	| 	|  |
| Total	| tinyint	| Yes	| 	| 	|  |

## t_Dntl_MMI_Schedule

MMI Schedule after being imported and matched with an applicant record.

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| Date	| datetime	| 	| 	| 	|  |
| Time	| datetime	| 	| 	| 	|  |
| Colour	| varchar	| 	| 	| 	|  |
| Number	| tinyint	| Yes	| 	| 	|  |

## t_Dntl_Reject_post_MMI

Rejecttion post MMI after being imported and matched with an applicant record.

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

## t_Dntl_RejFdbkLetter

Data for reject with feedback emails.

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| Life_And_Social	| varchar	| 	| 	| 	|  |
| Motivation_And_Insight	| varchar	| 	| 	| 	|  |
| Reflective_Skills	| varchar	| 	| 	| 	|  |
| Interests_And_Achievements	| varchar	| 	| 	| 	|  |

## t_Dntl_Results_Sheet

Results sheet data after being imported and matched with an applicant's decision record.

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

## t_Dntl_UCAS_Scores

UCAS Score data after being imported and matched with an applicant record.

| Attribute | DataType | Allow Nulls? | PKey? | FKey? | Notes |
|-----------|----------|--------------|-------|-------|-------|
| pidm	| int	| 	| Yes	| Yes	| t_Dntl_Applicants |
| Life_And_Social	| varchar	| 	| 	| 	|  |
| Motivation_And_Insight	| varchar	| 	| 	| 	|  |
| Reflective_Skills	| varchar	| 	| 	| 	|  |
| Interests_And_Achievements	| varchar	| 	| 	| 	|  |
| GLOBAL	| varchar	| 	| 	| 	|  |
| Overall_Score	| varchar	| 	| 	| 	|  |