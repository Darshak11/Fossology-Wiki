All functionalities in this section can only be used by a user with admin rights.

# 1. Admin License Acknowledgements

Managing License Acknowledgements in especially useful when dealing with dual or triple licenses.
Also other licenses require acknowledgements.
They can be created in this place and can be chosen in the [License Clearing File View](https://github.com/fossology/fossology/wiki/Deciding-on-Licenses), when deciding on a license.
The acknowledgements are available for all users in all groups.

![image](https://github.com/fossology/fossology/assets/9692764/6fcbc022-ab7e-45ed-b823-a086d88db712)

# 2. Add License

The licenses, which are added here, will be used mainly by the Monk agent or can be chosen manually.

![image](https://github.com/fossology/fossology/assets/9692764/55c1b3bb-3566-46c1-a969-5db9df5a9aa9)

* Active: yes or no, standard is yes. But a license can be deactivated later
* Checked: yes or no, standard is no. Since a correct license is the core of license compliance, there should be a 4 eye validation of an authorized person.
* SPDX-ID: The SPDX specification is an open standard, please check [SPDX Linux foundation project](https://spdx.dev/use/specifications/). Please check if there exists and SPDX-ID for this license already, or create one according to the specifications. 
The SPDX-ID is used in the reports.
* Short Name: This is an internal short name and must be unique.
* Full Name: enter the full name of the license
* License text: copy the full license text here
* Text updatable: yes or no, which shall prevent an update by chance.
* Detector type: defines where the licenses were created or will be used
  * Reference License: will be used mainly by the Monk agent.
  * Nomos: created by Nomos
  * Unconcrete License: created outside the tool
* URL: of the license
* Public Notes: any publicly interesting note
* Conclusion: what will be concluded by the Monk agent
  * self: the license itself
  * instead any other license can be chosen. This makes for example sense with the BSD template licenses. In this case the individual text of the license is kept, but the conclusion is the general BSD license.
* Reported License: in the reports
  * self: the license itself is reported
  * alternatively another license can be chosen (see point above)
* Risk Level: please choose the risk level according to your definitions in the organizations
* Associated Obligations: Please add the predefined obligations to this license

# 3. CSV Export all
Exports all licenses in a CSV file with the following fields:
shortname,fullname,spdx_id,text,parent_shortname,report_shortname,url,notes,source,risk,group,obligations

# 4. CSV Export Marydone (???)

# 5. CSV Import
Import a CSV file, with the specific license informations, without the specific obligations. They must be uploaded in the obligation section.

![image](https://github.com/fossology/fossology/assets/9692764/97d995bb-f596-458c-a215-8d11980cf912)

# 6. Candidates

NOTE: Candidate licenses can be only used in your selected group.

![screenShot54](https://user-images.githubusercontent.com/10155976/195017055-2225f223-9c6d-4135-b487-b2ae131e6e29.PNG)

With reference to above screenshot.

1. Go to organize -> Licenses page in menu to list all the candidate licenses.
2. Click "New License" button to add a new candidate license.

![screenShot55](https://user-images.githubusercontent.com/10155976/195017592-47384b78-e4fd-4b4e-8da0-a5b43fba4499.PNG)

With reference to above screenshot.

1. Add license short-name(new license you wish to add into FOSSology database).
   ```
   ex: GPL-2.0-or-later
   ```
2. Add license full-name
   ```
   ex: GNU General Public License v2.0 or later
   ```
3. Add license Text.
   ```
   ex: GNU GENERAL PUBLIC LICENSE Version 2, June 1991

   Copyright (C) 1989, 1991 Free Software Foundation, Inc.
   51 Franklin Street, Fifth Floor, Boston, MA 02110-1301, USA....
   ```
3. Add license URL(Where this license reference exist) -> not mandatory.
   ```
   ex: https://spdx.org/licenses/preview/GPL-2.0-or-later.html
   ```
4. Add public notes -> not mandatory.
   ```
   ex: This license was released: June 1991. This license identifier refers to the choice to use code under GPL-2.0-or-later.....
   ```
5. Select risk level -> not mandatory.
   ```
   ex: 2 -> green
   ```
6. Check on merge request if you wish to add this license to actual license table. then save.

# 7 License Administration

Here Licenses can be managed and maintained, but not added.

![License-managment](https://github.com/fossology/fossology/assets/9692764/1cd08343-525b-45c4-a5fe-9b928aca7d69)

You can search for license families, like e.g. GPL, when they are managed in your licenses.
Licenses can be checked (reviewed) or not, which can also be chosen in the search.

At a result you get a list of licenses of your chosen license family.

the fields of the list:

* Edit: the licenses can be edited here
* Checked: you see if the licenses are checked or not
* SPDX ID
* Shortname
* Fullname
* Text
* URL
* Obligation topic: Obligations can be linked here

These fields can also be searched individually

# 8 Standard Comments

For licenses 'Standard Comments' can be added. 
This makes sense for example for unspecified licenses, which are concluded automatically.

![License comments](https://github.com/fossology/fossology/assets/9692764/9ef6f2d6-fcb2-449a-9fcb-9f3434538f0e)




