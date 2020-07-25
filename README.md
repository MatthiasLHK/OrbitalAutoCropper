# OrbitalAutoCropper

## Backend APIs

### Login APIs
| Function                     | Purpose                                                     | Input type                      | Return type  |
|:-----------------------------|:------------------------------------------------------------|:-------------------------------:|:------------:|
| createAccount(req,res) | Creates a new account when the user registers                     | req => username, password, email    | NULL |
| getLoginAuth(req,res)  | Checks the login credentials provided by the user when logging in | req => username, password           | Boolean |
| emailAuth(email,id)    | Creates an email verification promise                             | req => email, user id               | Promise object
| linkMaker(id)          | Makes the verification email link                                 | req => user id                      | String |
| verify(req,res)        | Verify that the user has confirmed the registered email           | req => user id, authentication code | DB action |

### Profiles APIs
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

### Settings APIs
| Function                    | Purpose                                                      | Input type                 | Return type  |
|:----------------------------|:-------------------------------------------------------------|:---------------------------|:-------------|
| getGeneralSettings(req,res) | Pull the shared settings from DB                             | req => null                | 2D Array     |
| getPrivateSettings(req,res) | Pull the user private settings from DB                       | req => user id             | 2D Array     |
| addNewSettings(req,res)     | Add and save a new setting into the user's private settings  | req => user id             | NULL         |
| uploadSettings(req,res)     | Upload selected private setting into the shared setting      | req => user id, setting id | NULL         |
| removeUpload(req,res)       | Un-upload the selected setting                               | req => user id, setting id | NULL         |
| editSettings(req,res)       | Modify an existing saved settings                            | req => user id, setting id | NULL         |
| deleteSettings(req,res)     | Delete the selected setting from the user's page             | req => user id, setting id | NULL         |

### Device APIs
| Function                        | Purpose                                                      | Input type                 | Return type  |
|:--------------------------------|:------------------------------------------------|:-----------------------------|:-------------|
| getConnectedDevice(req,res)     | Get the basic data on all the registered device | req => user id               | 2D Array |
| getFullConnectedDevice(req,res) | Get all data related to all registered device   | req => user id               | 2D Array |
| getInfo(x)                      | Get all data on a specific registered device    | req => device id             | 1D Array |
| registerNewDevice(req,res)      | Add a new device that is tagged to the user     | req => user id, device id    | DB Action |
| sendDevice(req,res)             | Send and upload a saved setting to that device  | req => setting id, device id | NULL |

### Rating APIs
| Function                      | Purpose                                | Input type        | Return type  |
|:---------------------|:------------------------------------------------|:------------------|:-------------|
| getTopRated(req,res) | Returns the top 5 most rated settings           | req => null       | 2D Array |
| getNewPost(req,res)  | Returns the top 5 most recently shared settings | req => null       | 2D Array |
| upVote(req,res)      | Increase the rating of a setting by 1           | req => setting id | DB Action |
| downVote(req,res)    | Decrease the rating of a setting by 1           | req => setting id | DB Action |

### Hashing APIs
| Function                 | Purpose                                                         | Input type     | Return type  |
|:-------------------------|:----------------------------------------------------------------|:---------------|:-------------|
| idMaker()                | Creates a random 10 character Alphanumeric code                 | NULL           | String       |
| hasher(password)         | Use the bcryptjs package to hash the user password input        | String         | String       |
| checkPass(hash,password) | Use the bcryptjs package to check the input password and hashed | String, String | Boolean      |



## Database Tables

### User details

| Column name        | Data type               | Nullable  | Default | Relationship |
|:-------------------|:------------------------|:----------|:--------|:-------------|
| User id            | Variable Character(30)  | NO        | None    | 1-1 with User Device, Profiles<br>1-Many with Private settings, Shared Settings |
| Username           | Variable Character(335) | NO        | None    | None |
| Password           | Variable Character(335) | NO        | None    | None |
| Email              | Variable Character(335) | NO        | None    | None |
| Created on         | TimeStamp               | NO        | None    | None |
| Verified           | Boolean                 | NO        | False   | None |
| Authcode           | Variable Character(20)  | NO        | None    | None |
| Last login         | TimeStamp               | YES       | None    | None |
