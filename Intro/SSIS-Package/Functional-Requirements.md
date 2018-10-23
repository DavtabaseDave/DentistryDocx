# Functional Requirements

In no particular order theses are
- Connection managers **MUST** be used to simplify testing of the package against different DBs. This will also simplify deployment.
- Credentials of stored connection to Banner **MUST** be protected. Thus the entire BIDS project that contains them and facilitates their development **MUST** have its security protection level set to `EncryptSensitiveWithPassword` so that this can be used to deploy the package to the Integration Services DB.
- In order to prevent have to update the entire package at the start of each new academic year Project Level parameters **MUST** be used so that they can easily be altered
- As there is a slight chance that another Faculty will want a similar DB and variables and other names object should clearly indicate by a prefix (*"Dent"*) that they are Faculty specific
- At the same time should prefer Project params to Package variables as these can sometimes be ineffective.
