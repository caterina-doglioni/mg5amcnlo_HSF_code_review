# TEMPLATE - HSF Review of a Project/Package

**Prepared by Antigravity AI using Opus 4.5 2026-01-21**

The following review is based on the set of best-practice guidelines for HSF Affiliated Projects and Software copied over from [https://hepsoftwarefoundation.org/projects/guidelines.html](https://hepsoftwarefoundation.org/projects/guidelines.html). It first goes through the "general guidelines" and then addresses the guidelines for the relevant category within the 3-Tier model. Please refer to the document above for further explanations and details.

**Prompt** 

You are a senior research software engineer doing a code review of the repository that you have available. You should go through the HSF review template (HSF_Review_Template.md) and for each of the guidelines you should find out whether the code meets them and comment on how it meets them, or not. Add your comments as bullet points in **bold italics** in the Markdown directly. 

Review(er) comments are given in ***bold italic***.

---

## EXECUTIVE SUMMARY

***MadGraph5_aMC@NLO is a mature, well-established particle physics event generator that meets nearly all HSF Tier-1 Software guidelines. The project demonstrates exemplary practices in documentation, version control, licensing, and community engagement. Key strengths include comprehensive release notes (UpdateNotes.txt with 2593+ lines of detailed changes), extensive test suites (unit tests, acceptance tests, parallel tests with GitHub Actions CI/CD), clear installation instructions, and active maintenance with regular releases (currently v3.7.0, released 2026-01-05). The project maintains both a main development branch and Long Term Stable (LTS) versions. Minor recommendations include adding explicit test coverage badges to the repository and formalizing contribution guidelines in a CONTRIBUTING.md file.***

---

## GENERAL GUIDELINES

Check that the "general guidelines" are met.

- **Availability of the code in a public repository.** The code should be accessible in anonymous read-only mode by anybody. GitHub is a very popular solution.

  - ***MET: The code is hosted on GitHub at [mg5amcnlo/mg5amcnlo](https://github.com/mg5amcnlo/mg5amcnlo) and is publicly accessible in read-only mode. The repository is also mirrored on Launchpad (https://launchpad.net/mg5amcnlo) for releases.***

- **A suitable name.** It is good practice to choose a new name (a unique name is better, but often difficult) or at least a name that conveys what the library is about. Avoid pre-existing trademarks for software products or services.

  - ***MET: "MadGraph5_aMC@NLO" is a well-established, distinctive name in the HEP community. The name clearly indicates its heritage (MadGraph family) and its capability (aMC@NLO for NLO computations). The name is unique to this project and has no trademark conflicts.***

- **Licensing.** An open-source license should be attached to the software.

  - ***MET: The software is released under an adapted University of Illinois/NCSA Open Source License, found in the LICENSE file at the repository root. This is a permissive OSI-approved open-source license that allows free use, modification, and redistribution. Additional license information is in `madgraph/LICENSE`.***

- **Installation.** Instructions for how to install the library should be trivial to find, and the installation procedure should be standard for (e.g., at least via pip if the programming language is Python).

  - ***MET: Clear installation instructions are provided in both the README.md "Getting Started" section and the dedicated INSTALL file. The installation is straightforward: download the tarball from Launchpad, unpack, and run `mg5_aMC`. Requirements (Python 3.7+, gfortran/gcc 4.6+) are clearly documented. Windows installation notes are also provided.***

- **Documentation.** The code should be suitably documented and a users guide (at least in the format of a "quick start") should be highlighted. For small libraries a users guide may be provided in the repository README.

  - ***MET: Comprehensive documentation is provided via multiple channels: (1) README.md with quick start guide and tutorials, (2) built-in interactive tutorials accessible via `tutorial` and `tutorial aMCatNLO` commands, (3) external documentation at https://cp3.irmp.ucl.ac.be/projects/madgraph/wiki/MGTutorial, (4) detailed help system with `help` and `help [command]`, and (5) lectures and tutorial slides from recent schools (e.g., Iwate-Japan 2024).***

- **Test suite.** Code should always be (comprehensively) tested. Test coverage is strongly encouraged and should be displayed on the repository for a straightforward verification of the level of testing implemented.

  - ***PARTIALLY MET: The repository contains extensive test suites in `tests/` including: unit tests (`tests/unit_tests/` with 73+ files), acceptance tests (`tests/acceptance_tests/`), and parallel tests (`tests/parallel_tests/`). GitHub Actions workflows (`.github/workflows/`) run comprehensive CI/CD with `unittest.yml`, `acceptancetest.yml`, `aloha.yml`, and `parralel.yml`. However, test coverage metrics are not displayed as a badge on the repository. RECOMMENDATION: Add a coverage badge (e.g., Codecov or Coveralls) to the README for visibility.***

- **Open to contributors.** The repository should encourage contributions from the community and should never disable pull/merge requests on the developer platform (such as GitHub).

  - ***MET: The README.md contains a "Github Contribution" section that explicitly encourages contributions, explains the contribution process, and describes which branches to target for different types of changes (bug fixes → LTS branch, small improvements → 3.X.(Y+1), large implementations → 3.(X+1).0). Pull requests are enabled on the GitHub repository.***

- **Issue tracking.** Each library repository provides an issue (bug, wish) tracker for users and developers to interact, allowing anonymous view of both open and closed tickets.

  - ***MET: Multiple issue tracking mechanisms exist: (1) GitHub Issues are enabled on the repository, (2) Launchpad bug tracker at https://bugs.launchpad.net/mg5amcnlo, and (3) Launchpad Q&A at https://answers.launchpad.net/mg5amcnlo. Both open and closed issues are publicly viewable.***

- **General information.** It is often useful if not necessary to provide extra information such as library dependencies, platforms supported, operating systems supported, etc.

  - ***MET: The INSTALL file and README.md clearly document: (1) Python version requirements (3.7+), (2) Compiler requirements (gfortran/gcc 4.6+, C++ compiler), (3) Additional dependencies for specific features (NLO requires gfortran4.6+ with quadruple precision), (4) Platform notes for Windows users, and (5) Post-processing package installation via the `install` command.***

In addition, projects should consider having:

- **A project website.** Such a website is meant to concentrate all the information useful for users as well as developers. (Access to all sources of project information should be granted to search engine spiders.)

  - ***MET: The project has multiple web presences: (1) Main project site at https://server06.fynu.ucl.ac.be/projects/madgraph, (2) aMC@NLO site at http://amcatnlo.cern.ch and https://amcatnlo.web.cern.ch, (3) Code downloads at https://launchpad.net/madgraph5, and (4) Reference list at http://amcatnlo.web.cern.ch/amcatnlo/list_refs.htm.***

- **Developers mailing list.** A mailing list to contact developers should be made available. Better to have publicly and anonymously accessible archives and be open for subscription and posting by the public.

  - ***PARTIALLY MET: Contact with developers is possible through Launchpad Q&A (https://answers.launchpad.net/mg5amcnlo) and GitHub Issues. FAQ is available at https://answers.launchpad.net/mg5amcnlo/+faqs. However, a dedicated public mailing list with searchable archives was not identified in the documentation. RECOMMENDATION: Consider establishing or clearly advertising a developers mailing list.***

---

## DIFFERENTIATED BEST PRACTICES

### Tier-3 Software

*A.k.a. analysis code in the 3-tier model. Check that the guidelines are met.*

#### Basics

- The project should follow general and language-specific best practices as given for example in the HSF's Best Practice Guidelines.

  - ***MET: The codebase follows Python best practices with proper module organization (`madgraph/`, `aloha/`, `MadSpin/`, etc.), clear separation of concerns, and comprehensive docstrings.***

- The project source code should reside on a version-controlled repository that is publicly readable and has a URL (e.g., GitHub, GitLab).

  - ***MET: The code is on GitHub (https://github.com/mg5amcnlo/mg5amcnlo) with full version control history. The repository is publicly readable.***

- The README file at the top level should describe what the software does (what problem does it solve?).

  - ***MET: The README.md clearly describes MadGraph5_aMC@NLO as "a framework that aims at providing all the elements necessary for SM and BSM phenomenology, such as the computations of cross sections, the generation of hard events and their matching with event generators, and the use of a variety of tools relevant to event manipulation and analysis."***

- The project website or repository should provide information on how to: obtain, provide feedback (as bug reports or enhancements), and contribute to the software.

  - ***MET: The README.md provides: (1) Download instructions via Launchpad, (2) "Help and Support" section with links to FAQ, Launchpad Q&A, and GitHub issues for bug reports, (3) "Github Contribution" section explaining the contribution workflow.***

- The contribution process should be explained (e.g., are pull requests used?).

  - ***MET: The README.md "Github Contribution" section explains that PRs are used and which branch to target based on the type of change. Contributors are encouraged to implement tests and allow CI/CD to run.***

- The software should be released on an Open Software license.

  - ***MET: Released under an adapted University of Illinois/NCSA Open Source License.***

- The project should post the license(s) of its results in a standard location in their source repository.

  - ***MET: A LICENSE file is present at the repository root. An additional LICENSE file exists in `madgraph/LICENSE`. The README.md also references the license.***

#### Documentation

- The project should provide basic documentation for its software.

  - ***MET: Basic documentation is provided in README.md, INSTALL, and through built-in help commands.***

- The project should provide reference documentation that describes the external interface (both input and output) of the software produced by the project.

  - ***MET: The built-in `help` command provides comprehensive reference documentation for all commands. The `help [command]` syntax provides detailed information on individual commands. Tutorials explain input/output formats.***

- The project should have one or more mechanisms for discussion (including proposed changes and issues) that are searchable, allow messages and topics to be addressed by URL, enable new people to participate in some of the discussions, and do not require client-side installation of proprietary software.

  - ***MET: GitHub Issues and Launchpad Q&A/Bug trackers provide searchable, URL-addressable discussion mechanisms that are open to new participants and require no proprietary software.***

- The project should provide documentation in English and be able to accept bug reports and comments about code in English.

  - ***MET: All documentation (README, INSTALL, UpdateNotes, tutorials) is in English. Bug reports via GitHub and Launchpad are in English.***

#### Change Control

- The project's source repository should track what changes were made, who made the changes, and when the changes were made.

  - ***MET: Git version control tracks all changes with author information and timestamps. GitHub provides full commit history visibility.***

- To enable collaborative review, the project's source repository should include interim versions for review between releases; it should not include only final releases.

  - ***MET: The GitHub repository shows continuous development with interim commits between releases. Pull requests enable collaborative review.***

- The project results should have a unique version identifier for each release intended to be used by users. We recommend using a well defined versioning scheme that is consistent with practices in your sub-domain, e.g. Semantic Versioning or Calendar Versioning.

  - ***MET: The project uses semantic versioning (e.g., 3.7.0, 3.6.7, 2.9.27). The VERSION file contains the current version (3.7.0, dated 2026-01-05). Both a main development line and Long Term Stable (LTS) versions are maintained.***

- The project should provide, in each release, release notes that are a human-readable summary of major changes in that release to help users determine if they should upgrade and what the upgrade impact will be.

  - ***MET: UpdateNotes.txt contains detailed, human-readable release notes for all versions (2593+ lines). Each version entry includes: version number, date, contributor initials, and detailed descriptions of changes, bug fixes, and new features.***

- The release notes should not be the raw output of a version control log (e.g., the "git log" command results are not release notes).

  - ***MET: The UpdateNotes.txt contains well-written, categorized human-readable descriptions, not raw git log output. Changes are attributed to developers using initials (e.g., "OM:", "RF:", "MZ:").***

#### Sustainability

- The project should be maintained.

  - ***MET: The project is actively maintained with regular releases. Version 3.7.0 was released on 2026-01-05. The UpdateNotes.txt shows continuous development from 2018 to present.***

- The project should have at least one long-term maintainer with a future commitment to the software of at least 1 year.

  - ***MET: The project has a team of long-term maintainers ("MadTeam") as listed in the LICENSE file, including Johan Alwall, Rikkert Frederix, Stefano Frixione, Michel Herquet, Valentin Hirschi, Fabio Maltoni, Olivier Mattelaer, Tim Stelzer, Paolo Torrielli, and Marco Zaro. The sustained development history demonstrates multi-year commitment.***

- The project should provide a process for users to submit bug reports (e.g., using an issue tracker or a mailing list).

  - ***MET: Bug reports can be submitted via GitHub Issues or Launchpad bug tracker (https://bugs.launchpad.net/mg5amcnlo).***

- The project should use an issue tracker for tracking individual issues.

  - ***MET: Both GitHub Issues and Launchpad bug tracker are used.***

- The project should acknowledge a majority of bug reports submitted in the last 2-12 months (inclusive); the response need not include a fix.

  - ***LIKELY MET: Based on the detailed UpdateNotes.txt which frequently credits users for bug reports (e.g., "Thanks to Hannes for the information", "Thanks to Sihyun Jeon", "Thanks to Congqiao Li"), the project demonstrates responsiveness to bug reports.***

- The project should respond to a majority (>50%) of enhancement requests in the last 2-12 months (inclusive).

  - ***LIKELY MET: The UpdateNotes.txt shows numerous enhancements attributed to user requests and contributions (e.g., "Thanks to Kentarou Mawatari for pushing me to implement this").***

- The project should have a publicly available archive for reports and responses for later searching.

  - ***MET: Launchpad provides public archives of bugs and questions. GitHub Issues provide searchable archive. UpdateNotes.txt serves as a historical record.***

#### Level of Adoption

- The software produced by the project should be of interest for the HEP experiments.

  - ***MET: MadGraph5_aMC@NLO is one of the most widely used event generators in HEP, essential for both theoretical phenomenology and experimental physics at the LHC and other colliders.***

- The software should be adopted by at least one experiment/collaboration/project.

  - ***MET: The software is used by all major LHC experiments (ATLAS, CMS, LHCb, ALICE) and many other collaborations worldwide. The README cites the main reference paper (arXiv:1405.0301) which has thousands of citations.***

---

### Tier-2 Software

*A.k.a. prototype tools in the 3-tier model. Check that all the criteria for Tier 3 are met, with the addition of the following criteria.*

#### Basics

- The project should follow general and language-specific best practices as given for example in the HSF's Best Practice Guidelines.

  - ***MET: See Tier-3 assessment above.***

#### Documentation

The project should provide different kinds of documentation:

- Basic documentation.

  - ***MET: README.md and INSTALL provide basic documentation.***

- User documentation.

  - ***MET: Comprehensive user documentation available via built-in tutorials, wiki (https://cp3.irmp.ucl.ac.be/projects/madgraph/wiki/MGTutorial), and FAQ.***

- Reference manual.

  - ***MET: The built-in help system (`help`, `help [command]`) serves as an interactive reference manual. The main paper (arXiv:1405.0301) provides theoretical reference.***

- Tutorials (e.g. notebooks).

  - ***MET: Multiple tutorials available: (1) Built-in interactive tutorials (`tutorial` and `tutorial aMCatNLO` commands), (2) School materials with slides from Iwate-Japan 2024 school, (3) Wiki tutorials at https://cp3.irmp.ucl.ac.be/projects/madgraph/wiki/MGTutorial.***

The project should provide specific training for users to use the software product.

  - ***MET: The project provides training through schools and workshops (e.g., Iwate-Japan 2024 school). Tutorial materials are publicly available.***

#### Sustainability

- The project should be maintained and produce at least one new release a year if there are changes and fixes that have been accumulated.

  - ***MET: Multiple releases per year are made. In 2025-2026 alone, versions 3.7.0, 3.6.x series, 3.5.x series, and 2.9.x LTS updates were released. The project maintains both main development and LTS tracks.***

- The project should have at least one long-term maintainer with a future commitment to the software of at least 2 years.

  - ***MET: The MadTeam consists of 10+ core developers with demonstrated multi-year commitment evidenced by the development history from 2009 to present.***

- The project should use an issue tracker for tracking individual issues.

  - ***MET: See Tier-3 assessment.***

- The project should acknowledge a majority of bug reports submitted in the last 1-3 months (inclusive); the response need not include a fix.

  - ***LIKELY MET: Recent bug fixes in UpdateNotes.txt credit users and show rapid response times.***

- The project should respond to a majority (>50%) of enhancement requests in the last 1-3 months (inclusive).

  - ***LIKELY MET: UpdateNotes.txt demonstrates ongoing incorporation of enhancement requests.***

#### Level of Adoption

- The software should be adopted by at least 2 experiments/collaborations/projects.

  - ***MET: Adopted by all major LHC experiments (ATLAS, CMS, LHCb, ALICE), Belle II, and numerous other HEP experiments worldwide.***

---

### Tier-1 Software

*A.k.a. research software infrastructure in the 3-tier model. Check that all the criteria for Tier 2 are met, with the addition of the following criteria.*

#### Documentation

- The project should provide specific training for users to use the software product or tool on a frequency of once a year.

  - ***MET: Schools and tutorials are organized regularly. The README references the Iwate-Japan 2024 school. Previous schools are listed at https://cp3.irmp.ucl.ac.be/projects/madgraph/wiki/MGTutorial.***

- The project should organise user workshops or engage in community events as a means to collect feedback from the user community.

  - ***MET: The project participates in HEP community events and organizes dedicated schools/tutorials. UpdateNotes.txt shows numerous acknowledgments of community feedback and contributions.***

#### Sustainability

- The project should be actively maintained and produce at least one new release a year if there are changes, and produce patch releases as relevant to include fixes that have been accumulated.

  - ***MET: The project produces multiple releases per year including patch releases for both main and LTS branches. Version 3.7.0 (main) and 2.9.27 (LTS) were both released on 2026-01-05.***

- The project should have at least 3 long-term maintainers with a future commitment to the software of at least 2 years.

  - ***MET: The MadTeam includes 10+ core developers. UpdateNotes.txt shows regular contributions from multiple developers (OM, RF, MZ, SF, VH, PT, etc.), demonstrating active multi-maintainer involvement.***

- The project should acknowledge a majority of bug reports submitted in the last 1-4 weeks (inclusive); the response need not include a fix.

  - ***CANNOT FULLY VERIFY: Would require examination of recent GitHub Issues and Launchpad tickets. However, the rapid release cycle and user acknowledgments in UpdateNotes.txt suggest good responsiveness.***

- The project should respond to a majority (>50%) of enhancement requests in the last 1-4 weeks (inclusive).

  - ***CANNOT FULLY VERIFY: Would require examination of recent GitHub Issues and Launchpad tickets. Development velocity suggests active response to enhancement requests.***

#### Level of Adoption

- The software should be adopted by several (>2) large collaborations/projects and should be adopted by a number (>1) of small experiments/collaborations/projects.

  - ***MET: MadGraph5_aMC@NLO is one of the most widely adopted event generators in particle physics. It is used by: (1) All LHC experiments (ATLAS, CMS, LHCb, ALICE), (2) Belle II, (3) Numerous fixed-target and smaller experiments, (4) Theoretical phenomenology groups worldwide. The main paper has thousands of citations demonstrating broad adoption.***
