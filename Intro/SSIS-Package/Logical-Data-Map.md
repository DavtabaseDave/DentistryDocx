# INB Extractions Data Flow Task

[[_TOC_]]

This runs several queries in parallel against the Banner Oracle DB via ADO.NET source connections.
The data is temporarily stored in SQL Server holding tables via OLEDB connections. As there
is a 1:1 correspondence between the source queries and the target tables no data conversions
are required and is pictorially represented by:
 ![INB_Extractions_Data_Flow_Task.PNG](/.attachments/INB_Extractions_Data_Flow_Task-56d4fbc1-6872-4ace-8969-0e445b8ea330.PNG)
NB: Green arrows represent a data source and blue arrows a data destination