[[_TOC_]]

# Package Settings

This sets out the two connection managers and the Package Parameters

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

**NB: don't put the contents of sets in the Value part of the parameter - SSIS doesn't like it**

### AdApplNoMask

A string, default value: 180000000
Purpose: limit applicant (and associated data to a minimum UCAS ID
