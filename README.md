# Lambda: LL-Yodlee-UpsertProvider

The purpose of this Lambda is to add and update the Yodlee Providers.

This can be used in 2 ways: (It supports 2 types of search_keys)
## Add or update the Yodlee providers 
The Lambda expects the following JSON object to add and update the providers.
  Provide the list of provider Id's that either need to be updated or inserted.
  ### UpsertProviderById
  ```json
  {
    "search_key": "providerId",
    "search_values": "12345678,21080",
    "yodlee_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzUxMiJ9.eyJpc3MiOiIwMDk4ZTc5OC1hZTIzYzQ4Yy1jYjlkLTRlNmItYmE1Yi0zNDMxODhkOGY1ZjkiLCJpYXQiOjE2MDYxMTM4OTQsImV4cCI6MTYwNjExNTI0NH0.d9Id7OvrNHpuElExV43hywqzHxq_fTOo9o7I_KaNQdBymnSXquI2z8C3Ppcsw-PItFrm861W6IzENGqGB14eZOkUibPFb7Mt21orgUheHSHM30y06GMPt7rC6ebk9qEuva3pAWI0IRNAyFokJ-V6-Y89MeV9aIImQIF0zt17TwndKwiFOy8tM6JgCWI9jz7WiNvmJvmRXOTl7zjEXW66i3oOFNzpj-9DUR_Gqq7OW8zUcHFPkFfb7W1-0zZWXLf_dwVvDh46p517PbAPS7a6PWuYVijkh0J4YgEVtCEmrrhlR7aPEgIYh5bO9gUPdZJzp4a5rEM3iVcP0qEkxQ0DJQ"
  }
  ```

## Get the providers by the provider name
Use this option to get the list of all the providers with a given name. This will return JSON in cloudwatch logs.
Send this JSON to the client, so that they can select the providerId's that needs to be added to intelligent401K.com
Once the client gives the list of providerId's,  use the option above to actually add/update the providers to the database 
The Lambda expects the following JSON object to add and update the providers.
  Provide the list of provider Id's that either need to be updated or inserted.
  ### UpsertProviderById
  ```json
  {
    "search_key": "name",
    "search_values": "vanguard",
    "yodlee_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzUxMiJ9.eyJpc3MiOiIwMDk4ZTc5OC1hZTIzYzQ4Yy1jYjlkLTRlNmItYmE1Yi0zNDMxODhkOGY1ZjkiLCJpYXQiOjE2MDYxMTM4OTQsImV4cCI6MTYwNjExNTI0NH0.d9Id7OvrNHpuElExV43hywqzHxq_fTOo9o7I_KaNQdBymnSXquI2z8C3Ppcsw-PItFrm861W6IzENGqGB14eZOkUibPFb7Mt21orgUheHSHM30y06GMPt7rC6ebk9qEuva3pAWI0IRNAyFokJ-V6-Y89MeV9aIImQIF0zt17TwndKwiFOy8tM6JgCWI9jz7WiNvmJvmRXOTl7zjEXW66i3oOFNzpj-9DUR_Gqq7OW8zUcHFPkFfb7W1-0zZWXLf_dwVvDh46p517PbAPS7a6PWuYVijkh0J4YgEVtCEmrrhlR7aPEgIYh5bO9gUPdZJzp4a5rEM3iVcP0qEkxQ0DJQ"
  }
  ```
  
 ## About yodlee_token
 In the above examples,yodlee_token is taken from the Yodlee_log_table. From the latest record. You can create a new yodlee_token.
