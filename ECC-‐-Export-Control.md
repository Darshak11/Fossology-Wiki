# 1. Introduction

The ECC agent searches for specific expressions in the file, which can be managed in the Agent [Settings](fossology/src/copyright/agent/ecc.conf at master · fossology/fossology (github.com)).

There can be many false positives, depending on the expressions you have set. The results will not appear in the License Clearing Reports.

# 2. Overview of the page

![ECC](https://github.com/fossology/fossology/assets/9692764/c1cffe69-abda-4859-8249-2514240f85dd)

1. Package or Folder you are working in. 

2. Selection which information you want to see
    * Show all
    * Files without a license

3. Folder you are working in. A Folder tree can be seen here, when you work with subfolders

4.1 You can select how many entries you want to see.

4.2 The number of occurrences of a specific expression

5. Export restriction: shows the expressions which were found in the files

6. Searching for specific expressions, or by checking the box, inverse search (all other topics are found, but not the expression, you have mentioned in the search field).

7.1. X for deactivating the finding

7.2 A checkbox to check the finding and use further functionalities on it.

![image](https://github.com/fossology/fossology/assets/9692764/db3aeaf2-0c88-44ca-bf92-04e15f1951ea)

The deactivated ECC restrictions are in the same structure like the findings.

The detailed search will be described in section **_xxx_**

# 3. Decide on ECC Findings

All findings are activated by standard. To deactivate them you have several options.

### Deactivate a single Finding

![image](https://github.com/fossology/fossology/assets/9692764/5050dd92-6a4f-4634-a0b9-269bb0d8bb86)

click on the **X** on the right side of the finding. Immediately the entry will change to **deactivated** with the possibility to undo the decision. By clicking on **undo** the decision will be activated again.
With a refresh of the page, the entries will be moved to the **Deactivated Eport Restriction Statements**.

### Deactivating several findings at once

![ecc-select](https://github.com/fossology/fossology/assets/9692764/58f2a209-3b51-444e-a67a-92777d6343b9)


Click on the check boxes on the right side of the finding, or even mark all by clicking on the check box on the top.

Then choose **Deactivate selected rows** on the bottom of the list.
Refresh the page to update the list.

### Advanced Search
Please look in the Copyright documentation to understand this functionality. Within ECC it is mostly not used.

# 4. Analyzing an ECC Finding

_Comment: Cryptography is relevant to ECC classification. Because if this, the ECC agent searches for cryptographic text phrases._

To analyze the finding in the specific file, please click on the number of the occurrence of the finding.

![image](https://github.com/fossology/fossology/assets/9692764/223325da-2c71-4b2e-93f8-7dd329fbc923)

A structure will open with all the file names with that explizit finding, including the pathes: 

![image](https://github.com/fossology/fossology/assets/9692764/7c65fd38-df1c-4d55-9578-41d1e4f098b3)

Click on the file name.

The Page 'View Export Control and Customs' opens.

![ECC-finding](https://github.com/fossology/fossology/assets/9692764/868f7b51-acd4-4366-a3ed-b7c26b61ef08)

Search for the purple marked text and decide on the finding.

1. Text of the file

2. The Legend (6) can be hidden

3.1 Submit button: when the decision is done, click on this button
3.2 Go through all files: the next file will be shown
3.3 Go through all files with ECC export restriction (to be recommended, when you want to see all details of export restrictions)

4. Issue Type: the possible reactions of to the finding
    * to be discussed: will be marked as to be discussed _**(which color?)**_
    * Irrelevant: is a false positive and not relevant in regard of ECC
    * Identified: is identified as a ECC finding
    * Do not use: is a critical finding and the file should not be used. This will be marked in _**color ???**_
    * Not functional: is not a functional file _**(e.g. test folder, example folder)**_

5. More information about the finding
    * Description: The page is the same like for details on copyright statements and so on. So please add the kind of finding, here ECC
    * Text finding: add the complete expression of the finding here. Sometimes the finding by the agent is too short, sometimes to long.
    * Comment: add your comment

6. The Legend, which is color coded
    * black: text of the file
    * Finding of the export restriction in the text


