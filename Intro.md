Data Tables
===========

t\_Dntl\_Applicants
-------------------

The main applicants table containing Banner derived data and mutable
local data

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>spriden_pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>skrsain_applicant_no</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>spriden_id</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>skrsain_personalid</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>spriden_last_name</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>spriden_first_name</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>spriden_mi</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>student_initials</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>spbpers_name_prefix</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>spbpers_birth_date</td>
<td>datetime</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>current_age</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>age_at_entry</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>spbpers_sex</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>eth_code</td>
<td>varchar</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_stvethn</td>
</tr>
<tr class="odd">
<td>sprmedi_disa_code</td>
<td>varchar</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_stvdisa</td>
</tr>
<tr class="even">
<td>skrsain_criminal_conv</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skruccr_ssdt_code_home</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>STREET_ADDRESS_PH_LINE1</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>STREET_ADDRESS_PH_LINE2</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>STREET_ADDRESS_PH_LINE3</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>spraddr_city</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>nation_description_ph</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>spraddr_zip</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>telephone_number_ph</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skbspin_natn_code_legal</td>
<td>varchar</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_stvnatn</td>
</tr>
<tr class="even">
<td>saradap_resd_code</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skrsain_appl_date</td>
<td>datetime</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>email_address</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skbuarf_predictedgrades</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>sorhsch_sbgi_code</td>
<td>int</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_stvsbgi</td>
</tr>
<tr class="odd">
<td>skrsain_ssdt_code_pared</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>skrsain_care</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>isActive</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Query_Sent</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Query_Deadline</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>extension_deadline</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>isExtension</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Attending_Open_Day</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Offer_Holder_Visit_Date</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Attended_Pre_Offer_Day</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Attended_Offer_Holder_Day</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Attended_Offer_Holder_Visit_Date</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Notes</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Form_Received</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Email_Ack</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Entry_Req</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>A2L</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>International_agent</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_International_Agent</td>
</tr>
<tr class="odd">
<td>isSports</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>isDisability</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>isFeesAssess</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>isMature</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>underYes8</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>hasDeferred</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>data_source</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_data_source</td>
</tr>
<tr class="even">
<td>VS</td>
<td>timestamp</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>CreatedDate</td>
<td>smalldatetime</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>LastUser</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

Decisions
---------

Contains mostly Banner derived decision data plus some local management
data

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>skruccr_pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>skruccr_choice_type_no</td>
<td>varchar</td>
<td></td>
<td>Yes</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skruccr_ssdt_code_crse</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>DEGC_CODE</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skrutop_program</td>
<td>varchar</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_smrprle</td>
</tr>
<tr class="even">
<td>skruccr_ssdt_code_decn</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skruccr_decision_date</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>skruccr_ssdt_code_reply</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skruccr_ssdt_code_cf_decn</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>skruccr_ssdt_code_ap_resp</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skruccr_prop_entry_yr</td>
<td>smallint</td>
<td></td>
<td>Yes</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>skruccr_prop_entry_mth</td>
<td>smallint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skruccr_conditions</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>skruccr_ssdt_code_entry</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>date_off_let_sent</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>gurmail_code</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>predicted_grade</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Predicted_Grade</td>
</tr>
<tr class="even">
<td>achieved_grade</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Achieved_Grade</td>
</tr>
<tr class="odd">
<td>reason_for_rejection</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Reason_Rej</td>
</tr>
<tr class="even">
<td>Reason_For_Rej_Notes</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>VS</td>
<td>timestamp</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>CreatedDate</td>
<td>smalldatetime</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>LastUser</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_A2L\_RR
----------------

Only other Banner derived data - Access to Leeds Running Record

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>sarchrt_pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>spriden_id</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>skrsain_personalid</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>spriden_first_name</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>spriden_last_name</td>
<td>nvarchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>skruccr_ssdt_code_crse</td>
<td>varchar</td>
<td></td>
<td>Yes</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Programme</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>A2L_Eligibility_Decision</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>saradap_term_code_entry</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Number_Courses_Applied_For</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>A2L_Route</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>A2L_Application_Received</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>A2L_Decision_Date</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_Academic\_Scores
-------------------------

Data imported for the different GCSE scores

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PIDM</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>Scorer initials</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_English</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_GCSE_Maths</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_Biology_or_Science</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_GCSE_Chemistry_or_Science</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_other_1</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_GCSE_other_2</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_other_3</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_GCSE_other_4</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_other_5</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_A2</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_English_GCSE</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Grad_Maths_GCSE</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_Biology_GCSE</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Grad_Chemistry_GCSE</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_GCSE_any_1</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Grad_GCSE_Any_2</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_GCSE_total</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Grad_Degree_name</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_Degree_classification_Degree</td>
<td>char</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>total_GCSE</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Reference_statement?</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Notes</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Total</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_All\_MMI\_Rankings
---------------------------

Data imported for the different MMI rankings

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>prog_code</td>
<td>varchar</td>
<td></td>
<td>Yes</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Mean_Rank_Task</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Offer_Cutoff</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_1_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_1_Quartile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Quartile_Rank</td>
</tr>
<tr class="odd">
<td>Station_2_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_2_Quartile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Quartile_Rank</td>
</tr>
<tr class="odd">
<td>Station_3_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_3_Quartile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Quartile_Rank</td>
</tr>
<tr class="odd">
<td>Station_4_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_4_Quartile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Quartile_Rank</td>
</tr>
<tr class="odd">
<td>Station_5_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_5_Quartile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Quartile_Rank</td>
</tr>
<tr class="odd">
<td>Station_6_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_6_Quartile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Quartile_Rank</td>
</tr>
<tr class="odd">
<td>Station_7_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_7_Quartile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Quartile_Rank</td>
</tr>
<tr class="odd">
<td>Station_8_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_8_Quartile_Rank</td>
<td>tinyint</td>
<td></td>
<td></td>
<td>Yes</td>
<td>l_Quartile_Rank</td>
</tr>
</tbody>
</table>

