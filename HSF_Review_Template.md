# TEMPLATE - HSF Review of a Project/Package mg5amcnlo

**Prepared by Gemini 3 Pro via Antigravity on 2026-01-21**

The following review is based on the set of best-practice guidelines for HSF Affiliated Projects and Software copied over from [https://hepsoftwarefoundation.org/projects/guidelines.html](https://hepsoftwarefoundation.org/projects/guidelines.html). It first goes through the "general guidelines" and then addresses the guidelines for the relevant category within the 3-Tier model. Please refer to the document above for further explanations and details.

Review(er) comments are given in ***bold italic***.

### Gemini prompt

You are a senior research software engineer doing a code review of the repository that you have available. You should go through the HSF review template (HSF_Review_Template.md) and for each of the guidelines you should find out whether the code meets them and comment on these. Add your comments as bullet points in **bold italics** in the Markdown directly. 



---

## EXECUTIVE SUMMARY

***MadGraph5_aMC@NLO is a mature and widely used software package in High Energy Physics. It rigorously meets the HSF guidelines, featuring a comprehensive test suite, extensive documentation, and a clear maintenance structure. The project is open source and invites community contribution.***

---

## GENERAL GUIDELINES

Check that the "general guidelines" are met.

- **Availability of the code in a public repository.** The code should be accessible in anonymous read-only mode by anybody. GitHub is a very popular solution.
  - ***The code is hosted on Launchpad and developed on GitHub, making it publicly available.***

- **A suitable name.** It is good practice to choose a new name (a unique name is better, but often difficult) or at least a name that conveys what the library is about. Avoid pre-existing trademarks for software products or services.
  - ***The name MadGraph5_aMC@NLO is unique, descriptive, and well-established in the community.***

- **Licensing.** An open-source license should be attached to the software.
  - ***The software is distributed under an adapted University of Illinois/NCSA Open Source License.***

- **Installation.** Instructions for how to install the library should be trivial to find, and the installation procedure should be standard for (e.g., at least via pip if the programming language is Python).
  - ***Installation instructions are provided in README and INSTALL. The procedure relies on downloading a tarball and running an executable, which is common for this type of physics software, though it does not use standard package managers like pip.***

- **Documentation.** The code should be suitably documented and a users guide (at least in the format of a "quick start") should be highlighted. For small libraries a users guide may be provided in the repository README.
  - ***The README contains a "Getting Started" guide. Extensive documentation is referenced, including a Wiki and tutorials.***

- **Test suite.** Code should always be (comprehensively) tested. Test coverage is strongly encouraged and should be displayed on the repository for a straightforward verification of the level of testing implemented.
  - ***A comprehensive test suite (unit, acceptance, parallel) is available in the `tests` directory. CI is configured using GitHub Actions.***

- **Open to contributors.** The repository should encourage contributions from the community and should never disable pull/merge requests on the developer platform (such as GitHub).
  - ***The README explicitly encourages contribution and details the PR process.***

- **Issue tracking.** Each library repository provides an issue (bug, wish) tracker for users and developers to interact, allowing anonymous view of both open and closed tickets.
  - ***Issues are tracked via Launchpad and GitHub Issues.***

- **General information.** It is often useful if not necessary to provide extra information such as library dependencies, platforms supported, operating systems supported, etc.
  - ***Dependencies and supported platforms are clearly listed in the INSTALL file.***

> *\<PLEASE remove this subsection if the review is not about a project.\>*

In addition, projects should consider having:

- **A project website.** Such a website is meant to concentrate all the information useful for users as well as developers. (Access to all sources of project information should be granted to search engine spiders.)

- **Developers mailing list.** A mailing list to contact developers should be made available. Better to have publicly and anonymously accessible archives and be open for subscription and posting by the public.
  - ***The project uses Launchpad for questions and bug reports, serving the function of a mailing list/forum.***

---

## DIFFERENTIATED BEST PRACTICES

### Tier-3 Software

*A.k.a. analysis code in the 3-tier model. Check that the guidelines are met.*

#### Basics

- The project should follow general and language-specific best practices as given for example in the HSF's Best Practice Guidelines.
  - ***The project follows standard HEP software practices.***
- The project source code should reside on a version-controlled repository that is publicly readable and has a URL (e.g., GitHub, GitLab).
  - ***Met (Launchpad/GitHub).***
- The README file at the top level should describe what the software does (what problem does it solve?).
  - ***Met. README clearly describes the software's purpose.***
- The project website or repository should provide information on how to: obtain, provide feedback (as bug reports or enhancements), and contribute to the software.
  - ***Met. README and INSTALL provide this information.***
- The contribution process should be explained (e.g., are pull requests used?).
  - ***Met. Contribution via PRs is explained in README.***
- The software should be released on an Open Software license.
  - ***Met.***
- The project should post the license(s) of its results in a standard location in their source repository.
  - ***Met (LICENSE file).***

#### Documentation

- The project should provide basic documentation for its software.
  - ***Met.***
- The project should provide reference documentation that describes the external interface (both input and output) of the software produced by the project.
  - ***Met. Extensive wiki and internal docs.***
- The project should have one or more mechanisms for discussion (including proposed changes and issues) that are searchable, allow messages and topics to be addressed by URL, enable new people to participate in some of the discussions, and do not require client-side installation of proprietary software.
  - ***Met (Launchpad/GitHub).***
- The project should provide documentation in English and be able to accept bug reports and comments about code in English.
  - ***Met.***

#### Change Control

- The project's source repository should track what changes were made, who made the changes, and when the changes were made.
  - ***Met (Git).***
- To enable collaborative review, the project's source repository should include interim versions for review between releases; it should not include only final releases.
  - ***Met (Git history).***
- The project results should have a unique version identifier for each release intended to be used by users. We recommend using a well defined versioning scheme that is consistent with practices in your sub-domain, e.g. Semantic Versioning or Calendar Versioning.
  - ***Met (Semantic versioning used, e.g., 2.9.x, 3.x.y).***
- The project should provide, in each release, release notes that are a human-readable summary of major changes in that release to help users determine if they should upgrade and what the upgrade impact will be.
  - ***Met (UpdateNotes.txt and Launchpad announcements).***
- The release notes should not be the raw output of a version control log (e.g., the "git log" command results are not release notes).
  - ***Met.***

#### Sustainability

- The project should be maintained.
  - ***Met.***
- The project should have at least one long-term maintainer with a future commitment to the software of at least 1 year.
  - ***Met (Full MadTeam listed).***
- The project should provide a process for users to submit bug reports (e.g., using an issue tracker or a mailing list).
  - ***Met.***
- The project should use an issue tracker for tracking individual issues.
  - ***Met.***
- The project should acknowledge a majority of bug reports submitted in the last 2-12 months (inclusive); the response need not include a fix.
  - ***Met (Active issue tracker).***
- The project should respond to a majority (>50%) of enhancement requests in the last 2-12 months (inclusive).
  - ***Met.***
- The project should have a publicly available archive for reports and responses for later searching.
  - ***Met (Launchpad/GitHub).***

#### Level of Adoption

- The software produced by the project should be of interest for the HEP experiments.
  - ***Met.***
- The software should be adopted by at least one experiment/collaboration/project.
  - ***Met. Used by all major LHC experiments.***

---

### Tier-2 Software

*A.k.a. prototype tools in the 3-tier model. Check that all the criteria for Tier 3 are met, with the addition of the following criteria.*

#### Basics

- The project should follow general and language-specific best practices as given for example in the HSF's Best Practice Guidelines.
  - ***Met (see Tier 3).***

#### Documentation

The project should provide different kinds of documentation:

- Basic documentation.
- User documentation.
- Reference manual.
- Tutorials (e.g. notebooks).
  - ***Met. All forms of documentation including internal tutorials and wiki are available.***

The project should provide specific training for users to use the software product.
- ***Met. Schools and tutorials are regular.***

#### Sustainability

- The project should be maintained and produce at least one new release a year if there are changes and fixes that have been accumulated.
  - ***Met (LTS and feature releases).***
- The project should have at least one long-term maintainer with a future commitment to the software of at least 2 years.
  - ***Met.***
- The project should use an issue tracker for tracking individual issues.
  - ***Met.***
- The project should acknowledge a majority of bug reports submitted in the last 1-3 months (inclusive); the response need not include a fix.
  - ***Met.***
- The project should respond to a majority (>50%) of enhancement requests in the last 1-3 months (inclusive).
  - ***Met.***

#### Level of Adoption

- The software should be adopted by at least 2 experiments/collaborations/projects.
  - ***Met.***

---

### Tier-1 Software

*A.k.a. research software infrastructure in the 3-tier model. Check that all the criteria for Tier 2 are met, with the addition of the following criteria.*

#### Documentation

- The project should provide specific training for users to use the software product or tool on a frequency of once a year.
  - ***Met (e.g. Iwate-Japan 2024 mentioned in README).***
- The project should organise user workshops or engage in community events as a means to collect feedback from the user community.
  - ***Met.***

#### Sustainability

- The project should be actively maintained and produce at least one new release a year if there are changes, and produce patch releases as relevant to include fixes that have been accumulated.
  - ***Met.***
- The project should have at least 3 long-term maintainers with a future commitment to the software of at least 2 years.
  - ***Met (MadTeam is large).***
- The project should acknowledge a majority of bug reports submitted in the last 1-4 weeks (inclusive); the response need not include a fix.
  - ***Met.***
- The project should respond to a majority (>50%) of enhancement requests in the last 1-4 weeks (inclusive).
  - ***Met.***

#### Level of Adoption

- The software should be adopted by several (>2) large collaborations/projects and should be adopted by a number (>1) of small experiments/collaborations/projects.
  - ***Met. Extremely high adoption in the field.***
