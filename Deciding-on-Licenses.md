This is the core of license compliance. The different agents scan the source code based on stored text phrases. To understand more details check the explanation of the different agents. _to be linked_

These license findings must be checked, perhaps adapted and approved.

## 1 Review a license in a file

![edit-file](https://github.com/fossology/fossology/assets/9692764/3b900229-aade-4df0-a97d-648622bc83b3)


Please check, which files are still open (red) and click on the file name.

## 2 Overview of the 'Change Concluded License' Page

![conclude-license](https://github.com/fossology/fossology/assets/9692764/c09c14ea-c1c9-4f3e-968e-8aa555253db1)

1. File in the folder structure
2. On the screen on bottom in the middle you find the legend. Sometimes it pretty big. This you can close with the button 'hide legend'.
3. Here you can see the source code text and highlighted the text which was found by the agents (in different colors - please look at the legend to understand the different colors.
4. Deciding and going to the next file
* Submit: apply the license decision
* To through all files: goes file by file through the folders, no matter if there are licenses found or not.
* Go through all files with licenses: jumps to the next file with a license, found by the agents, no matter if it is concluded already or not.
* Go through all files without license and no clearing result: jumps to the next file with a license, found by the agents, but no conclusion of a license.
5. If a file occurs more often in the component, the decision of one file can be applied also for the other files. But please check if this can really applied for the other files with the same name.
6. Clearing Decision Type
* no license known: apply if there is no license in the file
* to be discussed: if there are open questions to be discussed
* irrelevant: sometimes license findings are irrelevant in the context of the file. Then mark them as irrelevant
* identified: if all licenses are decided on (in Section 7) check identified
* do not use: if there is a license found which cannot used in the context of the project, please check 'do not use'
* non functional: It can be decided by the license compliance team to mark non functional files, which are not relevant in the specific use case and do not need a license decision.
7. License Finding (of the different agents) : more details in the process of license conclusion)
* Action: fields to decide on the license finding 
* License: shows the licenses which are found by the different agents
* Source: the name of the agent who found the license
* License Text: shows the text of the license, if there is a text available in the scanner
* Acknowledgement: shows available acknowledgements per license or acknowledgements can be added.
* Comments: Comments can be added to document the conlcusions
8. User Decision: can be concluded indivdually
9. Bulk Recognition: a specific text phrase can be conclude for many licenses (in the tree, the component or for all components)
10. Clearing History: Shows the whole clearing history for the file

## 3. Process to conclude a License

### 3.1. Open a file in your component on the 'Change Concluded License' Page (see above)

### 3.2. Main License
1. It is always good to find out the main license, for example in a Readme file or in publicly available information.

**Example: ** ZLIB
A Readme file is available:

![edit-file-2](https://github.com/fossology/fossology/assets/9692764/7afd5d76-0f0c-42f5-b691-b4b79911f952)


2. Check the reference text

If you click on the link behind the different agent findings, they reference text is highlighted in the sourcecode itself.

The monk result is only 98 % because there is an additional character in the source code:

![edit-file-3](https://github.com/fossology/fossology/assets/9692764/da46e215-88cd-4512-b940-378737d9055d)


### 3.3. Conclude a single license

Based on the result it is clear, that the main license is the zlib license.
Click on the star next to the license, mark 'identified license' and submit or click on the '>' next to the submit button, to continue with the next file.

![edit-file-4](https://github.com/fossology/fossology/assets/9692764/bbfae349-c202-4d86-aea1-1813cebc01a0)

The star next to the license, makes this license the main license for the component.

## 4. Change found license

![file-edit-5](https://github.com/fossology/fossology/assets/9692764/353f8505-cdea-4a6e-a52e-657c2dabd1ae)


In this file a reference text is mentioned in zlib.h. Please check this file. In this case also the zlib license is mentioned.

### 4.1. The zlib reference must be deleted with the red 'X':

![delete-license](https://github.com/fossology/fossology/assets/9692764/3d26244f-c8ed-42d4-a4e9-bbdd2bf211e3)

After deselecting the license, the symbol changes to a green '+' in case you want to add the license again.

### 4.2. Add the correct license (here zlib license)

![add-license](https://github.com/fossology/fossology/assets/9692764/dcd3688c-1b02-416d-abde-cb8e0f317893)


Click on 'User Decision' and search for the correct license. Press the green '+' to add the license and close the window.

![image](https://github.com/fossology/fossology/assets/9692764/f7d636e1-4e5b-498b-965f-2a03a27fe9ec)

Now 2 licenses are visible, one selected (as a user decision) the other deselected.

## 5. Bulk Scan

If you want to add or/and delete a license for more files at once the Bulk Scan can be used.

![Bulk](https://github.com/fossology/fossology/assets/9692764/34e2e522-c015-4008-aef4-0073d8a2cb2b)


Mark the relevant text, this can be also a part of the reference text, found by the agent. 

**Attention:** It is very important to reference to a text part which is really clearly referring to a specific license information and which also available in other files.

Click on 'Bulk Recognition'

If there are characters of comment symbols check 'Clean text' button.

![bulk-clean](https://github.com/fossology/fossology/assets/9692764/5538fb55-02bc-45d9-88ed-7baf7167ceb6)

*** Remove a license:**

zlib-possibility must be deselected with the red '-'.

![image](https://github.com/fossology/fossology/assets/9692764/3367fbfa-812f-48a9-8977-b316c31e6866)

*** Add a license**

zlib license must be added. 

  * Click on the License field
  * Search for the license
  * Add it with the green '+'.

**Result:**

![bulk-license-management](https://github.com/fossology/fossology/assets/9692764/e09f5693-fe63-4623-99c3-9c79cc471071)


In the box you see the added and removed licenses. 

To undo these selections, click on the red '-' on the right side of the table.

More Options:

![image](https://github.com/fossology/fossology/assets/9692764/5a75091d-6f9e-40c3-8378-707f9b49d75b)

* Scope of the bulk: 
  * Scan the whole upload
  * Scan only current folder (sometimes the text reference is only valid in the current folder, e.g. with included dependencies which have another license.
* Ignore Conflicts: If there are other bulk scans, which refer to another license, this shall be ignored.
* Scan files with findings: not all files are scanned, but only the ones with agent findings.
* Ignore irrelevant files: all files which are marked as irrelevant are ignored
* Custom delimiters (???? to be explained)

Click on 'Schedule Bulk Scan' and the bulk job will be started.

![image](https://github.com/fossology/fossology/assets/9692764/5bfebd07-625a-45bb-9b32-677f809e11ed)

The job number is shown on the bottom, so that you can follow the status.

![image](https://github.com/fossology/fossology/assets/9692764/0fb53203-e68b-4ad0-8cc6-7d0ff0813d96)

When the job is done, the result will be shown on the screen (after refreshing).

The correct licenses are chosen and the bulk history is visible:

![image](https://github.com/fossology/fossology/assets/9692764/a0f92a17-9a59-4667-976f-55c0f2e60557)

You can check also in the License Browser Overview the overall result in your component:

![image](https://github.com/fossology/fossology/assets/9692764/14232a74-147f-4c08-b838-2ec72bf79c9e)

## 6. Individual License Texts

OSS License texts or permission notices are usually standardized, but there are also individual license texts, which are not predefined in your system.

**Example:** 

* Here is a specific permission notice, which is not captured in the system. 
* The MIT-CMU-style license is not relevant and must be deleted.
* The Permission Notice can be used. 
* Both licenses have no license text.

Copy the whole text of the permission notice.

Anyhow the license text must be added here, so click on the 'Click to add' Button.

![add license text](https://github.com/fossology/fossology/assets/9692764/e08e54e4-6ca1-4679-b4c8-27d937ce33b7)


* Add the text in the field. If the field is to small, open it on the right bottom corner.
* Use the 'Clean Text' Button to delete comment characters.
* Press 'OK'

![license-text-add](https://github.com/fossology/fossology/assets/9692764/935e0093-d9f1-4f0f-ae4d-b93531c9ebdd)


The License Text is appearing in the overview:

![image](https://github.com/fossology/fossology/assets/9692764/26ff3076-92da-4c7e-a761-3b72e8177ed3)

In the same way individual acknowledgements and comments can be added.

For acknowledgements please refer to _(to be linked)_


* 7. Add Acknowledgements

*** 7.1 Acknowledge for Apache License

Some Licenses need to have specific acknowledgements in the Readme.OSS (the file with all license compliance information).
This is for example the Apache-2.0 license, which wants to have the content of the notice file added as an acknowledgement.

![notice-file](https://github.com/fossology/fossology/assets/9692764/d2d93a70-5d18-49cb-aab2-0e82ff539185)

* Click on Acknowledgement
* In case of Apache-2.0 click on 'Select from Notice File'. 

The content of the Notice file of the specific component will be selected and shown in the window. Click on 'use this' and cancel the appearance of the screen. 

![Uploading notice-content.png…]()

The content of the notice file is added to the 'Enter Content' field and can be edited here. 
In this example the reference text to the license requirement should be deleted.

![image](https://github.com/fossology/fossology/assets/9692764/b01cbca4-a06e-448a-9351-6f63c855e249)

In the 'Change concluded licenses view' the content of the notice file can be seen in the 'Acknowledgememt' field. If wanted a comment can also be added. This will not be printed in the Readme.OSS.

![ackn-comment](https://github.com/fossology/fossology/assets/9692764/aa82ab08-829b-47e0-9018-3541440ced6d)

*** 7.3 Any other Acknowledgement

There are also other acknowledgements required, for example for using Dual or Triple Licenses.
Here you have to indicate, what options are given and which one you choose.

* Acknowledgements can just be entered in the field.
* Acknowledgements can be chosen from a list of acknowledgements you have created before:

![image](https://github.com/fossology/fossology/assets/9692764/5466efd7-c810-4c56-9470-7b718929052d)

*** 7.3. Manage Acknowledgement

??? Where???



 

