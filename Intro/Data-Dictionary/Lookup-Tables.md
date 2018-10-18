# Lookup Tables

When using the lookup tables in a query, they should be joined by the PK field to the referencing column in the data table. The description field (ends "_desc") should be used in your output or to check for a particular value in a "where" clause.

# l_Achieved_Grade

Populates the "Achieved Grade" menu on the Decisions tab
| Attribute | DataType | Allow Nulls? | PKey? |
|-----------|----------|--------------|-------|
| achieved_code	| tinyint	|  | Yes |
| achieved_desc	| varchar	| |  |