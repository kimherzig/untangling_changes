# untangling_changes

## News
* 2015-09-21
Moved repository from https://www.st.cs.uni-saarland.de/softevo/untangling_changes/

* 2012-11-19
We moved the data sets to a public radable Git repository: https://hg.st.cs.uni-saarland.de/git/untangling-public-data/. We also fixed some falsely marked obvious blobs. The data sets in the Git repository are up-to-date. Please note that the results of the TechReport are only affected marginally!

* 2011-09-29
The data sets showing the change sets and their classification (tangled or atomic) as presented in the paper are now online.

## Why untangling changes?

Mining version archives became a popular research field. Most research approaches analyze version archives to map bug reports or other external documents to committed changes. Mostly this is done by parsing the commit message of the applied changes scanning for bug report or other document IDs. But these approaches rely on the fact that developers write (correct) commit messages. Even if a commit message contains a bug report ID there is no evidence that the change applied only the bug fix without any extra code changes. In empirical studies researchers found that many of the applied code changes are non-atomic---meaning that applied bug fixes also touch code artifacts that were refactored or reformatted without any hint in the commit message. This introduces noise and bias into prediction and recommendation tools and their evaluation. With this work, we aim to build an algorithm that is capable to automatically untangle code changes into code change partitions. Each partition corresponds to an individual development task and could have been applied separately.

## Download

The different data sets are provided as CSV files for five open-source projects: ArgoUML, Google Webtool Kit, Jaxen, JRuby, XStream. The corresponding project repositories were transformed to GIT repositories before analysis. The corresponding GIT repositories can also be downloaded below.
Except for the git repositories, the data sets are provided in a public readable Git reposiotry: https://hg.st.cs.uni-saarland.de/git/untangling-public-data/. You can either clone the Git repository or browse the files online.

Please note that transactions are identified by GIT-hashes and not by SVN ids. We also provide a mapping file between the original SVN ids and GIT hashes for the individual project repositories.

## GIT repositories

Each repository download is a 7z file. You can unzip it using 7zip. Each zip file contains a directory holding the project name. Each directory contains the GIT repository which can be used, directly. 

## Atomic fixes

We manually classified bug fixes as atomic. Atomic classified bug fixes are bug fixes that apply only those code changes required to fix a particular issue without applying extra code changes. We classified code changes using their commit message and the individual code changes applied. (Since we are project outsiders, we cannot ensure that our classification is correct.) Code changes not classified as atomic may be atomic but were mis-classified. Vice versa, we only classified code changes as being atomic if there were no doubts about their atomicity.
The data sets are contained in the Git repository subdirectory ``atomic_fixes''.

## Obvious blobs

We manually classified code changes to be non-atomic using the commit messages only. If a commit message contains multiple bug report references or a clear indication of other code changes applied that were not relevant for the main purpose (e.g. refactorings) we marked it as non-atomic. The data sets downloadable below contains git hashes of those transactions that could be classified as non-atomic. All code changes in none of the data sets (atomic fixes, obvious blobs) were undecidable for us. 
The data sets are contained in the Git repository subdirectory ``obvious_blobs''.

## Papers

[2011] K. Herzig and A. Zeller, "Untangling Changes", under submission, 2011.
People

* Kim Herzig (contact)
* Andreas Zeller
