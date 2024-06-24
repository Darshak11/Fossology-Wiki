# 1. Add User

![image](https://github.com/fossology/fossology/assets/9692764/1c8805de-d7c4-48b4-8077-44e6a83fd6b2)

* Username: Add a name, which must not be the email address, but any name.
* Description: This is optional
* Email address: is also optional, but helpful
* Access Level: there are different options
  * None: very basic, not database access 
  * Read-only: Read, but not write or downloads
  * Read-Write: Read, write, edit information or download
  * Clearing-Administrator: Read, write, edit information and decisions, download
  * Full Administrator: all rights, including adding users
* User Root Folder: maybe different groups have different root folders
* Password with specific rules
* E-Mail Notification: Check to enable email notification when upload scan is complete
* Default upload visibility
  * Visible only for the active group (which is active right now, see upper right corner)
  * Visible for all groups (which are accessible by you)
  * Make Public (visible for all groups)
* Default agents when uploading files.
* Default Bucket Pool (????)
Add User

# 2. CSV Export
Exports the list of all users with the following fields:
username,description,email,email_notify,userlevel,root_folder,password,userseed,group,group_permission

# 3. CSV Import
Imports a list of users in a CSV format. 

This option permits uploading a single CSV file from your computer to FOSSology. Your FOSSology server has imposed a maximum upload file size of 700 Mbytes.

# 4. Delete a User

Deleting a user removes the user **permanently **from the FOSSology System.
There is **NO **'undo' button.
If the user is the only one having access to specific uploads, work can be unaccessible. Only the Full Adminstrators can help here.

# 5. Edit User Account

Beside changing the fields, which are described when creating a user, also REST API Tokens can be created here for the specific user.

![image](https://github.com/fossology/fossology/assets/9692764/0d254fa2-5553-406b-b939-2de54f36e4f5)

_??What is the difference between oauth client and a new token??_

