# Views

[[_TOC_]]

These can be divided into two broad categories:
-  **UI Views** - for data access in the .NET client program to provide "shaped" data for populating controls
- **Reporting Views** - simply displays data in the user's desired format for copying and use elsewhere


## UI Views

### Summary of Applicants 

This provides a read-only source of data for the Applicants browser Form where the user can search for a particular record then call it up for editing. There is also a corresponding view for the previous year's applicants. Full source can be located [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FViews%2Fv_Dntl_Applicants_Precis.sql&version=GBmaster) and [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FViews%2Fv_Dntl_Applicants_Prev_Precis.sql&version=GBmaster
)

### v_Dntl_Email_Ack_Combo

This populates the Combo box for sending out acknowledgement emails to new applicants. They are picked up based on the following criteria:
- they've not had an email acknowledgement before and
- there's no decision for their application and
- their application was made no more than four weeks ago

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FViews%2Fv_Dntl_Email_Ack_Combo.sql&version=GBmaster
)

### v_Dntl_Email_Ack_To_Go

This is used to provide the data when sending out emails for a particular courses' applicants. It uses identical criteria to the one that populated the combo box except it also requires that they have an email address of at least 7 characters in length

Full source [here](https://universityofleeds.visualstudio.com/FAD/FAD%20Team/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FViews%2Fv_Dntl_Email_Ack_To_Go.sql&version=GBmaster)

## Reporting Views

The remainder of the views in the DB are used for reporting. These are listed [here](https://universityofleeds.visualstudio.com/FAD/_git/FAD-SSDT?path=%2FFAD%2Fdbo%2FViews&version=GBmaster)

