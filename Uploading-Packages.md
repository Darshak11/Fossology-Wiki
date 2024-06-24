# General Instructions

![instructions-upload](https://github.com/fossology/fossology/assets/9692764/802c42fd-c4ef-43a1-bd06-699035a96d5d)


# 1. Uploading a file

![upload-file](https://github.com/fossology/fossology/assets/9692764/babf6130-a467-412b-a695-850781e8e1cb)


## 1.0 Rights
Every upload stored in a specific group and the rights are managed per group.
So please make sure that you have sufficient rights for your planned use case.
Please see [Access Control](https://github.com/fossology/fossology/wiki/Access-Control)

The maximal allowed file size is 700 MB.

## 1.1 Select a folder
First a folder must be selected, where the component shall be uploaded. 
The folder structure can be managed according to the the rules of the clearing process.

![image](https://github.com/fossology/fossology/assets/9692764/3af6b60d-af57-4c78-94f6-f83d07c1f412)
When clicking on folder repository the menu opens, where you can either search for your folder or scroll down to select it.

## 1.2 Select a File
Clicking on 'select a file' the file can be searched in your directory.
You can choose the following kind of files iso, tar, rpm, jar, zip, bz2, msi, cab, etc.
As soon as you have uploaded the file, the name is shown next to the box.


## 1.3 Descriptions
Optionally any description can be added to the file.

## 1.4 Apply global decisions
You can apply decisions of other scans, which are marked as global, to your upload. Please check if these decisions meet your quality expectations.

![image](https://github.com/fossology/fossology/assets/9692764/72c8008f-fa1e-43be-a1eb-962ff95fb0e2)

## 1.5 Ignore SCM Files and files with a particular Mime-Type

SCM files are git, svn, tfs. Specific Mime-types can be configured from Admin-Customize-Skip

![image](https://github.com/fossology/fossology/assets/9692764/6e874574-e0ba-43b1-a815-e0e7b48ed69c)

## 1.6 Visibility
The visibility of your upload can be chosen. Either it is just the actual group which is just chosen, or 'all groups' where you have access to or 'all groups'.

![image](https://github.com/fossology/fossology/assets/9692764/203efb26-7f8f-4f38-ba3c-fa565ffd8168)

## 1.7 Optional Analysis

![image](https://github.com/fossology/fossology/assets/9692764/745003a0-bb1a-4fef-826c-127fab89448d)

* Bucket Analysis
> Buckets are methods to classify or group license data.
* Copyright/Email/URL/Author Analysis
> Scanning for all text fragments which can be relevant to copyright laws.
* ECC Analysis
> Scanning for text fragments potentially relevant for export control
* IPRA Analysis
> Scanning for test fragments potentially relevant for patent issues
* Keyword Analysis
> Scanning for keywords, which are entered in addition
* Mime-type Analysis
> Determines the mimetype of every file, which can be used to ignore specific file types.
* Monk License Analysis
> Scanning for licenses by text comparison
* Nomos License Analysis
> Scanning for Licenses using regular expressions
* Ojo License Analysis
> Scanning for licenses using SPDX-License-Identifier
* Package Analysis
> Parsing package headers for files ex. if files are rpm package listed, display their package information
* REUSE.Software Analysis
> ReSo agent marks licensed files with a license found in the .license files (outside of the licensed files).
* Software Heritage Analysis 
> Get file information from Software Heritage A significant amount of source code has already been ingested in the Software Heritage archive.

## 1.8 Automated Concluded License Decider
To support automation the auto deciders can be chosen, but only for the files they apply for. Be aware that the decisions can be wrong according to very specific license conditions in the files.


![image](https://github.com/fossology/fossology/assets/9692764/e83c164a-11a4-4cd1-974b-b6417dbb6876)

* If the all results of the Monk and the Nomos agent match
* if Ojos or REUSE.Software findings do not contradict with other findings
* Bulk phrases from reused package match **(please see reuse and bulk functionality)**
* New scanner results, i.e., In case of new license findings by scanners add 'work in progress' decision.

## 1.9 Reuse of existing uploads
This functionality can be used optionally if you have uploaded and cleared an earlier version of the package already.
All previous decisions on licenses, copyrights etc. can be applied, if the files are the same in the new version of the package.

![image](https://github.com/fossology/fossology/assets/9692764/2a139881-1f77-4718-a63b-3328a17ce7a2)


* Check the box 'select an already uploaded package for reuse in a specific folder.
A repository can be searched and selected, in which the package is located.
* Enhanced Reuse
This option can be slow, since a diff tool compares all files of the previous version with the actual version. As long if the difference is not bigger than 1 line, all decisions will be applied to the new version.
* Main License
Will apply only the main license of the previous version of the package, if there is one.
* Reuse Report Configuration Settings
All information from the conf page will be copied, if there are any.
* Reuse deactivated copyrights
All deactivated copyrights from the previous version will be applied.
* Upload to Reuse
Finally the actual package to be compared with must be chosen

## 1.10 ScanCode Toolkit
ScanCode is integrated as a scanner in FOSSology and can be optionally be chosen.
ScanCode provides a database with License, Copyrights, Emails and URLs. 
A full comparison is made between this ScanCode database and the package the user has uploaded.
Please choose with which information in ScanCode shall be compared to.

![image](https://github.com/fossology/fossology/assets/9692764/1c2a63dc-20b4-4868-ade8-9a50c06e268f)

Big Uploads can take a while to be uploaded, depending on the size of the package.

# 2. Upload from Server
Use this functionality if you want to upload more than one file or a whole folder
The difference to **1. Upload File** is just the selection of the files.

![image](https://github.com/fossology/fossology/assets/9692764/01cdc7ad-d006-41ec-a0f7-6674119fd50d)

# 3. Upload from URL
Use this functionality to upload from a URL. Beside choosing the upload path, all other options are the same like **'1. Upload File'**


![image](https://github.com/fossology/fossology/assets/9692764/d32df64e-d247-4546-91d1-9f68e775a19b)

* Enter the URL, where you want to upload a file or directory from
* Enter a descriptive name. If no name is provided the file or directory name will be chosen.

Optionally you can set:
* Enter a comma-separated list of file name suffixes or patterns to accept.
**Example**
* Enter a comma-separated list of file name suffixes or patterns to reject.
 **Example**
* Enter maximum recursion depth 
inf or 0 for infinite
**Example**

# 4. Upload from Version Control System
There can be packages uploaded from Git or any other configured version control System (where to configure?)


![image](https://github.com/fossology/fossology/assets/9692764/6f66e34b-5309-409c-a413-474112818d26)


* Choose the version control system
* Enter the URL or repo
Use either HTTPS:// or HTTP:// If HTTPS:// fails, try HTTP://
* Enter Git Branch name
* Enter Username (if relevant)
* Enter Password (if relevant)
* Enter descriptive name for the upload
If no name is provided the name of the file or directory is chosen.

# 5. Import FOSSology Dump
A FOSSology Dump can be imported from another system or an old version of your system.

![image](https://github.com/fossology/fossology/assets/9692764/c5721880-3f81-4527-84ff-bcae99abb081)

* Select the folder that contains the FOSSology upload.
* Select the upload you want to import
* Select the dump report file you want to upload (**???**)
* Select the who should be the owner of the uploaded decisions.
Any User can be chosen.

# 6. Import Report
![image](https://github.com/fossology/fossology/assets/9692764/15deb25a-6f49-4c17-a17c-a47b95d20425)

# 7. One-Shot Copyright/Email/URL
A single file can be scanned in real time for Copyright/Email/URL Analysis. Binaries are not unpacked. The result of this analysis is not stored!

![image](https://github.com/fossology/fossology/assets/9692764/3dd7109f-fb6f-438a-8f54-9b0a08256dd6)

# 8. One-Shot Monk Analysis
A single file can be scanned for licenses in real time. The result is not stored and binaries are not unpacked. 

![image](https://github.com/fossology/fossology/assets/9692764/74d7f919-43c7-4c6b-a085-213d12ca0ca2)


# 9 One-Shot Nomos Analysis
A single file can be scanned for licenses in real time. The result is not stored and binaries are not unpacked. 

![image](https://github.com/fossology/fossology/assets/9692764/02be6c27-93af-4883-8f01-a0396bf8f156)


# 10 Information about uploaded Files

All information about uploaded files can be found in the 'Info' Folder when working on a component.

![Info](https://github.com/fossology/fossology/assets/9692764/4701e1ba-db17-417d-90e8-72b6286ec2f9)

In the section 'Sightings' you can find identical packages on your instance. It is useful to check, if clearings are already conducted.