
# 1. Folder
Folders must be managed in this section, and cannot be created in context windows.

_Can everybody manage folder???_

## 1.1 Create Folder

A good folder strategy is helpful, for example per clearing team, per component name or the whole organization.

![image](https://github.com/fossology/fossology/assets/9692764/2e7aec87-ad5c-447a-9be5-cec83d07e6f9)

## 1.2 Delete Folders

![image](https://github.com/fossology/fossology/assets/9692764/61e37ed6-1537-4953-9f24-b1a9b159c70c)

## 1.3 Edit Properties

Actually only the name and the description can be changed.

![image](https://github.com/fossology/fossology/assets/9692764/2df5f20e-47f1-4a25-b20f-b5a8a84f7247)

## 1.4 Move or Copy

Either components or whole folders can be copied or moved to another folder. In case of reorganizing or when having uploaded in the wrong folder this is very helpful.

![image](https://github.com/fossology/fossology/assets/9692764/fbf24ef3-a439-4599-ba52-1ec70f0cb4b4)

1. Search for the uload or the folder (here zlib)
2. Select the folder you want to copy or move to (here training)
3. Copy or move


## 1.5 Unlink Content

_tbd.???_

# 2. Licenses

If licenses are not know to your FOSSology instance, new licenses can be created, which are called 'Candidate Licenses'.
Candidate licenses can be created by anybody who found a new license, but should be reviewed by Legal, to enter the risk level in a correct way.
As soon as Candidate Licenses are created, they can be used in the specific group of the creater.
Please make sure, that also the obligations are added to the license (see admin section).

In the Candidate License View the licenses are listed with their SPDX ID, Short Name, Fullname and the license text and if available the URL link.


To edit an existing candidate license, click on the edit button on the left side.

![candidate-licenses](https://github.com/fossology/fossology/assets/9692764/facf152c-4bd4-45b3-b833-07e9785a5810)

To create a new license click the button 'New License' on the bottom of the page.

![candidate-new](https://github.com/fossology/fossology/assets/9692764/c6c8c571-2522-4468-989a-cd3199ee0388)

The edit and create license page look the same:

![image](https://github.com/fossology/fossology/assets/9692764/a91277f6-599a-4336-a8f6-e8cf0c5d7993)

Information to be added:
* SPDX-ID: Please check the SPDX Specification of the SPDX - Linux Foundation Project (https://spdx.dev/) for entering a correct SPDX License ID.
* Short Name: Please refer to your internal specifications for a short name. This can also be the SPDX-ID
* Fullname: Enter the full name of the license
* Reference Text: Please enter the full text of the license
* URL: If availabel enter the URL of the license
* Public Notes: If available enter your notes on the license here
* Risk Level: There are 6 risk levels (0-5).
  * 0: no risk and no obligation_???_
  * 1: no risk, but standard obligation _??_
  * 2: 
  * 3: 
  * 4: high risk
  * 5: do not use
* Merge request: Check Merge request, if the license shall be merged to the general license pool and shall be a standard license in the future. This must be reviewed by Legal. As long as the candidate license is not merged, they can be used in the group of the creator. 
* Save the new are edited license


# 3. Upload

## 3.1 Delete uploaded File

![image](https://github.com/fossology/fossology/assets/9692764/12a9d554-2e5b-4d7e-84a0-0ffd3bcb1823)


## 3.2 Edit Properties

Name and Description of the upload can be edited.

![image](https://github.com/fossology/fossology/assets/9692764/fe3ca02d-1b50-43fc-a644-8f418e99a72e)


## 3.3 Move or copy upload or folder

It is helpful to be able to move or copy an uploaded file in another folder, or even move or copy a whole folder in another folder. Sometimes uploads are not done correctly. 

![image](https://github.com/fossology/fossology/assets/9692764/d15e09b5-1793-4d22-8e2e-4e4762e94dde)

1. Search on the left side for the folder, which contains the folder or upload you wish to move or copy (here 'Apache')
2. Select the folder or upload you wish to move or copy (here 'lucene')
3. Select the folder where the content should be moved or copied to (here 'test')
4. Click on Move or Copy


