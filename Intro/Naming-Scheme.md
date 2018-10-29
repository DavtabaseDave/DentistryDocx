[[_TOC_]]

# Naming conventions in FAD

NB: to prevent confusion this key is presented in uppercase but in ReSIS they are usually lower case.

## Prefixes

_F__: denotes and MSAccess form.
_L__: This denotes a lookup table – there are a few different sub-types of these dependent upon what follows the underscore. Usually they contain a simple digit or character code and its associated description.
_L_Ap__: A lookup table for applications
_L_Stv_: A lookup table that has been extracted from Banner – always followed by a four letter code, e.g. “APDC” that is shorthand (here: APplication DeCision).
_RPT__: This denotes a stored procedure for report generation table – admissions specific ones are denoted by “RPT_Ad_”.
_T__: Prefixes a data table– there are a few different sub-types of these dependent upon what follows the underscore.
_T_Dntl__: This denotes **Dentistry** specific admissions tables.
_V__: This denotes a View – there are a few different sub-types of these dependent upon what follows the underscore. These are frequently used to simplify the programming of the GUI by hiding joins to lookup/linking tables.
_V_AD__: This denotes admissions specific views.
_V_RPT__: This denotes a report view.
_X__: denotes a static table used for holding MS Word documents, PDFs, and other BLOB data.

## Suffixes

\_Prev: This denotes the PREVious year's version of the table. This contains the data for Completed or Withdrawn Students.
$: this denotes that the table is a holding table for data imported from an XLS(X) file. The corresponding "user" table will have the usual "t_" prefix and lack the trailing dollar sign.

## Infixes, others

\_TX/TX\_ : “TX” is used as shorthand for “Transfer”.

## Banner fields/table columns

Any field that is extracted and updated on a frequent basis from Banner retains the original name and should be immediately obvious as such, e.g. swbsusp_susp_exp_ret_date. Any changes to the contents of these fields will be overwritten at the next scheduled extract of data from Banner.
About the only exception to this general rule are the students email addresses iss_email and pers_email. These both come from the same column in GOREMAL with the ISS email being placed into iss_email and their personal email in pers_email. The latter is special in that if there is no personal email in Banner and one is added from within FAD it won’t be removed by the next Banner extract. HOWEVER, you are strongly advised to it put the personal address into Banner and allow that to propagate to FAD in the next extract. Changes to existing personal email address in FAD WON’T survive the Banner extraction process.