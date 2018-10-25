# INB Extractions Data Flow Task

[[_TOC_]]

**Ignore the Vital Note below at your peril**

This runs several queries in parallel against the Banner Oracle DB via ADO .NET source connections.
The data is temporarily stored in SQL Server holding tables via OLEDB connections. As there
is a 1:1 correspondence between the source queries and the target tables no data conversions
or complicated mappings are required. 

This is pictorially represented by:
 ![INB_Extractions_Data_Flow_Task.PNG](/.attachments/INB_Extractions_Data_Flow_Task-56d4fbc1-6872-4ace-8969-0e445b8ea330.PNG)
NB: Green arrows represent a data source and blue arrows a data destination

## **Vital Note**

Although static text queries are used to build the data flows they are parameterized using the 
Data Flow's "Expressions" property. Briefly this allows the developer to introduce any number of parameters into the SQL string before it is sent to the source DB. 
  ![Expressions.PNG](/.attachments/Expressions-b20b031c-8cf3-4d82-8598-972dc9f5d40f.PNG)


## Source queries

Double clicking on the source queries brings up an editor where the connection, Data access mode, and the SQL command
text can be set. This appears thus:
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

Double clicking on the data destination brings up an editor where the connection, access mode, target table can be set.
This appears thus (for h_Applicants destination table):
 ![Data_destination.PNG](/.attachments/Data_destination-c2d5aa3a-bd10-4e16-9d9a-507dfa9eda09.PNG)

When building a data flow destination the procedure is to:
1. create the data destination by dragging from the toolbox - give it a meaningful name. and set the
connection, access mode, and select the table from the drop down.
0. link the source and the destination and then set column mappings (see below)
**NB**: when creating holding tables the best way is in SSMS using openquery() against a 
linked server to create the new table structure based on the Oracle columns.

## Link data source and destination 

This is made by dragging the blue arrow (attached to the data source) and connecting it manually
to the data destination. To break a connection, select the blue arrow and press the "DEL" key

## Set column mappings

To set/alter the column mappings, click on the "Mappings" item in the list box. This appears thus:
![source_dest_mappings.PNG](/.attachments/source_dest_mappings-29410702-bc68-4fcd-82e6-389f4b467760.PNG)
Mappings can be altered as desired by dragging and dropping, selecting and deleting, etc..

