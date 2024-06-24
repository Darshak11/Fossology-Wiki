# ReSo agent

`ReSo` stands for `REUSE.Software` - a set of recommendations about licensing a project. The standard assumes creating a `.license` file per each licensed file in the sources code. `ReSo` agent marks licensed files with a license found in the `.license` files (outside of the licensed files).

Extract of the specification: https://reuse.software/spec/#comment-headers
> If a file is not a plain text file or does not permit the inclusion of comments, the comment header that declares the file’s Copyright and Licensing Information SHOULD be in an adjacent file of the same name with the additional extension .license (example: cat.jpg.license if the original file is cat.jpg).

**Note:**
> *there are also other assumptions in the REUSE standard, that are not in the scope of the agent for the moment*

## Using the agent
1. User uploads source code with
    - `foobar.jpg` -> an image
    - `foobar.jpg.license` containing:
        ``` # SPDX-FileCopyrightText: 2016, 2018-2019 Jane Doe <jane@example.com>
        # SPDX-FileCopyrightText: 2019 Example Company
        #
        # SPDX-License-Identifier: GPL-3.0-or-later
        ```
2. Select Upload options:
   - Select optional analysis 
       - REUSE.Software Analysis -> will also trigger a scan with Ojo agent
   - Automatic Concluded License Decider, based on
       - ... scanners matches if Ojo or REUSE.Software findings are no contradiction with other findings
2. Ojo agent detects licenses for file `foobar.jpg.license`
3. The ReSo agent detects the link between `foobar.jpg` and `foobar.jpg.license`, and applies the same license to `foobar.jpg`

Note:
- If an agent found a contradictory license for `foobar.jpg`, the decider does not change it, even if `foobar.jpg.license` was found (same behavior os Ojo agent)
- Checking ReSo agent will also trigger Ojo agent, even if it not selected when uploading


## How it works

ReSo agent assumes that the [[Ojo]] agent will detect the SPDX entries in `.license` files
The `reso` agent itself does not perform any scan on the upload content directly. 
It requires `Ojo License Analysis` to be executed before, which results are the data source for the `reso` agent. Therefore `ojo` execution is forced as a dependency agent before `reso`.

For the moment only manual upload with web UI have been tested, however other variants may also work properly. API upload support is yet to be implemented.

## Testing

Developments were tested against this [project example](data/reuse.software-02-v02.tgz)

