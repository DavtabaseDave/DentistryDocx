# Security Groups


There are three main security groups defined for assigning role based security. They originate as the DS Groups:
- FMH_Dentistry_AD_DB_Admissions - to provide appropriate access for Dentistry admissions staff 
- FMH_Dentistry_AD_DB_Administrator - to provide access to all the extra tables for importing spreadsheet/CSV data
- FMH_Dentistry_AD_DB_Academic -  to provide minimal read-only access for academics

Briefly, USERs are creates as [DS\\<USERNAME>] for DB server level LOGINs of the same name (which are sourced from DS). Then ROLEs are created for [<USERNAME>] and then USER [DS\\<USERNAME>] is added to role [<USERNAME>].

Permissions are then assigned to the ROLE **NOT** the USER.