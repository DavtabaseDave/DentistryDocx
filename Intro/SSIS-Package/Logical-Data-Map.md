# INB Extractions Data Flow Task

[[_TOC_]]

**If you're unfamiliar with Expressions and/or Data flows in general, see [How To Add Edit DTSX Packages](/Intro/How-To-Add-Edit-DTSX-Packages)**

This runs several queries in parallel against the Banner Oracle DB via ADO .NET source connections.
The data is temporarily stored in SQL Server holding tables via OLEDB connections. As there
is a 1:1 correspondence between the source queries and the target tables no data conversions
or complicated mappings are required. 

This is pictorially represented by:
 ![INB_Extractions_Data_Flow_Task.PNG](/.attachments/INB_Extractions_Data_Flow_Task-56d4fbc1-6872-4ace-8969-0e445b8ea330.PNG)
NB: Green arrows represent a data source and blue arrows a data destination

## Source queries

Double clicking on the source queries brings up an editor where the connection, Data access mode, and the SQL command
text can be set. This appears thus:
 ![Source _queries.PNG](/.attachments/Source%20_queries-6f663bf7-9c8e-4859-ab29-4daf43fb04f8.PNG)


This is repeated for all the source -> destination mappings as required to fulfill the data requirements

## Data Destination

Double clicking on the data destination brings up an editor where the connection, access mode, target table can be set.
This appears thus (for h_Applicants destination table):
 ![Data_destination.PNG](/.attachments/Data_destination-c2d5aa3a-bd10-4e16-9d9a-507dfa9eda09.PNG)

0. link the source and the destination and then set column mappings (see below)

## Set column mappings

To set/alter the column mappings, click on the "Mappings" item in the list box. This appears thus:
![source_dest_mappings.PNG](/.attachments/source_dest_mappings-29410702-bc68-4fcd-82e6-389f4b467760.PNG)
Mappings can be altered as desired by dragging and dropping, selecting and deleting, etc..

