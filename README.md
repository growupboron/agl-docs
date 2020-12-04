# agl-docs (master)
Revamping and restructuring Automotive Grade Linux's documentation site under GSoD'20.

-> [The working documentation site.](https://agl-docs.readthedocs.io)

-> [ReadTheDocs project page.](https://readthedocs.org/projects/agl-docs/)

## To setup local build environment :

1) Clone this Repository : ```git clone https://github.com/growupboron/agl-docs.git```

2) Change into the directory : ```cd agl-docs/```

3) Install MkDocs and rtd-dropdown theme : ```sudo pip3 install -r requirements.txt```

4) Serve it, it would get defaultly rendered at [127.0.0.1:8000/](127.0.0.1:8000/) : ```sudo mkdocs serve```

# The Linux Foundation - GSoD 2020 Project Report

### Rework the documentation hosting & generation and Restructure getting started pages and developer guides

This report is a requirement of the `Project finalization phase` of [Google Season Of Docs](https://developers.google.com/season-of-docs) program. I [worked](https://developers.google.com/season-of-docs/docs/participants/project-linuxfoundation-boron) with the Linux Foundation, under Automotive Grade Linux on the project to ```Rework the documentation hosting & generation and Restructure getting started pages and developer guides```, the original proposal for the project can be found [here](https://growupboron.github.io/blog/the-linux-foundation-gsod-2020-proposal/).

![logo-gsod,lf,agl](https://i.imgur.com/u78qx6v.png)

[The Linux Foundation](https://www.linuxfoundation.org/) is the nonprofit consortium dedicated to fostering the growth of Linux. [Automotive Grade Linux](https://www.automotivelinux.org/) is an open-source project hosted by The Linux Foundation that is building an open operating system and framework for automotive applications.

## Project Deliverables

The primary aim of the project is to simplify the [existing](https://github.com/automotive-grade-linux) AGL documentation workflow pipeline by reworking the documentation hosting and generation :
1. Develop a single repository setup from the current multiple repository setup to improve the maintainability of the documentation site.
2. Simplify the indexing of the existing markdowns by using directory tree structure instead of maintaining [yml indexes](https://github.com/automotive-grade-linux/docs-webtemplate/tree/master/content/tocs).
3. Migrate the whole setup from the current Jekyll template to MkDocs static site generator which can be hosted at readthedocs which simplifies :
    - [Versioned Documentation](https://docs.readthedocs.io/en/stable/versions.html)
    - [Server Side Searching](https://docs.readthedocs.io/en/stable/server-side-search.html)
    - [Multi Language Support](https://docs.readthedocs.io/en/stable/localization.html) (Can be executed in the future)

    This setup would vastly improve and simplify fetching the markdowns of different releases of AGL from multiple repositories hosted mostly on [gerrit](https://gerrit.automotivelinux.org/) into different branches on a [single documentation repository setup](https://github.com/growupboron/AGL-GSoD-2020-Demo-MkDocs).

4.   Improve the Getting Started page and Developer guides the existing documentation along with writing new documentation into the following clear and bullet-proof structure :
        - **Tutorials:** a lesson that allows the newcomer to get started.
        - **How-to Guides:** a series of steps that show how to solve a specific problem.
        - **Reference:** a technical description describing the appropriate machinery and workflow processes.
        - **Explanation:** discursive explanation explaining code/workflow structure in detail.

- Rewrite the documentation of existing “[How to handle documentation](https://old-docs.automotivelinux.org/docs/en/icefish/howto/)” to the proposed setup and with the aim of making it beginner and developer-friendly.

Ultimately, making the documentation community driven so users can report any issues of the documentation and also be able to make changes that will be reviewed and merged by the AGL team.

## Community Bonding

Owing to timezone differences, my mentor and I scheduled the right time and medium for contact: triweekly Zoom Calls and constant communication over Telegram and IRC. Further refinement of objectives and goals were set to ensure that the proposed framework of the documentation site was in line with the priorities of the organization. Setup the [personal blog](https://growupboron.github.io/blog/) to log progress for future reference and help future Google Season of Docs applicants and aspiring technical writers alike. I started engaging actively within the AGL community by regularly participating in the [Weekly Developer Call](https://wiki.automotivelinux.org/dev-call-info). Since I had prior academic commitments and was already well accustomed to the AGL community. We decided to go ahead with the ```Documentation Development Phase``` earlier than the GSoD timeline.

## Documentation Development

- Initially, work was carried out over on ["agl-docs" GitHub repository](https://github.com/growupboron/agl-docs) with inputs from mentor regarding the theme and the implementation of the website. The corresponding ```readthedocs``` [project](https://readthedocs.org/projects/agl-docs/) and [site](http://agl-docs.readthedocs.io/).

- Later on, the initial repository was migrated over to ["documentation" Gerrit repository](https://git.automotivelinux.org/AGL/documentation/) in line with the contributions guidelines of AGL. Here are the corresponding ```readthedocs``` [project](https://readthedocs.org/projects/automotivegradelinux/) and [site](https://docs.automotivelinux.org/).

### Migrating to MkDocs and ReadtheDocs

To simplify the documentation site generation and maintenance from the earlier [four repositories](https://github.com/automotive-grade-linux/docs-webtemplate/blob/master/README.md) setup, it was decided to host the documentation site on ReadtheDocs using the robust and mature static site generator called MkDocs.

MkDocs uses markdown as its markup language, and many of its strengths come from the power and straightforwardness of markdown and its flexibility to maintain documentation. To ensure that every AGL user and developer would be able to easily navigate through the documentation, multiple mockup were created using different themes like [ReadtheDocs](https://agl-docs.readthedocs.io/en/master-rtd-default/), [Alabaster](https://agl-docs.readthedocs.io/en/master-albaster-0309/), [Material](https://agl-docs.readthedocs.io/en/master-material-0309/), [Bootstrap4](https://agl-docs.readthedocs.io/en/master-bootstrap4/), [Ivory](https://agl-docs.readthedocs.io/en/master-ivory/) and [Windmill](https://agl-docs.readthedocs.io/en/master-windmill/). [Windmill](https://agl-docs.readthedocs.io/en/master-windmill/) was finalized after discussion with the mentor and the AGL community mainly due to a clean and simple user interface with high responsiveness in mobile view and default collapsible navigation pane suiting AGL’s documentation index.

It was then decided to maintain the master version and new releases (>=jellyfish) of AGL on the new workflow and archive the older versions (=<icefish) by transferring it to [old-docs.automotivelinux.org](http://old-docs.automotivelinux.org/docs/en/icefish/getting_started). 

Currently, we are in the process of adding a CI configuration to build the MkDocs documentation directly from Gerrit. This way, every change request merged to the repository is reflected on the readthedocs site in a couple of seconds.

### Revising and Rewriting AGL documentation

- Major restructuring for segregation of Tutorials, How-to Guides, Reference, and Explanation.
- Removing obsolete images and information with updation of relevant sections.
- Reexamining build commands and verifying developer instructions on the corresponding platforms like Raspberry Pi 4 and QEMU.
- Added Contribution Guide that will help newcomers and active community members alike.
- The final [docs/](https://git.automotivelinux.org/AGL/documentation/tree/docs) structure :
    ```
    docs                    # https://git.automotivelinux.org/AGL/documentation/tree/docs
    ├── 0_Getting_Started
    │   ├── 1_Quickstart
    │   │   └── Using_Ready_Made_Images.md
    │   └── 2_Building_AGL_Image
    │       ├── 0_Build_Process.md
    │       ├── 1_Preparing_Your_Build_Host.md
    │       ├── 2_Downloading_AGL_Software.md
    │       ├── 3_Initializing_Your_Build_Environment.md
    │       ├── 4_Customizing_Your_Build.md
    │       ├── 5_0_Building_the_AGL_Image.md
    │       ├── 5_1_x86_Emulation_and_Hardware.md
    │       ├── 5_2_Raspberry_Pi_4.md
    │       └── 5_3_RCar_Gen_3.md
    ├── 1_Hardware_Support
    │   └── Overview.md
    ├── 2_Architecture_Guides
    │   ├── 1_Introduction
    │   │   ├── 0_Overview.md
    │   │   └── 1_AGL_Requirements_Specifications.md
    │   └── 2_Security_Blueprint
    │       ├── 0_Overview.md
    │       ├── 1_Hardware.md
    │       ├── 2_Secure_Boot.md
    │       ├── 3_Hypervisor.md
    │       ├── 4_Kernel.md
    │       ├── 5_Platform.md
    │       ├── 6_Application.md
    │       ├── 7_Connectivity.md
    │       ├── 8_Update_OTA.md
    │       ├── 9_Secure_development.md
    │       └── Annexes.md
    ├── 3_Developer_Guides
    │   ├── 1_Application_Framework
    │   │   ├── 0_Introduction.md
    │   │   ├── 1_afm-daemons.md
    │   │   ├── 2_widgets.md
    │   │   ├── 3_widgets_overview.md
    │   │   ├── 4_Widget_configuration_file.md
    │   │   ├── 5_Permissions.md
    │   │   └── 6_Quick-Tutorial.md
    │   ├── 1_Setting_Up_AGL_SDK.md
    │   ├── 2_Application_Framework_Binder
    │   │   ├── 0_Overview.md
    │   │   ├── 1_Binder_daemon_vocabulary.md
    │   │   ├── 2_How_to_write_a_binding.md
    │   │   ├── 3_Binder_References.md
    │   │   ├── 4_Binder_events_guide.md
    │   │   ├── 5_Binder_Application_writing_guide.md
    │   │   ├── 7_Document_revisions.md
    │   │   ├── Annexes
    │   │   │   ├── 1_Migration_to_bindings_v3.md
    │   │   │   ├── 2_WebSocket_protocol_x-afb-ws-json1.md
    │   │   │   ├── 3_Installing_the_binder_on_a_desktop.md
    │   │   │   ├── 4_Options_of_afb-daemon.md
    │   │   │   ├── 5_Debugging_binder_and_bindings.md
    │   │   │   ├── 6_LEGACY_Migration_from_v1_to_v2.md
    │   │   │   └── 7_LEGACY_Binding_v2_references.md
    │   ├── 2_Creating_a_New_Service.md
    │   ├── 3_AppFW_Privileges_Management
    │   │   └── AppFW-Privileges_Management.md
    │   ├── 3_Creating_a_New_Application.md
    │   ├── 4_AFB_Helper_Guide
    │   │   ├── 1_Usage.md
    │   │   ├── 2_AFB_Timer.md
    │   │   ├── 3_CURL_wrapper.md
    │   │   ├── 4_URL_Escaping.md
    │   │   ├── 5_Filescan_Utils.md
    │   │   ├── 6_Qt_AFB_Websocket_client.md
    │   │   ├── 7_JSON_library_for_modern_C++.md
    │   │   └── 8_C_JSON_Wrapper.md
    │   ├── 5_Using_CMAKE_Applications_Module
    │   │   ├── 1_Project_Architecture.md
    │   │   ├── 2_Configuring_AGL_CMake_Templates.md
    │   │   ├── 3_Advanced_Usage.md
    │   │   ├── 4_Advanced_Customization.md
    │   │   ├── 5_Autobuild.md
    │   │   └── 6_Using_CMake_Templates_from_Bitbake_Recipes.md
    │   └── 6_AGL_Layers
    │       ├── 1_Overview.md
    │       ├── 2_meta-agl.md
    │       ├── 3_meta-agl-demo.md
    │       └── 4_meta-agl-devel.md
    ├── 4_APIs_and_Services
    │   └── 0_API_Reference.md
    ├── 5_How_To_Contribute
    │   ├── 1_Getting_Linux_Foundation_account.md
    │   ├── 2_Using_Jira_for_current_work_items.md
    │   ├── 3_Working_with_Gerrit.md
    │   ├── 4_Submitting_Changes.md
    │   ├── 5_Reviewing_Changes.md
    │   ├── 6_Gerrit_Recommended_Practices.md
    │   ├── 7_General_Guidelines.md
    │   ├── 8_Adding_Documentation.md
    │   └── 9_Contribution_Checklist.md
    └── index.md
    ```

## Work Done

Final documentation site rendered at [docs.automotivelinux.org](https://docs.automotivelinux.org/).

**NOTE:** Some of the [Change Requests](https://gerrit.automotivelinux.org/gerrit/q/hashtag:%2522gsod%2522+(status:open+OR+status:merged)+owner:shankhoghosh123%2540gmail.com) might be going in through review and further changes can take place. Final GSoD work product as of the submission of this report : [agl-docs.readthedocs.io](http://agl-docs.readthedocs.io/).

### Commits

- [Github commits](https://github.com/growupboron/agl-docs/commits/)
- [Gerrit Change Requests](https://gerrit.automotivelinux.org/gerrit/q/hashtag:%2522gsod%2522+(status:open+OR+status:merged)+owner:shankhoghosh123%2540gmail.com)
- [Jira GSoD Tracker Bug](https://jira.automotivelinux.org/browse/SPEC-3633)

### Weekly Updates

All of the progress is well documented in the form of weekly updates over the ```agl-dev-community``` [mailing list](https://lists.automotivelinux.org/g/agl-dev-community/search?q=GSoD) and [personal blog](https://growupboron.github.io/blog/) :
- Week 0 & 1 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8613) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-0-1/))
- Week 2 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8632) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-2/)) 
- Week 3 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8640) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-3/)) 
- Week 4 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8683) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-4/)) 
- Week 5 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8697) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-5/))
- Week 6 & 7 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8724) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-6-7/))
- Week 8 & 9 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8783) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-8-9/))
- Week 10 & 11 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8826) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-10-11/))
- Week 12 & 13 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8857) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-12-13/))
- Week 14 ([mailing list](https://lists.automotivelinux.org/g/agl-dev-community/message/8878) | [blog](https://growupboron.github.io/blog/gsod-weekly-update-week-14/))

## Final Comments

### Future Work

- Rewrite and revise "[APIs and Services](https://agl-docs.readthedocs.io/en/master/#4_APIs_and_Services/0_API_Reference/)" section.

- Enable internationalization through [Multi Language Support](https://docs.readthedocs.io/en/stable/localization.html).

### Challenges

- Becoming proficient with AGL developer tools, especially `Gerrit` has been quite a worthwhile effort.

- Balancing academics along with GSoD was quite hectic but due to the mutual understanding with the mentors, I was able to overcome this.

### What did I learn?

- I learned a lot more about Automotive Grade Linux organization especially their developer tools, workflow, and developmental pipeline. 

- I was also able to learn how to use the MkDocs static site generator and readthedocs documentation platform. 

- My technical writing skills have definitely become better and have led me to contribute more effectively and robustly to academic research projects.

### Post GSoD

- I plan to maintain and add to the Automotive Grade Linux’s documentation repositories for the foreseeable future and work on continually improving it.

- I will keep contributing and help other new contributors to explore and learn projects in this organization.

- This project gave me the necessary experience and rigor to contribute meaningfully and efficiently to my role as Data Acquisition Engineer for [FSAE Team Fateh](https://teamfateh.com/).

- I plan to continue my involvement here at Automotive Grade Linux for the foreseeable future and also take part in [Google Summer of Code](https://summerofcode.withgoogle.com/) and continue my involvement with open source because it is the future and the best technique of learning is by doing.

### Acknowledgements

I would like to express my gratitude to my mentors [Jan-Simon Möller](https://www.automotivelinux.org/blog/developer-showcase-jansimon-moller/) and [Walt Miner](https://www.automotivelinux.org/about/leadership/) for mentoring me through GSoD and also to the whole AGL community for being so inclusive and friendly.

Overall, It was one of the best professional experience that I undertook this year. I have been fascinated with AGL for as long as I have been a Data Acquisition Engineer for [FSAE Team Fateh](https://teamfateh.com/) and the fact that I was able to contribute to the organization is an honor.
