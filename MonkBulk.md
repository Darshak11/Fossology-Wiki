# The Monk bulk scan is a way to conclude licenses based on text snippets contained in a file

The license matches are made if the entered text is matched to 100% (Some tokens like `#`, `//`, `/*`, `dnl`, `'''`, `"""` ... do not need to be matched). 
From these matches, a decision is made if it can be made without conflicts or the 'ignoreConflicts' option is checked.

A typical use case would be to remove a license finding hint like 'See file' and to replace it with the correct license.
The text used for that can just be copied out of the file into the bulk search box. 
If you wish to remove comments you can do it manually, as Monk does ignore them anyway.

We have made 2 Bulk scans already with a copy pasted text snippet on the left
![Before the scan](https://raw.githubusercontent.com/wiki/fossology/fossology/img/Bulk/BulkScan4.png)
To have a clean bulk scan history we have removed the '#' characters at the line start
![Scan again without comment characters](https://raw.githubusercontent.com/wiki/fossology/fossology/img/Bulk/BulkScan5.png)
... and it works just as well
![Result](https://raw.githubusercontent.com/wiki/fossology/fossology/img/Bulk/BulkScan6.png)

### Scheduling the agent

![Bulk dialog](https://user-images.githubusercontent.com/18077542/195315245-024d4d43-4e6b-4958-adae-71c4aca403b9.png)

As referenced in the image above, the Bulk recognition agent can be configured with following options:
1. Selecting the license to add/remove
    - From the drop-down, select the license which needs to be added/removed.
    - Clicking on the **+** will add the license in the table bellow with **Action** as Add.
    - Clicking on the **-** will add the license in the table bellow with **Action** as Remove.
2. Adding License Text/Acknowledgement/Comment
    - For each license added, the license text, acknowledgement and comment can be added by clicking on "Click to add" in respective columns.
    - This is very helpful in modifying the license text in report for multiple files and adding license acknowledgements.
3. Removing license from the operation
    - If a license was added/removed by mistake for the bulk operation, it can be removed by clicking on **-** button on the end of the column.
4. Reference text
    - The text snippet which is to be scanned in files should be added to the "Reference text" field.
    - The content can be copied directly from the file as well.
5. Scan scope
    - The scan scope can be set either to whole upload or to the current folder.
    - This can be helpful for reference text scenarios where license changes based on folder.
6. Ignoring files
    - The first option "Ignore conflicts" force add or remove the license where reference text matches irrespective of the license collision.
    - If the option "Ignore Irrelevant files" is selected (default), do not scan files marked with irrelevant decisions for the reference text.
    - Unchecking the "Ignore Irrelevant files" will scan all the files within the scan scope irrespective of the decisions on them.
7. Custom delimiters
    - Delimiters are single characters which are used to break text into tokens.
    - By default, Bulk uses ` \t\n\r\f#^%,*` as list of delimiters. This list can be modified using the "Custom delimiters" option and adding them to the Delimiters textbox.
    - The delimiters can only be single characters (`xyz` will be treated as 3 delimiters, `x`, `y` and `z`).
    - Special characters like `\t`, `\n`, etc will be treated as single delimiter. (`\r\n\t` will create 3 delimiters `\r`, `\n` and `\t`).
    - Space by default will be used as a delimiter irrespective of it being in the textbox.
8. Clean text
    - The "Clean text" button can be used to remove the delimiter characters from the reference text and replace them with a space.
    - Using the button will not effect the scan from bulk as scanner will drop the delimiters.
    - The button is just for reference, checking the effect of delimiter removal.
    - It is also used as a helper to clean up text for license text in option 2 by users.

Clicking on "Schedule the Bulk scan" will start the scan.

#### Folder level scanning
![Folder bulk](https://user-images.githubusercontent.com/18077542/195316588-8669bd83-aa0a-42dc-848d-1bf5956ed557.png)

The scanner dialog can also be opened by clicking on **[Bulk]** next to a folder. This will open the dialog as in [Scheduling the agent](#scheduling-the-agent), however the scope of the scan will only be limited to the folder.

### Caveats
1. Please note the periods (`.`) is not a default delimiter and will be used in text match.
    - For example, if the text in file is `CC0-1.0 license.`
        - The reference text `CC0-1.0 license` will not match.
        - The reference text `CC0-1.0 license.` will match.
    - For example, if the text in file is `CC0-1.0 license`
        - The reference text `CC0-1.0 license` will match.
        - The reference text `CC0-1.0 license.` will not match.