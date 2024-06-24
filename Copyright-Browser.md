# 1 Overview

This agent finds statements within code that could indicate ownership of the copyright. This obviously includes a standard copyright statement, but can also include statements beginning with "written by" or "maintained by." This agent also finds emails and urls embedding in source code, since these can also indicate the ownership of the code.

In this view you can select and adpapt the **Copyrights** of a package.

![Copyright](https://github.com/fossology/fossology/assets/9692764/d56e32db-4a95-4153-bb66-a0aa8b010ff2)

1. Name of the package folder structure you are working in.

2. Folders of the findings of different Scanners
The results can differ. Usually FOSSology finds all Copyrights, but also presents some false positives. SCanCode has less false positive, but could perhaps miss a finding. 

* FOSSology Findings 
* ScanCode Findings (if you have chosen to run the ScanCode Agent)
* User Findings **??**

3. Count: Number of occurrences of the specific Finding.

4. FOSSology Finding (or other agent Finding): the specific text phrase of the finding is shown. It is possible that the text is not exactly the Copyright, then this must be cleaned up.

5. 1. Search Field: Enter the phrase you are looking for. When checking the bos **Inverse Search** everything is shown, beside the text you have entered.

5. 2 In the column with the red **X** you can deactive a single copyright finding.

6. Checkbox to mark several copyright findings, to apply further functionality on them.

7. Folder Structure of the package

# 2. Deciding on the Copyright Findings

### 2.1 Deactivate a single Finding, by clicking on the red **X**

![image](https://github.com/fossology/fossology/assets/9692764/657031b2-9394-4976-a0f5-58331c7fe7fa)

Immediately it will be shown as deactivated. If you click **Undo** the decision will be reversed.
As soon as you refresh the page, the entries will be moved down to the **Deactivated Finding Statements**.

### 2.2 Deactivate several Copyright Statements at once

Click the Check boxes on the right side of the Finding, or even check all on the top of the page.
This way you work with it depends on the findings. Sometimes the page consists mainly of false positives, then it makes sense to choose all and deselect the real copyrights afterwords.

![image](https://github.com/fossology/fossology/assets/9692764/1bc3fbd3-d48d-422a-8704-e03a63ee4f2a)

Click **Deactivate Selected Rows** to delete the entries. After renewing the page, they will be moved to the **Deselected Finding** Section.

### 2.3 Cleanup of the Copyright Text

Sometimes there are characters in the Copyright Text, wich are not part of the Copyright Statement

* Cleanup of a single text

Click on the Copyright statement and delete the text, which does not belong to the statement.

![image](https://github.com/fossology/fossology/assets/9692764/0c3bb13f-f9ce-438a-968d-a4aa38ebc6b1)

### 2.4 History

All deselected Copyrights can be found on the bottom of the page.
In case you want to activate them again, please check the lines you want to activate and check 'Undo selected rows'.

![copyright-undo](https://github.com/fossology/fossology/assets/9692764/fa033c2f-b2c0-4b36-857e-f7f43396f714)


# 3. Advanced Search and Replace or Deactivate

A large number of Copyright findings can be processed at once with the 'Advanced Search'.

**Example**
In this package many Copyright of Mark Adler are found, but some of them need to be cleaned up. So we use this function to cleanup the copyrights.

Search for **Adler**

All Findings are selected in the check box.
![advanced search](https://github.com/fossology/fossology/assets/9692764/f268afad-5dca-4f52-bc1a-c6e1db7572ee)

Enter the text with Wildcards (*), to keep or be deleted.


In this example 
Copyright: this is the start of the copyright statement here
(*): Wildcard for all the different years of the copyrights and also the partner Jean-loup Gailly
Mark Adler: the name of the copyright holder
(*): another Wildcard for all characters after the name

Click on **Create Replacement Text**

![image](https://github.com/fossology/fossology/assets/9692764/87d5b705-4a1c-408d-9937-b1c720055113)

Delete the Placeholders $X which shall be deleted.

Please check the result with **Test Replacement**, because the whole change cannot be managed later on this page.

![test replacement](https://github.com/fossology/fossology/assets/9692764/dfd543b7-1dd5-4e4d-aa04-ec51b548cf93)

If everything looks good, click on 'replace selected rows' or 'deactivate selected rows'.

Result of the action:
![image](https://github.com/fossology/fossology/assets/9692764/d915c3d8-9665-4547-bb18-8c552fd5d066)

# 4. Copyright Agent doesn't find a specific copyright?

If the copyright agent isn't finding a copyright that you know is present in a file, there are a couple simple changes that can be made to the dictionaries to cause it to find your copyright.

**Change copyright.dic**

This is the best choice if the copyright agent is missing an entire class of copyrights. If there is some word that whenever it is seen, the agent should look for a name match nearby then simply add it to this file. Run a "make install" on the directory and restart the scheduler. Then run the copyright agent on the files again. See [[Useful SQL]] for a method to delete the results for a particular upload.

**Change names.dic**

This is the best choice when there is a specific person that you are looking for. If you know that a piece of code has an author, but the copyright agent is unable to find any statements relating them, add that name to the names.dic file. As with changes to the copyright.dic file, simply run a "make install" and restart the scheduler. Then run the copyright agent on the files again. See [[Useful SQL]] for a method to delete the results for a particular upload.




