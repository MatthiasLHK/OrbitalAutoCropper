# OrbitalAutoCropper

Backend APIs

Login APIs
| Function                     | Purpose                                                                | Input type        | Return type  |
|:----------------------------:|:-----------------------------------------------------------:|:----------------------------:|:------------:|
| getGeneralSettings(req,res) | Pull the shared settings from DB                             | req => request from frontend | 2D Array     |
| getPrivateSettings(req,res) | Pull the user private settings from DB                       | req => request from frontend | 2D Array     |
| addNewSettings(req,res)     | Add and save a new setting into the user's private settings  | req => request from frontend | NULL         |
| uploadSettings(req,res)     | Upload selected private setting into the shared setting      | req => request from frontend | NULL         |
| removeUpload(req,res)       | Un-upload the selected setting                               | req => request from frontend | NULL         |
| editSettings(req,res)       | Modify an existing saved settings                            | req => request from frontend | NULL         |
| deleteSettings(req,res)     | Delete the selected setting from the user's page             | req => request from frontend | NULL         |


Database Tables

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
