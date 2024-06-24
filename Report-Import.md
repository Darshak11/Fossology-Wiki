## Report Import

Report import page allows user to copy the findings from rdf file to FOSSology upload.

![screenShot65](https://user-images.githubusercontent.com/10155976/195320752-9b380d28-b05c-4e29-88cf-43068af29f3d.PNG)

With reference to above screenshot.

1. Select a folder that contains upload you wish to import decisions.
2. Select a upload.
3. Choose a .rdf file.
4. One can import the new licenses from .rdf report using two options

Select the option based on your needs.

   * Create new license as
     * candidate licenses.
     * new license.



   * Import license information as findings
     * SPDX tag of type licenseInfoInFile -> this option copies all the scanner findings.
     * SPDX tag of type licenseConcluded -> this option copies all the user decisions.


   * Checked by default "Add concluded licenses as decisions" -> enables user to add licenses as clearing decision.
     * also overwrite existing decisions
     * import as "to be discussed"

Check if you would like to copy the copyrights.

   * Add the copyright information as textfindings -> all the copyrights from .rdf report gets added as user findings.

Now click on upload and import to start processing.
 