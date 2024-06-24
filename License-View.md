# The License View

### File and License View

![browse](https://github.com/fossology/fossology/assets/9692764/889ee414-2226-4f36-9062-b503492a5d8d)

* 1 The User you are logged in with and the chosen group.

* 2 Folder ans subfolders you are currently seeing

* 3 The different Folders in the Browser View, wich are explained in the License Clearing _(to be linked_).

* 4 Different views to be selected, like number of entries, tree view or flat view

* 5 Search field to search files and folders

* 6 Files and Folders, which can be sorted

* 7 Search results of the different scanners. The field can contain several licenses.

* 8 Decisions on the licenses per file or folder. The field can contain several licenses.

* 9 Clearing status of the file and the checkbox to search just files with and clearing status 'open'. 

* 10 Number licenses found in a file or folder. 
  * Cleared: number of files with a license decision
  * Open: number of files without a license decision
  * Total: Number of total files

* 11 Actions to perform clearing decisions based on folder structures. This is described in the license clearing Section (to be linked)

* 12 License View
All licenses which are found by the Scanners are listed here.
They can be searched in the field. 
Table contents:
  * Scanner Count: Number of findings of a specific license
  * Concluded License Count: Number of decisions for a specific license
  * License Name

Below the table you find the sum of all licenses. There can be different pages of licenses, depending how many licenses you chose to show in the table.

![image](https://github.com/fossology/fossology/assets/9692764/4d3ab62b-509e-4be3-9fb3-b47c42ba3826)

* Summary of License Decisions
  * Number of Unique Licenses  in the number of file 
  * Number of Unique Licenses detected by the scanner and number of concluded unique licenses (with decisions).
  * Overall licenses found (also the ones which are found several times) and number of concluded licenses (all concluded licenses count)
  * Files with no detected license (files without any license) and concluded files with no license.

* REUSE Standard report

![image](https://github.com/fossology/fossology/assets/9692764/e4e4a864-c233-453d-93b8-c36537f4a818)

Results of the REUSE agent.**???**

* Scanner Information

![image](https://github.com/fossology/fossology/assets/9692764/89f4402b-2edc-4d09-bc39-ff87e9e73daa)

Information about the Agents wich did run on your package. Here also the Schedulers can be started to run an agent in addition.


# 3. Views

### Tree View
By default, you see the tree view, e.g., all files and directories which are in the browsed path. The results are ordered by the adj2nest agent, hence directories come first and all files follow in alphabetically order. Directories are displayed in bold font. 

![image](https://github.com/fossology/fossology/assets/9692764/34a10cdc-5448-43a7-bcfb-98b9d42845b3)

### Flat View

You can switch to flat view to see all plain files that are anywhere in the browsed path, e.g., also the files in subpaths. The results are sorted alphabetically hiding the nested structure.

![image](https://github.com/fossology/fossology/assets/9692764/f7ede9f0-7852-465c-b351-8c07bc487c5a)

Select the number of entries you want to see.

![image](https://github.com/fossology/fossology/assets/9692764/f1ac0d1f-3734-4fc8-ab82-8592db8d4c21)


Filter by the the conclusion status. To see all files, where the license is not concluded yes, check the **Open** checkbox.

![image](https://github.com/fossology/fossology/assets/9692764/72ee7557-acfd-47d7-8f43-88ee9f145c71)


# 4. Search

### Unqualified search
Enter a string in the search field, so files and directories starting with this string will be visible. 

![image](https://github.com/fossology/fossology/assets/9692764/39b81304-cc3f-491d-a556-e75b56660177)

This is equivalent to a search with the qualifier head, e.g., **head:t** yield the same selection.

![image](https://github.com/fossology/fossology/assets/9692764/274b1b20-6563-4967-a7f1-e62402864ea1)

### Searching for Extensions

You can use the qualifier **ext** to filter for file extensions. Note that the full extension must match, hence "ext:c" won't find class files.

![image](https://github.com/fossology/fossology/assets/9692764/0b5c2d3f-9a02-4956-9b67-8479218d1fcd)


### Sorting of files

please click the sort button on the left side.

![image](https://github.com/fossology/fossology/assets/9692764/2cd0b081-c42e-4a39-b576-1dbc22c310d8)


### Searching by licenses

In the license field on the right side you can click on the license and will see all files with this specific license.

![image](https://github.com/fossology/fossology/assets/9692764/333860c5-ff52-4144-8751-2a92c4c6672c)

The same you can achieve by choosing the specific license in the pulldown menu.
Here you can search for licenses which are found by the scanners (left) or licenses which are concluded already (right).

![image](https://github.com/fossology/fossology/assets/9692764/9e0881c2-b89e-4846-92c3-ed3509074d35)

To see all findings and conclusions, select **filter for edited results**.

![image](https://github.com/fossology/fossology/assets/9692764/ea78d3b7-8391-41b2-8ea0-16733eb46d70)

### Searching a license

In the license search field you can search for example for **GPL** and will see all GPL findings.
You can also sort the license view.

![image](https://github.com/fossology/fossology/assets/9692764/7c74f2cf-ab70-4c9b-93a7-4e59b1c844f2)


