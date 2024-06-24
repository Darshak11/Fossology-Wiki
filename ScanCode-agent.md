# Introduction

The ScanCode agent was added to FOSSology under the GSoC 2021 as a wrapper on ScanCode toolkit from nexB.

Currently, the agent only provides license findings which end-up in the reports. The agent also captures copyrights and emails but they are stored only in the database and displayed for reference and are not used in any reports.

Checkout the documentation of agent created during GSoC 2021: https://fossology.github.io/gsoc/docs/2021/scancode/
Checkout ScanCode toolkit: https://scancode-toolkit.readthedocs.io/

### Installation

The ScanCode wrapper interacts with ScanCode toolkit on it's CLI interface. To use the agent in FOSSology, ScanCode needs to be installed on the system from [PyPi using pip](https://pypi.org/project/scancode-toolkit/).

To ease the installation of agent, all the installation steps required are automated using the postinstall script. The script (which is [essential step during source install](https://github.com/fossology/fossology/wiki/Install-from-Source#4-run-the-postinstall-script)) can be called from following location:
```shell
sudo /usr/local/lib/fossology/fo-postinstall
```

During the installation, the script will install following packages:
1. `python3` <- installed from APT
2. `python3-pip` <- installed from APT
3. `python3-dev` <- installed from APT
4. `setuptools` <- installed from pip
5. `wheel` <- installed from pip
6. `scancode-toolkit` <- installed from pip

All the python dependencies are installed under fossy user's home directory (typically `/home/fossy/`) in a directory called `pythondeps`.
It is done to keep dependencies from `scancode-toolkit` separate from system installed packages.
Therefore, before running the agent, the wrapper should set the `PYTHONPATH` to `$HOME/pythondeps`.

### Usage
The ScanCode agent can be scheduled as any other agent from the upload page or agent scheduler.
While uploading a file, agent can be selected under the section of scan selection.

![image](https://user-images.githubusercontent.com/18077542/195003295-729033df-ea14-4401-a41b-217d981aec95.png)

The ScanCode scanner is an advanced tool and can generate multiple useful information about a file.
However, we limit the results to only following options:
1. License
    - Scan each file and fetch license information.
    - Missing licenses will be added to the database by the agent.
    - The matching lines from license scanning will be highlighted in the UI.
2. Copyright
    - Scan copyright statements in each file.
    - Results will be displayed under "Copyright" section -> "ScanCode findings" tab.
3. Email
    - Scan each file for emails.
    - Results will be displayed under "Email/URL/Author" section -> "ScanCode" tab.
4. URL
    - Scan each file for URLs.
    - Results will be displayed under "Email/URL/Author" section -> "ScanCode" tab.

### Caveats
The ScanCode toolkit itself is designed to scan the complete project at once. It is generally done by providing a source folder containing all files. Because FOSSology stores files in the file system in a different way, it cannot be processed like the ScanCode toolkit expects.

FOSSology scans the upload by scanning one file at a time with the ScanCode toolkit. Therefore, the bootstraping time of the agent which is expected for the whole project gets accumulated for each file in the project. Because of that, an upload with huge number of files will need a very long time to be scanned. Better plan running this agent with a large component when the system is not busy. A general evaluation of scan times can be checked in the following comment: https://github.com/fossology/fossology/pull/2074#issuecomment-902057799

There are efforts to streamline the process and improving the scan times.

### Reports
All the license findings from the ScanCode agent are included in the reports generated by FOSSology.