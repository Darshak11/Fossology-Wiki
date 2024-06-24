Welcome to the main page for all GSoC 2022 related information.

**Current Status:** [The fossology project has been selected for GSoC 2022 program](https://summerofcode.withgoogle.com/programs/2022/organizations/fossology).

## Intro

We from the fossology project would like to apply for GSOC. Please see two main resources for finding out more FOSSology in general:

* https://www.fossology.org
* https://github.com/fossology/fossology/wiki

Meetings: Checkout the [Meetings table](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#gsoc-2022-meetings-table)

## Interested in Application? - Getting Grip

If you are interested in an application - great! We encourage your application. So the question is how to get started with the topic, just a few points:

* Check https://www.fossology.org and these Github pages https://github.com/fossology/fossology/wiki
* Maybe check some initial intro at https://github.com/fossology/fossology/wiki/New-at-FOSSology%2C-You-Could-...
    * https://www.fossology.org/get-started/basic-workflow/
    * https://www.fossology.org/get-started/basic-training/
    * https://fossology.github.io/
* Try to install fossology, either using vagrant or docker
  + Check out our YouTube video for installation from source: https://youtu.be/q12KwmPYZG4
* Read the proposed topics
* Use the mailing list fossology-devel@fossology.org or contact proposed mentors for further steps
* [Slack invite link](https://join.slack.com/t/fossology/shared_invite/enQtNzI0OTEzMTk0MjYzLTYyZWQxNDc0N2JiZGU2YmI3YmI1NjE4NDVjOGYxMTVjNGY3Y2MzZmM1OGZmMWI5NTRjMzJlNjExZGU2N2I5NGY)
* [GitHub discussion](https://github.com/fossology/fossology/discussions/2140)
* If you are interested in trying to make contributions, see out issues with the label [good first issue](https://github.com/fossology/fossology/contribute). Maybe you could sort out the workflow and make a first pull request.

## Examples from past programs

In 2020, we were awarded seven slots, please see here what was the result of it:

* Ayush and Kaushlendra's work on the [Atarashi](https://github.com/fossology/atarashi) license scanner and [Nirjas](https://github.com/fossology/Nirjas)
    - https://github.com/hastagAB/GSoC-2020
    - https://github.com/Kaushl2208/GSoC-2020
* Darshan's work on Dashboard: https://github.com/darshank15/GSoC_2020_FOSSOlogy/wiki

Also - very much fun - There are some YouTube videos created:
- Ayush made a youtube video / interview style of his experience: https://youtu.be/C8f_etew-yc
- Hypnos invited Darshan for an interview: https://youtu.be/_KbQ83JK7Q0

In 2021, the GSOC program awarded the fossology project with 7 slots. It was a lot bigger and a lot of fun for 2021, a dedicated page has been set up. Please see the GOSC works at https://fossology.github.io/gsoc/
<br />From this page you can can get also an idea about the work being carried out: check the weekly reporting, [for example for the UI project](https://fossology.github.io/gsoc/docs/2021/ui/).

## Mentors

Interested in becoming a mentor? Please reach out to us!

#### Proposals so far:

* [Shruti Agarwal](https://github.com/Shruti3004) for FOSSologyUI
* [Kaushlendra Pratap](https://github.com/Kaushl2208)
* [Anupam Ghosh](https://github.com/ag4ums)
* [Gaurav Mishra](https://github.com/GMishx)
* [Ayush Bhardwaj](https://github.com/hastagAB)
* [Shaheem Azmal M MD](https://github.com/shaheemazmalmmd)
* [Nicolas Toussaint](https://github.com/NicolasToussaint)
* [Avinal Kumar](https://github.com/avinal)
* [Vasudev Maduri](https://github.com/vasudevmaduri)
* [Vivek Kumar](https://github.com/viv9k)
* [Sahil Jha](https://github.com/sjha2048)

## Topic Proposals

Please edit this wiki/reach out to us to add more proposals for GSoC 2022.

Currently discussion happening on https://github.com/fossology/fossology/discussions/2140

## Topic Proposals from 2022

1. [SPDX naming updates and reporting](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#spdx-naming-updates-and-reporting)
1. [REST API and UI improvements](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#rest-api-and-ui-improvements)
1. [Integrating Open Source Review Toolkit](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#Integrating-Open-Source-Review-Toolkit)
1. [Adopting REUSE standards in FOSSology](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#Adopting-REUSE-standards-in-FOSSology)
1. [Improving FOSSology CI scanner image](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#Improving-FOSSology-CI-scanner-image)
1. [Enhancement with ClearlyDefined.io (spasht)](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#enhancement-with-clearlydefinedio-spasht)
1. [Compatibility for PHP-8](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#Compatibility-for-PHP-8)
1. [Introduce concept of project in FOSSology](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#Introduce-concept-of-project-in-FOSSology)
1. [Improve Minerva OSS Dataset and implement models for Atarashi](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#Improve-Minerva-OSS-Dataset-and-implement-models-for-Atarashi)
1. [Overhauling scheduler design](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#Overhauling-scheduler-design)
1. [Debian packaging for Debian repository](https://github.com/fossology/fossology/wiki/Google-Summer-of-Code-Proposals-2022#Debian-packaging-for-Debian-repository)

### SPDX naming updates and reporting

**Goal:** Update SPDX license names and support for report formats

1. Updating SPDX license names to new naming convention. [Resource](https://spdx.dev/ids/)
2. Fixing issues with SPDX RDF (see notes bellow).
3. Other SPDX format reports, five file formats possible:
  * Tag/value (.spdx)
    * Exists
  * JSON(.spdx.json)
    * Can be implemented
  * YAML(.spdx.yml)
    * Can be implemented
  * RDF/xml(spdx.rdf)
    * Exists
  * Spreadsheets (.xls)
    * Need to understand if helpful
    * https://github.com/fossology/fossology/issues/1379

**References:**
* See https://github.com/fossology/fossology/pull/2133 for sample implementation of simple formats
* See https://github.com/spdx/spdx-spec/tree/development/v2.2.2/examples
* Related comments are available on discussion https://github.com/fossology/fossology/discussions/2140#discussioncomment-1939857

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | *** |
| Risk/Exploratory | ** |
| Fun/Periphial | ** |
| Core Development | *** |
| Project Infrastructure | *** |
| Possible mentors | Gaurav, Shaheem, Michael |
| Project size | 175 hour |
| Preferred contributor | Student |

### Notes from SPDX DocFest:
* File types are sometime OTHER vs SOURCE
* Originator/Supplier missing
* Download Location is NOASSERTION
* Package verification code is wrong. Should be all the source files
  * https://spdx.github.io/spdx-spec/package-information/#79-package-verification-code-field
* Filename should start with './' https://spdx.github.io/spdx-spec/package-information/#74-package-file-name-field
* Should rename file name as per https://spdx.github.io/spdx-spec/conformance/#44-standard-data-format-requirements

### REST API and UI improvements

**Goal:** Bringing new [FOSSologyUI](https://github.com/fossology/FOSSologyUI) towards completion

1. Continue work on React repo.
  - Bring in new features.
  - New design patterns.
2. Improve REST API and expose more endpoints
  - https://github.com/fossology/fossology/issues?q=is%3Aissue+is%3Aopen+REST
  - https://github.com/Shruti3004/FOSSology-REST-API/issues

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | - |
| Risk/Exploratory | * |
| Fun/Periphial | *** |
| Core Development | ** |
| Project Infrastructure | *** |
| Possible mentors | Shruti, Shaheem, Sahil, Vivek |
| Project size | 350 hour |
| Preferred contributor | Student/Professional |

### Integrating Open Source Review Toolkit

**Goal:** Using ORT to fetch dependencies and generate SBOM

Build systems fetch the required dependencies (library/artifact) for a project while building the project. Its important to get an insight of these dependencies for license compliance check.

The [OSS Review Toolkit](https://github.com/oss-review-toolkit/ort) is an open source project helps to find dependencies in a project.

The goal of this project is to render the project dependencies created by ort and display those in the fossology-UI. Dependencies can be scheduled directly from the UI and scan with fossology.

Alternative: [oss-review-toolkit/ort#2694](https://github.com/oss-review-toolkit/ort/issues/2694)

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | - |
| Risk/Exploratory | - |
| Fun/Periphial | ** |
| Core Development | *** |
| Project Infrastructure | * |
| Possible mentors | Gaurav, Shaheem, Avinal, Michael |
| Project size | 350 hour |
| Preferred contributor | Student/Professional |

### Adopting REUSE standards in FOSSology

**Goal:** Adopting [REUSE.software specs](https://reuse.software/spec/) in FOSSology codebase

Copyright and licensing is difficult, especially when reusing software from different projects that are released under various different licenses. REUSE make it easier for you to declare the licenses under which your works are released, but they also make it easier for a computer to understand how your project is licensed. This specification defines a standardized method for declaring copyright and licensing for software projects. REUSE also helps in creating a bill of materials with just one simple command.

FOSSology currently uses old methods of defining licenses on source files which can lead to some ambiguity. Following the REUSE specs, the code base of FOSSology should be updated with new licensing format.

**Note:** On its own, the project is very small for being a GSoC project. We can club it with other tasks, like working on [issue #1592](https://github.com/fossology/fossology/issues/1592)

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | ** |
| Risk/Exploratory | * |
| Fun/Periphial | * |
| Core Development | * |
| Project Infrastructure | *** |
| Possible mentors | Gaurav, Michael, Nicolas |
| Project size | 175 hour |
| Preferred contributor | Student |

### Improving FOSSology CI scanner image

**Goal:** Enhancing current scanner image with new reports and features

As a fun project, FOSSology started combining scanners in a simple and small Docker image which can be run on CI providers. The image is currently capable of understanding build environment (GitLab/GitHub Actions/Travis) and use their API's to fetch diff of a branch or scan the complete repo. The capabilities of image include license scanning with Nomos and ojo scanners, copyright and keyword scanning with respective scanners. The image makes use of a Python script to perform all the tasks.

1. The script, however, currently prints report in text format on console and generate the same as an artifact. It can be improved by generating reports in other formats like SPDX reports. See [their Python API](https://github.com/spdx/tools-python).
2. The integration with GitHub Actions can be improved by reporting line number where a license violation is found.
3. Allowing user to provide a different list of Keywords for scanning (currently stored at `/usr/local/share/fossology/keyword/agent/keyword.conf`).
4. Improving on [whitelist format](https://github.com/fossology/fossology/wiki/FOSSology-scanners-in-CI#explanation) with feature to provide it from other sources, currently it is read from a file which is expected to be in the root of repo being scanned.
5. Create a server backed image
    - There will be a server running on a remote machine.
    - The CI script will push the package to the server for scan with auto conclusion.
    - The package will become a version of a project.
    - Downloads the report and make it available as an artifact.
    - If there are unidentified licenses left, provide a link for manual review.
    - This can be extended to integrate with ticket management systems like Jira and redmine.

**Resources:**
- Current documenation: https://gitlab.com/GMishx/fossology/-/merge_requests
- Sample outputs: https://gitlab.com/GMishx/fossology/-/merge_requests
- Sample implementaiton for GHA: https://github.com/GMishx/fossology-scan

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | - |
| Risk/Exploratory | ** |
| Fun/Periphial | *** |
| Core Development | ** |
| Project Infrastructure | *** |
| Possible mentors | Gaurav, Anupam |
| Project size | 350 hour |
| Preferred contributor | Student/Professional |

### Enhancement with ClearlyDefined.io (spasht)

**Goal:** Contribute compliance metadata back to ClearlyDefined.io and community

Clearly defined is a project for collecting metadata about published software. This metadata shall help, among other things, for achieving OSS license compliance. More info can be found at:
- Docs -- https://docs.clearlydefined.io
- GitHub -- https://github.com/clearlydefined/clearlydefined
- API Docs -- https://api.clearlydefined.io/api-docs/#/curations/patch_curations
- Discord -- http://discord.gg/wEzHJku
- Twitter -- http://twitter.com/clearlydefd

The spasht agent is already pulling the data from ClearlyDefined, following enhancements are required:
- Fetch the main license of the package.
- What to do if package does not exist on ClearlyDefined.io
- Push the curated data back to ClearlyDefined.io
  - Current understanding: Send a patch request to `PATCH /curations` and in response, there will be a GitHub `prNumber` and `url`
  - ```JSON
    {
      "contributionInfo": {
        "summary": "title (100 char)",
        "details": "What's the problem",
        "resolution": "What's fixed and how",
        "type": "missing/incorrect/incomplete/ambiguous/other",
        "removeDefinitions": false
      },
      "patches": [
        {
          "coordinates": {"type": "composer", "provider": "packagist",
            "namespace": "athome", "name": "odtphp", "revision": "1.5"},
          "revisions": {
            "1.5": {
              "files": [
                {
                  "path": "Listeur-odtphp-9f31202/library/zip/pclzip/pclzip.lib.php",
                  "license": "LGPL-2.1-or-later",
                  "attributions": [
                    "123123"
                  ]
                }
              ]
            }
          }
        }
      ]
    }
    ```

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | ** |
| Risk/Exploratory | * |
| Fun/Periphial | ** |
| Core Development | ** |
| Project Infrastructure | * |
| Possible mentors | Gaurav, Kaushlendra |
| Project size | 175 hour |
| Preferred contributor | Student/Professional |

### Compatibility for PHP-8

**Goal:** FOSSology should be compatible with the PHP-8 version

1. Syntax compatibility for PHP-8
2. Backward compatibility with PHP-7.2.24
3. Omit all the deprecated features.
4. Migrating views from plain PHP to Twig.
5. Introduction to OPcache or other compatible caching mechanism
6. FOSSology should run on top of PHP8

**References**
* See https://github.com/fossology/fossology/pull/1925 for sample implementation
* See https://github.com/fossology/fossology/pull/2107 for new dependencies

**Docs:**
* PHP Migration Docs: https://www.php.net/manual/en/migration80.php
* Twig Docs: https://twig.symfony.com/doc/3.x/

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | * |
| Risk/Exploratory | ** |
| Fun/Periphial | * |
| Core Development | *** |
| Project Infrastructure | *** |
| Possible mentors | Shaheem, Kaushlendra, Avinal |
| Project size | 175 hour |
| Preferred contributor | Student |

**Good to have:** Improving the MVC architecture of Fossology using Symfony
Symfony as of now is used purely for dependency injection but it can do a lot more. Introducing the capabilities and making the architecture more stable is a good extension to the project.

### Introduce concept of project in FOSSology

**Goal:** Gather uploads under identified _projects_

Originally described in [#1738](https://github.com/fossology/fossology/issues/1738)
A project would be defined by:
- a project ID (as primary key)
- a project name
- a root folder in Fossology
- one or more Group IDs and associated access.
- a URL / ID / Free field to link the project to an external tool

This could be used, for example:
- to gather multiple uploads under the same umbrella,
  - and make bulk changes changes to all uploads / sub-directories that belong to a given project
  - reuse (cleared) findings from previous scan of same Project (or same component)
- to associate a link to a ticketing system or project management solution
- to produce metrics with Work-In-Progress dashboard

In terms of UI integration:
- Add an optional selection of project for new uploads
- Add pages to list, edit, delete projects (in Organize or Admin menu)
- Display the project name in the "Folder Navigation" window, and in the yellow band

Other extensions:
- inside Projects, create _Components_
  - have a proper name
  - are versioned
- leverage the use of [Fossology tags ](https://github.com/fossology/fossology/wiki/Tagging)

Practical use example:
- I have a new project FooBar
- This project is composed of 3 components: _Front-end_, _Back-end_ and _Mobile application_
- I want uploads to be stored in folders `projects/FooBar/Front-end`, ...
- I want to be able to give permissions for _all_ Folders and Uploads for that Project
- I want to automatically reuse findings from previous scans of same components

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | * |
| Risk/Exploratory | ** |
| Fun/Periphial | * |
| Core Development | *** |
| Project Infrastructure | * |
| Possible mentors | Nicolas, Anupam |
| Project size | 175 hour |
| Preferred contributor | Student |

### Improve Minerva OSS Dataset and implement models for Atarashi

**Goal:** To implement a semantic text model for finding out OSS license similarity with best accuracy

OSS Dataset Repository: [Minerva Dataset Generation](https://github.com/fossology/Minerva-Dataset-Generation);
Atarashi Repository: [FOSSology/Atarashi](https://github.com/fossology/atarashi)

In [GSoC 2021 @FOSSology](https://fossology.github.io/gsoc/docs/2021/) we have created our initial OSS License Dataset "[Minerva Dataset Generation](https://github.com/fossology/Minerva-Dataset-Generation)" which can be used to build Machine Learning models for license detection in [Atarashi](https://github.com/fossology/atarashi). We are now planning to try out few machine learning models to be trained on our dataset for the use case of Atarashi (OSS License Detection). As the open source license texts differ by very few tokens only which changes the meaning of the text. Semantic Similarity models might be the good place to try but we are open to discuss more about any other models that can fit our use case perfectly.

#### Tasks:
* Improve [Minerva Dataset Generation](https://github.com/fossology/Minerva-Dataset-Generation) for more accurate license files
* Research and suggest various ML/DL models to be implemented for [Atarashi](https://github.com/fossology/atarashi) (open for discussion)
* Implement the best model discussed for [Atarashi](https://github.com/fossology/atarashi)
* Improve the performance

| Category | Rating |
| :-- | :-- |
| Low Hanging Fruit | ** |
| Risk/Exploratory | * |
| Fun/Periphial | *** |
| Core Development | ** |
| Project Infrastructure | * |
| Possible mentors | Anupam, Ayush, Kaushlendra, Vasudev |
| Project size | 175 hour |
| Preferred contributor | Student/Professional |

### Overhauling scheduler design

**Goal:** Improving FOSSology scheduler or replacing with OTS solution

The existing scheduler design is causing new issues which need to be addressed. Moreover, existing scheduler design is not touched in years.

**Concerning points**
1. The scheduler is written in C which makes it next to impossible to find cause of a failure.
2. The C language does not support exception handling out of the box. It makes code less readable and prone to errors.
3. The linear queue design causes issue when there should be only one instance of an agent running for an upload, but overall the agent is not mutually exclusive.
    > For example, if the monkbulk has a limit set to 1, it should be implied for only single upload. But with linear queue, this monkbulk job will block all other agents from executing even when they are not effected by the results of monkbulk.
    >
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
| Possible mentors | Gaurav, Anupam, Michael |
| Project size | 350 hour |
| Preferred contributor | Professional |

### Debian packaging for Debian repository

**Goal:** Improve Debian packaging and make it acceptable for APT

The existing effort to put FOSSology under Debian packaging list needs to be taken forward. A repository under Debian Salsa was setup initially but not maintained any more: https://salsa.debian.org/fossology-team/fossology<br />
It is configured to use [gbp](https://honk.sigxcpu.org/piki/projects/git-buildpackage/).

**Blockers**

1. The Debian building mechanism does not allow installation from sources other than apt. The Composer packages need to be packed as Debian packages and shipped with FOSSology.
2. Packaging and shipping other tools needs to satisfy their licensing terms.
3. The versions of packages in APT and actual versions used are different.
4. APT also provides JS libraries like JQuery and DataTables but RHL does not.

**See also**
* https://github.com/fossology/fossology/pull/2075
* Good example: https://salsa.debian.org/debian/reuse
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
| Possible mentors | Gaurav, Michael |
| Project size | 175 hour |
| Preferred contributor | Student/Professional |

# GSOC 2022 Meetings Table

To coordinate work, we have had regular meetings for the different topics open for the community. For example for 2022, find all the GSoC calls sorted on topics. Keeping the meetings open for everyone to join.

| Topic(s) | Timings | Meeting link | ICS |
| :--- | :--- | :---: | :--- |
| General Meeting | *Thursdays* 12:30 - 13:30 UTC | [Microsoft Teams](https://teams.microsoft.com/l/meetup-join/19%3ameeting_MTAwZTUyMWYtNDNiNy00MTIyLWFlYWItZWMwNDA5YjYxMzgw%40thread.v2/0?context=%7b%22Tid%22%3a%2238ae3bcd-9579-4fd4-adda-b42e1495d55a%22%2c%22Oid%22%3a%227f1979f2-e3e3-40d0-8a77-bcef842abf7e%22%7d) | [.ics](https://fossology.github.io/gsoc/assets/files/gsoc_2022_weekly-cd50a5e3cb034ba946c900016258fb87.ics) |
| - | - | - | - |
| Atarashi - Minerva | *Wednesdays* 04:30 - 05:00 UTC | [Microsoft Teams](https://teams.microsoft.com/l/meetup-join/19%3ameeting_NmE4ZWVkZjktZTI1NS00YzQyLWE1YTMtMjUxMDkyODVmZTg0%40thread.v2/0?context=%7b%22Tid%22%3a%2238ae3bcd-9579-4fd4-adda-b42e1495d55a%22%2c%22Oid%22%3a%22a897f79c-71f3-4e34-a964-67183e5a6731%22%7d) | [.ics](https://fossology.github.io/gsoc/assets/files/gsoc_2022_atarashi-108e673f48d64c63100f2c18029aad86.ics) |
| REUSE project | *Tuesdays* 12:00 - 12:30 UTC | [Microsoft Teams](https://teams.microsoft.com/l/meetup-join/19%3ameeting_ZWQyNjRlMmUtMzljNS00OWJlLThiNmEtYmRlM2IwNjRmMDI2%40thread.v2/0?context=%7b%22Tid%22%3a%2238ae3bcd-9579-4fd4-adda-b42e1495d55a%22%2c%22Oid%22%3a%22a2c4f566-cad3-46d5-9146-26004cf4bc7c%22%7d) | [.ics](https://fossology.github.io/gsoc/assets/files/gsoc_2022_reuse-bca23d35bbae63e79cf26905a63b221d.ics) |
| React UI | *Tuesdays* 14:30 - 15:30 UTC | [Microsoft Teams](https://teams.microsoft.com/l/meetup-join/19%3ameeting_ZDYzM2M0ZWEtMDE1MC00ZGM0LTk1MGUtNWYxYTNjNzQ1OWRk%40thread.v2/0?context=%7b%22Tid%22%3a%2238ae3bcd-9579-4fd4-adda-b42e1495d55a%22%2c%22Oid%22%3a%227f1979f2-e3e3-40d0-8a77-bcef842abf7e%22%7d) | [.ics](https://fossology.github.io/gsoc/assets/files/gsoc_2022_ui-d90bca4bc8befce72563349223589308.ics) |
| Spasht | - | - | - |
| Concept of project | *Thursdays* 09:00 - 09:30 UTC | [Microsoft Teams](https://teams.microsoft.com/l/meetup-join/19%3ameeting_MWE4YTRlMDEtODc4Yi00NjY4LWIzNGYtM2ViYWNmMDU3ZDVl%40thread.v2/0?context=%7b%22Tid%22%3a%2238ae3bcd-9579-4fd4-adda-b42e1495d55a%22%2c%22Oid%22%3a%22a2c4f566-cad3-46d5-9146-26004cf4bc7c%22%7d) | [.ics](https://fossology.github.io/gsoc/assets/files/gsoc_2022_project-d0c3e6d8b9e7466343af8099296f6abe.ics) |