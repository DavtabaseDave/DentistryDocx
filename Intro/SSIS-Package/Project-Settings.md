[[_TOC_]]

# Package Settings

This sets out the two connection managers and the Project Parameters

## Connection Managers

### Target.FAD.conmgr

To be used for any data destination
An OLE DB\SQL Server Native Client connection set up like so:
 ![Target_FAD_conmgr.PNG](/.attachments/Target_FAD_conmgr-18422a5b-5c4f-4c44-b36d-392f7902083e.PNG)

### INB_PROD.LUSTXFR.conmgr

To be used for any data source
An ADO .NET\Oracle Client connection set up like so (password is not displayed as the
project is password protected - this has to be entered EVERY time a change is made to
this connection)
 ![INB_PROD_LUSTXFR_conmgr.PNG](/.attachments/INB_PROD_LUSTXFR_conmgr-7d1df574-a27f-4b87-a657-aca2e169fa6d.PNG)

## Project Parameters

**NB: don't put the contents of sets in the Value part of the parameter - SSIS doesn't like it** ;)
NB1: quotes are not required for strings in the Parameters editor

The editor appears thus:
 ![Project_Params.PNG](/.attachments/Project_Params-e2d9c461-2f96-48c8-b478-5f4a6492538e.PNG)

### AdApplNoMask

A string, default value: 180000000
Purpose: limit applicants (and associated data) to a minimum UCAS ID

### AdDentFacCode

A string, default value: MH
Purpose: limit A2L data to the MH Faculty code

### AdDentSchoolCode

A string, default value: DENT
Purpose: limit A2L data to the DENT Department code

### AdDentSelectorCentre

A string, default value: 1K
Purpose: limit applicants (and associated data) to the 1K Select Centre code

### AdEntryYear

A string, default value: 2019
Purpose: limit applicants (and associated data) to the earliest entry year of 2019

### AdPrevYear

A string, default value: 17
Purpose: limit applicants (and associated data) to those made after 31-AUG-<AdPrevYear>.
That is, acquire data from at the earliest, the beginning of the previous academic year - we want the deferred applicants.

### AdTermCodeEntry

A string, default value: 201920
Purpose: to limit offers to the entry year and A2L data to the entry year plus the year after.
