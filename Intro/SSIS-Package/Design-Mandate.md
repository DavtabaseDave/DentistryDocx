In order to best facilitate maintenance and update of SSIS packages the following guidelines are more than strongly urged
In no particular order theses are:
- Connection managers **MUST** be used to simplify testing of the package against different DBs.
This will also simplify deployment.
- Credentials of stored connection to Banner **MUST** be protected. Thus the entire BIDS project
that contains them and facilitates their development **MUST** have its security protection level
set to `EncryptSensitiveWithPassword` so that this can be used to deploy the package to the
Integration Services DB.
- Queries sent to the Oracle DB will have a plain text, non-variable containing, version in the data
flow ADO .NET Data sources so that data flows and OLE DB Destinations (SQL Server) can be
setup. These will be replaced at runtime using the "Expressions" property of the data flow
containing them. These will make reference to the Project Parameters to prevent the package
being tied to a particular academic year.
- Data Flows can only contain **NO MORE THAN 10** Data Flow Components as only ten expressions
are permitted per data flow. In practice this is not too problematic as the Oracle queries are run in
parallel.
- to avoid confusion, meaningful names **MUST** be ascribed to all data sources and destinations. These
do not need to be complicated, merely facilitate easy understanding of the parts - e.g. destination
holding table name ("h_Applicants") or the what the data source is acquiring ("Applicants").
If they become too long and descriptive they make the whole picture difficult to grasp
- Where applicable raw SQL should be avoided in SQL tasks in the main control flow steps except to
call SProcs in the DB (with or without an enclosing transaction). This facilitates better error detection
as the DB model is held in an SSDT project that catches most internal errors.