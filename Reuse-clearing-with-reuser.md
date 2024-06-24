# Introduction
FOSSology allows reusing clearing decisions from a reused package/upload. This is done by the agent called "Reuser". The agent is capable to bring license clearing decisions, copyright decisions, [[Conf Page]] settings and main license from the previously cleared package.

### 1. Working

#### Copying license clearing decisions
The reuser agent compares the file tree of reused and current package to find same files. It uses the file checksums of files to match the file and understand which files from reused package are in current package. This behavior can be modified using the "Enhanced reuse" configuration explained bellow. Once a match is found, the agent will copy the clearing decisions from reused package to current package.

#### Copyright decisions
The reuser agent matches the copyright text's checksum between the reused and current package. If there are matches found between the versions, and if the copyright was deactivated in reused package, it will be deactivated in current package as well.

However, if the copyright content was modified, the text checksum will change and thus a match cannot be established anymore.

#### Report configuration setting
The reuser agent copies all of the [Unified report settings](https://github.com/fossology/fossology/wiki/Conf-Page#1-unified-report-settings) stored in the [[Conf page]] from reused package to current package.

#### Main license
If the main license(s) of the reused package will be copied as main license(s) of current package.

### 2. Scheduling
The reuser agent can be scheduled while uploading a package or using the Schedule agent page.

**Note:** License clearing decisions are added based on user's current group. So make sure you are in the correct intended group before scheduling the agent.

![Reuse agent scheduling](https://user-images.githubusercontent.com/18077542/195279080-e0140f7f-c8e8-48d1-878f-8ea299aa6dc2.png)

While using Schedule agent page to schedule the reuser agent, it can be found in the "Select additional analysis" section as "Reuse of License Clearing" which **must be** selected first and configured from the "reuser:" section.

![Reuse agent conf](https://user-images.githubusercontent.com/18077542/195278782-93815ba5-76b1-4a30-a47b-069fc4176acc.png)

The configuration section can be found as referenced above while uploading a package.

### 3. Configuration

![Reuse agent conf](https://user-images.githubusercontent.com/18077542/195278782-93815ba5-76b1-4a30-a47b-069fc4176acc.png)

The reuser agent provides following configurations:
1. Select an already uploaded package for reuse in specific folder
    - To schedule the agent, this option **must be** selected and it enables the drop-down to select the folders on right.
    - As mentioned earlier, the clearing decisions are stored associated with groups. Thus the group names appear next to folder names in `()`.
    - The group name next to folder name selects the group to fetch the clearing decisions from.
2. Enhanced reuse (slower)
    - Between versions, most files do not change but have small changes in like 1 or 2 lines.
    - When checked, this option will not limiting the file matching based on file checksum only, but get the number lines changed in files where names match.
    - If  files having same name in reused and current package have less than 5 lines changed, the decision will be copied.
3. Reuse main license/s
    - Reuse the main license(s) used in the reused package as main license(s) of current package.
4. Reuse report configuration settings
    - Reuse the configurations saved in [[Conf Page]] from reused package to current package.
5. Reuse deactivated copyrights
    - Check deactivated copyrights from reused package and deactivate them in current package.
    - The match of copyrights depends on text checksum.
    - In case the copyright was edited or there is any difference in agent's match, the copyrights cannot be identified as same.
6. Upload to reuse
    - Selecting the upload to reuse the clearing decisions from.
    - The uploads are listed from the folder selection in option 1 above.

### Caveats
1. As noted above, the copyright decision reuse is little bit fiddly and might not work for all situations.
2. While using the "Enhanced reuse" option, the agent uses Linux tools [diff](https://www.gnu.org/software/diffutils/) and [wc](https://www.gnu.org/software/coreutils/manual/html_node/wc-invocation.html#wc-invocation) to compare files which share same name in reused and current package. The `diff` tool operations to find difference in files is a compute heavy operation on its own. As the permutation and combination of files sharing same name can be big, running `diff` tool for each pair is going to increase the run time of agent. Better plan scheduling this agent with "Enhanced reuse" option on a large component when the system is not busy.