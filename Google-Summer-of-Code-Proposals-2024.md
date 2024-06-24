Welcome to the main page for all GSoC-2024 related information.

## Intro

We from the fossology project would like to apply for GSoC-2024. Please see two main
resources for finding out more FOSSology in general:

- https://www.fossology.org
- https://fossology.github.io/gsoc/

Meetings: Checkout the [Meetings table](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2024#gsoc-2024-meetings-table)

## Interested in Application? - Getting Grip

If you are interested in an application - great! We encourage your application. So the question is how to get started with the topic, just a few points:

- Check https://www.fossology.org and these Github pages https://github.com/fossology/fossology/wiki
- Maybe check some initial intro at https://github.com/fossology/fossology/wiki/New-at-FOSSology%2C-You-Could-...
  - https://www.fossology.org/get-started/basic-workflow/
  - https://www.fossology.org/get-started/basic-training/
  - https://fossology.github.io/
- Try to install fossology, either using vagrant or docker
  - ~~Check out our YouTube video for installation from source: https://youtu.be/q12KwmPYZG4 (Outdated)~~
- Read the proposed topics
- Use the mailing list fossology-devel@fossology.org or contact proposed mentors for further steps
- [Slack invite link](https://join.slack.com/t/fossology/shared_invite/enQtNzI0OTEzMTk0MjYzLTYyZWQxNDc0N2JiZGU2YmI3YmI1NjE4NDVjOGYxMTVjNGY3Y2MzZmM1OGZmMWI5NTRjMzJlNjExZGU2N2I5NGY)
- [GitHub discussion](https://github.com/fossology/fossology/discussions/2663)
- If you are interested in trying to make contributions, see out issues with the label [good first issue](https://github.com/fossology/fossology/contribute). Maybe you could sort out the workflow and make a first pull request.

## Examples from past programs

In 2020, we were awarded seven slots, please see here what was the result of it:

- Ayush and Kaushlendra's work on the [Atarashi](https://github.com/fossology/atarashi) license scanner and [Nirjas](https://github.com/fossology/Nirjas)
  - https://github.com/hastagAB/GSoC-2020
  - https://github.com/Kaushl2208/GSoC-2020
- Darshan's work on Dashboard: https://github.com/darshank15/GSoC_2020_FOSSOlogy/wiki

Also - very much fun - There are some YouTube videos created:

- Ayush made a YouTube video / interview style of his experience: https://youtu.be/C8f_etew-yc
- Hypnos invited Darshan for an interview: https://youtu.be/_KbQ83JK7Q0

In 2021, the GSoC program awarded the fossology project with 7 slots. It was a lot bigger and a lot of fun for 2021, a dedicated page has been set up. Please see the GSoC works [here](../2021/index.md).

From this page you can also get an idea about the work being carried out: check the weekly reporting, [for example for the UI project](../2021/ui).

You can check out our GSoC 2022 projects with 8 slots. The dedicated page can be found [here](../2022/index.md).

You can check out our GSoC 2023 projects with 5 slots. The dedicated page can be found [here](https://fossology.github.io/gsoc/docs/2023)

## Mentors

Interested in becoming a mentor? Please reach out to us!

#### Proposals so far:

- [Anupam Ghosh](https://github.com/ag4ums)
- [Avinal Kumar](https://github.com/avinal)
- [Ayush Bhardwaj](https://github.com/hastagAB)
- [Gaurav Mishra](https://github.com/GMishx)
- [Kaushlendra Pratap](https://github.com/Kaushl2208)
- [Shaheem Azmal M MD](https://github.com/shaheemazmalmmd)
- [Vivek Kumar](https://github.com/viv9k)
- Katharina Ettinger
- [Sahil Jha](https://github.com/sjha2048)

## Topic Proposals

Please reach out to us to add more proposals for GSoC-2024.

Currently, discussion happening on https://github.com/fossology/fossology/discussions/2663

## Topic Proposals from 2024

1. [Improving FOSSology CI scanner image](#Improving-FOSSology-CI-scanner-image)
2. [SPDX license expression support](SPDX-license-expression-support)
3. [Overhauling scheduler design](Overhauling-scheduler-design)
4. [Debian packaging for Debian repository](Debian-packaging-for-Debian-repository)
5. [REST API improvements](REST-API-improvements)
6. [New Artificial Intelligence based copyright and license scanner agent](New-Artificial-Intelligence-based-copyright-and-license-scanner-agent)
7. [Support SPDX 3.0 reports](Support-SPDX-3.0-reports)
8. [Support text phrases and bulk phrases scanning for MONK agent](Support-text-phrases-and-bulk-phrases-scanning-for-MONK-agent)


### Improving FOSSology CI scanner image

**Goal:**: Enhancing current scanner image with new reports and features
As a fun project, FOSSology started combining scanners in a simple and small Docker image which can be run on CI providers. The image is currently capable of understanding build environment (GitLab/GitHub Actions/Travis) and use their API's to fetch diff of a branch or scan the complete repo. The capabilities of image include license scanning with Nomos and ojo scanners, copyright and keyword scanning with respective scanners. The image makes use of a Python script to perform all the tasks.

1. The integration with GitHub Actions can be improved by reporting line number where a license violation is found.
2. Allowing user to provide a different list of Keywords for scanning (currently stored at `/usr/local/share/fossology/keyword/agent/keyword.conf`).
3. Improving on [whitelist format](https://github.com/fossology/fossology/wiki/FOSSology-scanners-in-CI#explanation) with feature to provide it from other sources, currently it is read from a file which is expected to be in the root of repo being scanned.
4. Ability to download a dependency for scan (path provided at pipeline trigger).

Additionally, the JSON output of nomos needs to be enhanced providing highlight and line information in the output.

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | - |
| Risk/Exploratory | ** |
| Fun/Periphial | *** |
| Core Development | ** |
| Project Infrastructure | *** |
| Project size | Large |
| Preferred contributor | Student/Professional |
| Skills needed | Docker, Python |

### SPDX license expression support
**Goal**: Support SPDX license expression detection and reporting
1. Support SPDX license expressions in FOSSology such as `MIT AND (GPL-2.0-only OR BSD-2-Clause)`.
2. Differentiate SPDX licenses with exceptions. FOSSology currently stores license exceptions as licenses.
3. Scanning SPDX Expressions with ojo as step 1.
4. UI components to create and see license expressions in file clearing page.
5. Updating reports to export the expressions correctly.

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | - |
| Risk/Exploratory | ** |
| Fun/Periphial | *** |
| Core Development | *** |
| Project Infrastructure | *** |
| Project size | Large |
| Preferred contributor | - |
| Skills needed | PHP, C/C++ |

###  Overhauling scheduler design

**Goal**: Improving FOSSology scheduler or replacing with OTS solution
The existing scheduler design is causing new issues which need to be addressed. Moreover, existing scheduler design is not touched in years.

**Concerning points**
1. The scheduler is written in C which makes it next to impossible to find cause of a failure.
2. The C language does not support exception handling out of the box. It makes code less readable and prone to errors.
3. The linear queue design causes issue when there should be only one instance of an agent running for an upload, but overall the agent is not mutually exclusive.
    > For example, if the monkbulk has a limit set to 1, it should be implied for only single upload. But with linear queue, this monkbulk job will block all other agents from executing even when they are not effected by the results of monkbulk.
    > This essentially makes the agent mutually exclusive even though, there is a special flag EXCLUSIVE for the very same purpose: https://github.com/fossology/fossology/wiki/Job-Scheduler#agentconfs
  - One idea on redesigning the queue, it can be broken into buckets per upload each maintaining its own priority queue. There can be another queue for global operations like maintenance, delagent, etc.
  - Doing so, each bucket can be traversed in round-robin and pick first pending job and check against host limit. This will eliminate the scenario mentioned in point 3. Also, exclusive agents can be sent to global queue.
    ```
      upload specific queue
    |-<upload_2> -> nomos, copyright, ojo, keyword
    |-<upload_3> -> monkbulk, decider, monkbulk, decider
    |-<upload_4> -> reuser, decider
    
    global queue
    -> delagent,
    ```
4. Since the FOSSology is released, there can be number of new scheduling libraries being released which needs to be explored. They can be a nice addition to the project.

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | - |
| Risk/Exploratory | ** |
| Fun/Periphial | *** |
| Core Development | *** |
| Project Infrastructure | * |
| Project size | Large |
| Preferred contributor | Professional |
| Skills needed | C/C++, Go, any fast language |

### Debian packaging for Debian repository

**Goal**: Improve Debian packaging and make it acceptable for APT

The existing effort to put FOSSology under Debian packaging list needs to be taken forward. A repository under Debian Salsa was setup initially but not maintained any more: https://salsa.debian.org/fossology-team/fossology
It is configured to use [gbp](https://honk.sigxcpu.org/piki/projects/git-buildpackage/).

**Blockers**

1. The Debian building mechanism does not allow installation from sources other than apt. The Composer packages need to be packed as Debian packages and shipped with FOSSology.
2. Packaging and shipping other tools needs to satisfy their licensing terms.
3. The versions of packages in APT and actual versions used are different.
4. APT also provides JS libraries like JQuery and DataTables but RHL does not.

**See also**
* https://github.com/fossology/fossology/pull/2075
* https://wiki.debian.org/PackagingWithGit
* https://wiki.debian.org/SimplePackagingTutorial
* https://wiki.debian.org/Diagrams
* https://wiki.debian.org/PHP
* https://peertube.debian.social/videos/watch/0fb2dbc4-f43d-477e-8b14-20c426f970de

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | * |
| Risk/Exploratory | ** |
| Fun/Periphial | *** |
| Core Development | * |
| Project Infrastructure | *** |
| Project size | Small |
| Preferred contributor | Student/Professional |
| Skills needed | Debian, APT, CMake |

### REST API improvements

**Goal**: Completing REST API implementation and migrate to v2
- Writing test cases for all the existing and new functionalities.
- Improve REST API and expose more endpoints
  - Update REST API to v2
  - https://github.com/fossology/fossology/pull/2617
  - https://github.com/fossology/fossology/pull/2633
  - https://github.com/fossology/fossology/pull/2634
  - https://github.com/orgs/fossology/projects/2/views/2

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | ** |
| Risk/Exploratory | * |
| Fun/Periphial | ** |
| Core Development | *** |
| Project Infrastructure | ** |
| Project size | Large |
| Preferred contributor | Student/Professional |
| Skills needed | PHP, Slim framework |

### New Artificial Intelligence based copyright and license scanner agent
**Goal**: Integrate new AI capabilities to improve the scanners

A quick ChatGPT 3.5  test  shows it's pretty good at spotting the correct licenses and expressing them as SPDX expressions.

One idea would be integrate a similar technology into an Fossology agent - however not by relying on external proprietary services but by building a dedicated LLM model based on existing open source solutions.

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | - |
| Risk/Exploratory | *** |
| Fun/Peripheral | *** |
| Core Development | * |
| Project Infrastructure | * |
| Project size | Large |
| Preferred contributor | Student/Professional |

### Support SPDX 3.0 reports
**Goal**: Support reading and generating SPDX 3.0 reports
- Support generation of SPDX 3.0 reports in different formats.
- Start with Core, Software and Licensing profiles. Increase if needed.
- Support generation of SPDX reports in JSON format.
- Support ingestion of SPDX 3.0 reports

Refs:
- https://github.com/spdx/spdx-3-model/
- https://github.com/fossology/fossology/tree/master/src/spdx2
- https://github.com/fossology/fossology/tree/master/src/reportImport

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | ** |
| Risk/Exploratory | ** |
| Fun/Periphial | * |
| Core Development | ** |
| Project Infrastructure | * |
| Project size | Large |
| Preferred contributor | Student/Professional |
| Skills needed | PHP, Twig |


### Support text phrases and bulk phrases scanning for MONK agent

**Goal**: Adding text phrases from UI to database and provide ability to scan them using MONK.

FLOW : Create a UI Where user can add multiple text phrases associated with license. Also user should have a option to choose bulk license text based on users or whole.
<br />Should enable MONK or new Monk like agent to scan from phrases table. also enabling options to add license text acknowledgement and comments from UI. 
<br />Test cases needs to be provided as well.


| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | ** |
| Risk/Exploratory | * |
| Fun/Peripheral | ** |
| Core Development | * |
| Project Infrastructure | ** |
| Project size | Large |
| Preferred contributor | Student/professional |

# GSOC 2024 Meetings Table

To coordinate work, we have had regular meetings for the different topics open for the community.

| Topic(s) | Timings | Meeting link | ICS |
| :--- | :--- | :---: | :--- |
| General Meeting | TBD | TBD |
| - | - | - | - |
| Project 1 | TBD | TBD |