t\_Dntl\_BMAT\_Scores
---------------------

BMAT scores after being imported and matched with an applicant record

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>Section Yes Score</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Section 2 Score</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Essay Answered</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Section 3 Content</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Section 3 English</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Section 3 English Score</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Overall Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_Definitive\_List\_Prev
-------------------------------

Instead of keeping separate tables for each of the previous year’s
applicant data that has been uploaded a single table  
has been put together to store all this data in one location. This
aggregates the different scores etc and as a consequence  
many of the fields are null-able.

As the t\_Dntl\_All\_MMI\_Rankings table may contain multiple entries
for an applicant that has applied for both courses  
a compromise had to be implemented that took only the “minimum” course
code. This is to enable the t\_Dntl\_Definitive\_List\_Prev  
to be directly linked to the Previous Applicant and thus be able to be
displayed properly in the .NET client application.

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>spriden_pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants_Prev</td>
</tr>
<tr class="even">
<td>A2L_Eligibility_Decision</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>A2L_Mark</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>A2L_Pass</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>hasBMAT</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>LS_1stScorer</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>LS_2ndScorer</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>LS_Final</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>MI_1stScore</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>MI_2ndScorer</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>MI_Final</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Ref_1stScorer</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Ref_2ndScorer</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Ref_Final</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>IA_1stScorer</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>IA_2ndScorer</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>IA_Final</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Section 1 Score</td>
<td>float</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Section 2 Score</td>
<td>float</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Essay Answered</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Section 3 Content</td>
<td>float</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Section 3 English</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Section 3 English Score</td>
<td>float</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Overall Rank</td>
<td>float</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Mean_Rank_Task</td>
<td>float</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Offer_Cutoff</td>
<td>float</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_1_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_1_Quartile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_2_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_2_Quartile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_3_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_3_Quartile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_4_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_4_Quartile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_5_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_5_Quartile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_6_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_6_Quartile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_7_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_7_Quartile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station_8_Mean_Percentile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station_8_Quartile_Rank</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>MMI_Date</td>
<td>datetime</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>MMI_Time</td>
<td>time</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>MMI_Colour</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>MMI_Number</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Life_And_Social</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Motivation_And_Insight</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Reflective_Skills</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Interests_And_Achievements</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>GLOBAL</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Overall_Score</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Leeds_Code</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Scorer_initials</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_English</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_GCSE_Maths</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_Biology_or_Science</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_GCSE_Chemistry_or_Science</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_other_1</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_GCSE_other_2</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_other_3</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_GCSE_other_4</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Std_entry_GCSE_other_5</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Std_entry_A2</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_English_GCSE</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Grad_Maths_GCSE</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_Biology_GCSE</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Grad_Chemistry_GCSE</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_GCSE_any_1</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Grad_GCSE_Any_2</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_GCSE_total</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Grad_Degree_name</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Grad_Degree_classification_Degree</td>
<td>char</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>total_GCSE</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Reference_statement?</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Notes</td>
<td>varchar</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Total</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_MMI\_Schedule
----------------------

MMI Schedule after being imported and matched with an applicant record

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>Date</td>
<td>datetime</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Time</td>
<td>datetime</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Colour</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Number</td>
<td>tinyint</td>
<td>Yes</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_Reject\_post\_MMI
--------------------------

Rejecttion post MMI after being imported and matched with an applicant
record

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>StudentID</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station 1 Mean Percentile Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station 2 Mean Percentile Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station 3 Mean Percentile Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station 4 Mean Percentile Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station 5 Mean Percentile Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station 6 Mean Percentile Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Station 7 Mean Percentile Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Station 8 Mean Percentile Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Overall_Rank</td>
<td>float</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_RejFdbkLetter
----------------------

Data for reject with feedback emails

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>Life_And_Social</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Motivation_And_Insight</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Reflective_Skills</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Interests_And_Achievements</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_Results\_Sheet
-----------------------

Results sheet data after being imported and matched with an applicant’s
decision record

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Decisions</td>
</tr>
<tr class="even">
<td>choice_type_no</td>
<td>varchar</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Decisions</td>
</tr>
<tr class="odd">
<td>prop_entry_yr</td>
<td>smallint</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Decisions</td>
</tr>
<tr class="even">
<td>Full_Offer_Text</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Condition_Code</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Late_App</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>IELTS</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>RoP</td>
<td>bit</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Full_Results</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Decision</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Result_Position</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Quality</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Notes</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Received_as_CCO</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Received_from</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Old_Course_Code</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

t\_Dntl\_UCAS\_Scores
---------------------

UCAS Score data after being imported and matched with an applicant
record

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>DataType</th>
<th>Allow Nulls?</th>
<th>PKey?</th>
<th>FKey?</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>pidm</td>
<td>int</td>
<td></td>
<td>Yes</td>
<td>Yes</td>
<td>t_Dntl_Applicants</td>
</tr>
<tr class="even">
<td>Life_And_Social</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Motivation_And_Insight</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Reflective_Skills</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Interests_And_Achievements</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>GLOBAL</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Overall_Score</td>
<td>varchar</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>
