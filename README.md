# OrbitalAutoCropper

## Backend APIs

# Login APIs
| Function                    | Purpose                                                      | Input type                 | Return type  |
|:----------------------------|:-------------------------------------------------------------|:---------------------------|:-------------|
| getGeneralSettings(req,res) | Pull the shared settings from DB                             | req => null                | 2D Array     |
| getPrivateSettings(req,res) | Pull the user private settings from DB                       | req => user id             | 2D Array     |
| addNewSettings(req,res)     | Add and save a new setting into the user's private settings  | req => user id             | NULL         |
| uploadSettings(req,res)     | Upload selected private setting into the shared setting      | req => user id, setting id | NULL         |
| removeUpload(req,res)       | Un-upload the selected setting                               | req => user id, setting id | NULL         |
| editSettings(req,res)       | Modify an existing saved settings                            | req => user id, setting id | NULL         |
| deleteSettings(req,res)     | Delete the selected setting from the user's page             | req => user id, setting id | NULL         |

# Profiles APIs
| Function                     | Purpose                                                     | Input type                      | Return type  |
|:-----------------------------|:------------------------------------------------------------|:-------------------------------:|:------------:|
| initialProfile(req,res)      | Create the starting blank profile object will null values   | req => user id                  | 1D Array |
| updateComment(req, res)      | Update the bio of the user's profile                        | req => user id, comment string  | NULL     |
| getProfile(req,res)          | Retrieve the profile information of the user                | req => user id                  | 1D Array |
| updateProfile(req,res)       | Update the profile information of the user                  | req => user id, profile strings | NULL     |
| getUserDetails(req, res)     | Get the basic user account information                      | req => user id                  | 1D Array |
| browseUserSettings(req, res) | Search for a setting of a specific user                     | req => user id, setting id      | 2D Array |
| browseUserProfile(req, res)  | Search for a profile of a specific user                     | req => user id                  | 1D Array |
| browseUserDetails(req, res)  | Search for the account details of a specific user           | req => user id                  | 1D Array |


Database Tables

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
