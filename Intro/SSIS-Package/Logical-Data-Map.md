# INB Extractions Data Flow Task

[[_TOC_]]

This runs several queries in parallel against the Banner Oracle DB via ADO.NET source connections.
The data is temporarily stored in SQL Server holding tables via OLEDB connections. As there
is a 1:1 correspondence between the source queries and the target tables no data conversions
or complicated mappings are required. This is pictorially represented by:
 ![INB_Extractions_Data_Flow_Task.PNG](/.attachments/INB_Extractions_Data_Flow_Task-56d4fbc1-6872-4ace-8969-0e445b8ea330.PNG)
NB: Green arrows represent a data source and blue arrows a data destination

## Source queries

Double clicking on the source queries brings up an editor where the connection, Data access mode, and the SQL command text can be set. This appears thus:
 ![Source _queries.PNG](/.attachments/Source%20_queries-6f663bf7-9c8e-4859-ab29-4daf43fb04f8.PNG)

When building a data flow source the procedure is to:
1. create the data source by dragging from the toolbox - give it a meaningful name. and set the connection, access
mode, and query.
**NB**: when building Oracle queries the best tool for this is Oracle's SQL Developer. Use
this until the queries run efficiently and the data produced is verifiably correct
0. create a data destination - in this case an OLEDB destination (see below)
0. link the source and the destination and then set column mappings

This is repeated for all the source -> destination mappings as required to fulfil the data requirements

## Data Destination

## Set column mappings

