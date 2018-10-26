# How To Add Edit DTSX Packages

[[_TOC_]]

## Important Note

This is a **NOT** a guide on how to setup and later edit DTSX packages in general. This is merely 
a guide on how the DTSXs for the StEdBase, ReSIS, and FAD are setup for the express purpose 
of extracting data from Banner (INB) to be stored in SQL Server DBs (this may include others at 
a later date).

To avoid having to alter myriad queries by hand every year, the packages are setup to use Package
Parameters to set faculty and/or term specific parameters in the queries before they are sent to
the Banner Oracle DB.

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

## 4. Set column mappings

To set/alter the column mappings, click on the "Mappings" item in the list box. This appears thus:
![source_dest_mappings.PNG](/.attachments/source_dest_mappings-29410702-bc68-4fcd-82e6-389f4b467760.PNG)
Mappings can be altered as desired by dragging and dropping, selecting and deleting, etc..

## Iteration
This steps are repeated for all the source -> destination mappings as required to fulfill the data requirements of the application

## Identify parameters

The queries are inspected to identify suitable parameters for the package. These include restrictions such as:
- Faculty Code
- School Code
- Selector Centre
- Entry Year
- Term Code of Entry

These should be added as Project Parameters. Sensible naming scheme should be employed and
 the most suiteable data type for the parameters is String

## Add Expressions to the Data Flow

Although static text queries are used to build the data flows they are parameterized using the 
Data Flow's "Expressions" property. Briefly this allows the developer to introduce any number of parameters into the SQL string
before it is sent to the source DB.

It will always overwrite **ANY** alterations to the SQL text in the data source editor. To update the query the SqlCommand expression must
be altered. This can be found by selecting the background of the Data Flow and scrolling down the "Properties" page to "Expressions"
as shown here:
![Expressions.PNG](/.attachments/Expressions-b20b031c-8cf3-4d82-8598-972dc9f5d40f.PNG)
Click on the RHS most part of the value that lists the query string to bring up the editor

### Expression Builder

This badly designed editor appears thus:
 ![Expression Builder.PNG](/.attachments/Expression%20Builder-cd9316e5-a093-43dc-8d27-54a6ac231fa7.PNG).
Great care must be taken when using this editor as:
1. The font used for the actual query is tiny and
0. The Query text control (indicated in red) is not expandable - the separate controls grow in 
proportion to the editor window.
0. The query must be surrounded by double quotes and any double quotes within the SQL string
must be escaped
0. It doesn't deal with newlines properly
0. when dragging parameters from the top left tree view into the query text it doesn't insert them
properly. Instead inserting the following into the query string:
`"' +@[$Project::AdApplNoMask] + '"` (the substitution has to be performed by a parser)
it merely inserts 
`@[$Project::AdApplNoMask]`
leaving the inexperienced user to puzzle over why it doesn't work.

When making changes to these always click the "Evaluate Expression" button before saving it.




