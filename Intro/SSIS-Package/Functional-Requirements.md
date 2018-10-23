# Functional Requirements

In no particular order theses are
- Connection managers **MUST** be used to simplify testing of the package against different DBs
- Credentials of stored connection to Banner **MUST** be protected. Thus the entire BIDS project that contains them and facilitates their development **MUST** have its security protection level set to `EncryptSensitiveWithPassword` so that this can be used to deploy the package to the Integration Services DB.
- In order to prevent have to update the entire 