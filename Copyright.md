This agent finds statements within code that could indicate ownership of the copyright. This obviously includes a standard copyright statement, but can also include statements beginning with "written by" or "maintained by." This agent also finds emails and urls embedding in source code, since these can also indicate the ownership of the code.

## General Technical Remarks

* The copyright agent is written in C++, this is easier for handling regular expressions.
* The regular expressions are put into file that parsed at agent startup. Note that agent startup means started by the scheduler service, not when you surf to the FOSSology Web pages.
* File name is ```src/copyright/agent/copyright.conf```
* The regular expressions have been tested with the notorious FSF-copyright statements including really many years and going over up to three lines, check projects like libelf.

In addition, the copyright agent can:

* look for URLs like http, https, ftp
* look for emails

## How does it work?

You can use the copyright agent for two main use cases:

* Review the findings (copyrights, author statements, e-mails, URLs) in the FOSSology Web UI.
    * For example, you could search for contributors from France to identify a bunch of French people, then you could check the top level domain of the found e-mail addresses on screen. See the screenshot as example also using the filter function in the upper left of each table.

![Copyright E-Mail Example](https://raw.githubusercontent.com/wiki/fossology/fossology/img/2015-10-15%2000_16_50-Copyright_Email_URL_Author%20Browser%20.png)

* Edit the copyright statements for generation of a readme-/notice-file for your distribution or a SPDX file (or maybe a Debian copyright file for a package in future). You need to know that the listed copyright statements can either be allowed or blocked:
    * all statements you see will land in a report
    * you must disable statements rows with the red cross to get rid of them
    * or, as an alternative, you can edit or correct copyright statements, by clicking into the respective text line. Please do not forget to enter return to save your edited text.

## Fidelity

Since the copyright agent has changed with 2.6.2, the question rises, how good are the findings. While a complete proof is impossible because this would involve a complete scan of all open source packages. Rather, a qualitative look has been performed at some heterogeneous package, OpenSSL 1.0.2.

The analysis has been done as part of solving ticket
https://github.com/fossology/fossology/issues/352 (please scroll down for spreadsheet attachment)

In summary, the newer implementation offers handling advantages and seems to find slightly more items than the implementation prior to 2.6.2. Moreover, the matched statements seem more complete. Please see the issue description for details.

## Command Line

Copyright can be run from the command line:

```
./copyright -c file1.c -c file2.c 
```

The output is formatted like this:

```
file1.c :: [start_byte:end_byte:statement] 'text of statement' [start_byte:end_byte:url] 'text of url' file2.c :: [start_byte:end_byte:url] 'text of url' [start_byte:end_byte:email] 'text of email'
```

## Copyright Agent Prior to 2.6.2

The copyright agent uses to two dictionaries to determine if a sentence is, or is not a copyright statement. The first dictionary is a list of trigger words and should be very small. The second is a list of words that will be used to validate a statement found using the first dictionary. The second dictionary used by the copyright agent is much larger than the first and mostly contains names. The idea behind this is to find a statement like "copyright (c) 2010 hewlett-packard development company, l.p." by finding the work "copyright" and matching it with one of the other words in the sentence, in this case the agent would match it with "2010" since years are an excellent method for identifying copyrights.

The entirety of the first dictionary used currently by the copyright agent:

```
copyright (c) written modified patched maintained contributed &copy; &#169; &#xa9; author
```

A section of the second dictionary used by the copyright agent:

... hartzel haruko harv harvard harvey harville harvison harwell harwerth harwilll harwood hasan ...

## Copyright Agent doesn't find a specific copyright?

If the copyright agent isn't finding a copyright that you know is present in a file, there are a couple simple changes that can be made to the dictionaries to cause it to find your copyright.

**Change copyright.dic**

This is the best choice if the copyright agent is missing an entire class of copyrights. If there is some word that whenever it is seen, the agent should look for a name match nearby then simply add it to this file. Run a "make install" on the directory and restart the scheduler. Then run the copyright agent on the files again. See [[Useful SQL]] for a method to delete the results for a particular upload.

**Change names.dic**

This is the best choice when there is a specific person that you are looking for. If you know that a piece of code has an author, but the copyright agent is unable to find any statements relating them, add that name to the names.dic file. As with changes to the copyright.dic file, simply run a "make install" and restart the scheduler. Then run the copyright agent on the files again. See [[Useful SQL]] for a method to delete the results for a particular upload.

# Advance search and replace - UI

Once you've uploaded a package and scanned it for Copyright, you might see additional information captured by the agent. Cleaning up this information for each entry is a daunting task. However, FOSSology allows you to select the effected copyrights and replace all of them with a new string.

#### Basic replace

If all rows have similar text, you can replace the text for all rows with following simple steps.
1. Filter rows by using the "Search" bar on top.
2. Select the effected rows you would like to be replaced.
3. Put the new string in "Replace" field.
4. Hit "Replace selected rows"
![Basic replace](https://i.imgur.com/uat91b1.png)

This feature, however, will replace the entire text. What if, you do not want to replace the entire row? For example, the year in all rows might be different. For such scenarios, "Advance Search" comes handy.

#### Advance search and replace

With advance search, you can have some placeholders in your search string. It allows working on rows where they differ only at some places.
Let's take an example from our package and see how this feature can help you speedup your work. We are using [diffutils-3.5](https://ftp.gnu.org/gnu/diffutils/diffutils-3.5.tar.xz) for this example.
![Example copyrights](https://i.imgur.com/EKfpwt6.png)

In this example, valid/clean copyrights will be `Copyright (C) <year> Free Software Foundation, Inc.`. But we can not use "Basic replace" as each row has different year in string. To match such copyrights and remove anything following `, Inc.`, let's see how we can use the "Advance search" feature.
1. We need to filter interesting strings to make our work bit easier.
  - ![Filter](https://i.imgur.com/IXTZfqM.png)
2. Now, we need to fabricate an Advance search string.
  - Since our copyrights follow `Copyright <year> Free Software Foundation, Inc.` syntax, we can make use of placeholder `(*)`
  - The string can be written as `Copyright (*) Free Software Foundation, Inc.`
  - But, the filter matches complete string and will leave rows which have the following characters `, Inc.` which we want to remove. Let's create placeholder for them as well.
  - `Copyright (*) Free Software Foundation, Inc.(*)` <- **Note:** No space before last placeholder.
3. Select rows which needs to be update.
  - You have control to select which rows you want to work with. But if your query is good, you can select all rows at once.
  - ![Select rows to update](https://i.imgur.com/zZKTlpX.png)
4. Put in the "Advance search" string and create replacement text.
  - Put the Advance search string from step 2 in "Advance search" box.
  - Hit "Create replacement text" button. Immediately, the search string will be copied into "Replace" field with every placeholder `(*)` replaced with it's position `$1` and `$2`.
  - Whatever matches in our placeholder, is given a location like `$1` and `$2` which we can play with.
5. Making changes in final replace string and testing it.
  - If we remove the `$2` from "Replace" field, we remove everything from original string which is at our second placeholder `(*)`.
  - Making other changes like replacing `Inc.` with `Incorporated`, the same change will be done in original string.
  - After making changes we like, hitting "Test replacement" will take first row from all selected rows and perform the replace operation. The results will be displayed in a table bellow.
  - Once you are satisfied with the changes, hit "Replace selected rows" to perform the replacement on all selected row.
  - ![Test and replace](https://i.imgur.com/tAvneNu.png)
6. After the operation, the copyrights look much neat.
  - ![Search and replace result](https://i.imgur.com/fXLtuwT.png)

It is advisable to test your replacements first with rows you want to replace and rows you do not want to replace before making final submission.

The placeholders `(*)` will match everything and are equivalent to `(.*)` match group from RegEx. Similarly, the replacement placeholders `$1` are equivalent of `\1` match group number from RegEx.