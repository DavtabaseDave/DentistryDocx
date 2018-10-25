# How To Add Edit DTSX Packages

[[_TOC_]]

## Important Note

This is a **NOT** a guide on how to setup and later edit DTSX packages in general. This is merely 
a guide on how the DTSXs for the StEdBase, ReSIS, and FAD are setup for the express purpose 
of extracting data from Banner (INB) to be stored in SQL Server DBs (this may include others at 
a later date).

To avoid having to alter myriad queries by hand every year, the packages are setup to use Package Parameters to set faculty and/or term specific parameters in the queries before they are sent to the Banner Oracle DB.

The steps involved building a Data Flow item in a Data Flow Task (which must already be present
in the Control Flow):

## 1. Setup Source data

When building a data flow source the procedure is to:
Create the data source by dragging from the toolbox - give it a meaningful name. and set the connection, access
mode, and SQL query.
**NB**: when building Oracle queries the best tool for this is Oracle's SQL Developer. Use
this until the queries run efficiently and the data produced is verifiably correct

## 2. Setup Data Destination

When building a data flow destination the procedure is to:
Create the data destination by dragging from the toolbox - give it a meaningful name. and set the
connection, access mode, and select the table from the drop down.

## 3. Link data source and destination 

This is made by dragging the blue arrow (attached to the data source) and connecting it manually
to the data destination. To break a connection, select the blue arrow and press the "DEL" key


0. create a data destination - in this case an OLEDB destination
0. link the source and the destination and then set column mappings