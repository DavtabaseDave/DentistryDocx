# How To Add Edit DTSX Packages

[[_TOC_]]

## Important Note

This is a **NOT** a guide on how to setup and later edit DTSX packages in general. This is merely 
a guide on how the DTSXs for the StEdBase, ReSIS, and FAD are setup for the express purpose 
of extracting data from Banner (INB) to be stored in SQL Server DBs.

To avoid having to alter myriad queries by hand every year, the packages are setup to use package parameters to set faculty and/or term specific parameters for the queries sent to the Banner Oracle DB.