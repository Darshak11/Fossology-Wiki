# Browse View

![Browse View](https://github.com/fossology/fossology/assets/9692764/ed11339c-770b-4333-8073-02d9a85a6716)

0. You see all folders and all uploads in this view, dependant on your user and the group.

1. This is the overall folder structure. If you choose the root structure, you see all uploads, where you have access within your group.
   If you choose a folder without having the rights you will not see any content.
   All folder can be collapsed or expanded.
   
2. In this column the upload can be searched by name and will be displayed in the column.

3.  Different actions can be performed for the upload:
    * File Browser: jumps to the File Browser view (link)
    * View: Shows the upload file itself
    * Conf: jumps to the configuration folder (link)
    * Info: jumps to the Info folder (link)
    * Compare: jumps to the File Picker to compare 2 uploads _(to be described)_
    * Copyright/Email jumps to the Copyright/Email/URL/author folder
    * Delete: deletes the upload
    * Download: downloads the upload
    * Export CLIXML: exports a CLIXML file with all clearing information (CLI- Component License Information)
    * Export CSV Report (SPDX): exports a csv report with the SPDX structure _(tbc)_
    * Export CycloneDX Report: export all license information in a CycloneDX structure
    * Export DEP5 Report: exports all license information in a DEP5 format (_tbd)_
    * Export FOSSology Dump: exports all information as a dump _(which format, what is the content?)_
    * Export ReadMe_OSS: Exports a Readme.OSS File with all license clearing information _(which format?)_
    * Export SPDX RDF report: Exports all License clearing information in an SPDX RDF format
    * Export SPDX tag - value report: _???_
    * Export Unified Report: Exports all license information as an Word Document
    * Import FOSSology Dump: a dump of another FOSSology instance or an older dump can be uploaded here _(why to do it here?)_
    * Import Report: _what kind of report?_
    * Licenses: _Set the concluded licenses for this upload ???_
    * Tag: _Tag files are containers???_
    * History: jumps to the job results of the upload of this package

4. The status of the license clearing can be added and also searched for:
    * Open (standard)
    * In progress
    * Closed
    * Rejected
   The status changed must be managed manually.

5. Comment must be added when changing the status

6. The main license is added in the view, if any is chosen.

7. Upload date and time is set automatically

8. A person (email address) can be assigned to the upload. It is also possible to search for the assigned person. 

9. Different reports can be generated for a specific package (when clicking the checkbox) or for the whole upload:
    * CLIXML Generation: generates a CLI file with all clearing results
    * CycloneDX Generation: generates a CycloneDX file with all clearing results
    * ReadmeOSS_Generation: Generates a Readme file (example) 
    * SPDX2 Generation: Generates a SPDX2 File (example)
   All file creations generate jobs.

When clicking on the Package Name the License View for this package opens.


