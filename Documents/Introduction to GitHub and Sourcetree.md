# Introduction to GitHub and Sourcetree

- [Overview](#Overview)
  - [What Are GitHub and Sourcetree?](#What-Are-GitHub-and-Sourcetree?)
  - [Why Use These Technologies?](#Why-Use-These-Technologies?)
  - [Relevant Git Terminology](#Relevant-Git-Terminology)
- [Getting Started with GitHub](#Getting-Started-with-GitHub)
- [Getting Started with Sourcetree](#Getting-Started-with-Sourcetree)
- [Working with Gnu Privacy Guard (GPG) Keys](#Working-with-Gnu-Privacy-Guard-(GPG)-Keys)
- [Cloning Company Repositories](#Cloning-Company-Repositories)
- [Making New Branches in Sourcetree](#Making-New-Branches-in-Sourcetree)
- [Committing Changes in Sourcetree](#Committing-Changes-in-Sourcetree)
- [Synching with the Team](#Synching-with-the-Team)
- [Working with Pull Requests in GitHub](#Working-with-Pull-Requests-in-GitHub)
- [Next Steps](#Next-Steps)

## Overview
Our team manages documentation using GitHub and Sourcetree. This page serves as a primer to these technologies and a guide to setting up and working with them.

### What Are GitHub and Sourcetree?
[GitHub](https://github.com/) is a file hosting platform for version control and collaboration. Simply put, it is a storage location in the cloud. A user can control limited aspects of documents stored on GitHub through a browser, but tools like [Sourcetree](https://www.sourcetreeapp.com/) are what allow for in-depth file management.

Sourcetree and GitHub are connected using [Git](https://git-scm.com/) as the underlying technology for how this kind of source control works. Because of this, you will naturally learn how Git works by learning how to use these tools.

### Why Use These Technologies?
Large projects and large teams interacting with them can become difficult to manage. Source control enables versioning and workflows for creating and approving documents that make collaboration easier, even as projects and teams grow.

While these tools aren't the only solution for this problem, they are some of the most widely used.

### Relevant Git Terminology
Before getting started, it is important to review common terms associated with Git since they will be sprinkled throughout resources in the following sections. [This guide by A Cloud Guru](https://acloudguru.com/blog/engineering/git-terms-explained) offers a concise list to become familiar with as you continue getting set up.


## Getting Started with GitHub
1. [Create a GitHub account *(Internal Document)*](#).
2. [Enable Two-Factor Authentication (2FA)](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa). 2FA is a requirement to work with Company GitHub projects.
3. [Create a Personal Access Token (PAT)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token). PATs are used in place of passwords to interact with GitHub in programs like Sourcetree when 2FA is enabled.
   1. When selecting scopes, check **repo** and **user**.

> **NOTE:** For security reasons, a new PAT must be generated if it is forgotten. GitHub will not allow you to copy PATs after navigating off of their initial creation page.


## Getting Started with Sourcetree
Atlassian's documentation serves as a great resource to get accustomed to Sourcetree. Because Sourcetree is versatile, there may be mention of other technologies like Mercurial. It is not required to understand anything beyond Sourcetree itself, GitHub, and Git.

1. [Install Sourcetree](https://confluence.atlassian.com/get-started-with-sourcetree/install-sourcetree-847359094.html).
2. [Connect Sourcetree with GitHub](https://confluence.atlassian.com/get-started-with-sourcetree/connect-your-bitbucket-or-github-account-847359096.html).
   1. Select Basic for **Auth Type**.
   2. Use your GitHub username as your **Username**.
   3. Use your PAT as your **Password**.
   4. Select HTTPS for **Protocol**. Click **Save**.
3. [Become familiar with Sourcetree’s interface](https://confluence.atlassian.com/get-started-with-sourcetree/understand-the-interface-847359069.html).
4. [Review working with Git through Sourcetree](https://confluence.atlassian.com/get-started-with-sourcetree/work-using-git-847359053.html).


## Working with Gnu Privacy Guard (GPG) Keys
[GPG](https://gnupg.org/) keys are used to sign and verify commits. They must be enabled to successfully work with Company repositories.

1. [Set up GPG keys on your computer *(Internal Document)*](#).
   1. During several steps of this process, the guide asks you to run code blocks on your machine. This needs to be done using the Command Prompt in Windows or the Terminal in macOS.
   2. You do not need to do anything else with the GPG tool you install in **Step 0c**. Close it after installation and continue.
   3. **Step 1** links to GitHub documentation that may not be clear. Here are some things to keep in mind:
      1. When installing GPG command line tools, download **Gpg4win** for Windows or **Mac GPG** for macOS. Both can be found in the **GnuPG Binary Releases** section further down in [the page GitHub links to](https://gnupg.org/download/).
      2. GitHub will ask you to copy and paste commands that have a `$` symbol at the start. Do not copy the `$`; just copy the rest of the command. For example `$ gpg --full-generate-key` should just be `gpg --full-generate-key`.
      3. Make sure your key is **4096** bits as this is a requirement. Default options for other parts of the key generation are fine.
      4. When asked for your name and email, use the name and email associated with your GitHub account.
      5. When asked to enter a secure passphrase during this process, type whatever you like. This passphrase is for the key itself, not your GitHub account. Save it somewhere in case you need to use it in the future.
      6. Once your GPG key is generated, the GitHub documentation will then take you through fetching the ID of that key and using it to get a public key. This public key is what you will paste into GitHub.
   4. Pay particular attention to **Step 4** and **Step 5** to ensure that GPG keys are used system-wide.
   5. Restart Sourcetree after the process is complete.
2. If using Windows, no other steps are necessary.
3. If using macOS, Sourcetree may need another setting enabled to work with GPG keys:
   1. For each repository, go to **Settings > Security** and check **Enable GPG key signing for commits**.
   2. Your previously generated key should automatically be listed. Click **OK**.

> **NOTE:** If you do not have access to the articles linked in this section, let the documentation team know as soon as possible.


## Cloning Company Repositories
After connecting your GitHub account to Sourcetree, repositories associated with the Company organization should show up in the **Remote** tab. In Windows, you may need to open a new Sourcetree tab to see the option to view remote repositories.

Each repository will have the option to **Clone** it to your computer. Cloning a repository makes a local copy of the repository on your computer that you can edit and then use to update the remote repository.

If you are going to be editing documentation, start by cloning these repositories:

- *List Redacted.*

If you are going to editing DevOps recipes, start by cloning these repositories:

- *List Redacted.*

If these repositories do not show up in your Sourcetree remote repository list automatically, you can add and clone them manually:

1. In Windows, open a new Sourcetree tab, and click the **Clone** tab to the right of **Remote**.
In macOS, the same window opens by going to **New… > Clone** from URL.
2. Enter the above URLs individually. For each, the rest of the fields in the form will automatically populate.
3. Keep the populated information as is and click **Clone**.

> **WARNING:** In Windows, Sourcetree may prompt you to **select a credential helper** when you try to clone a repository. Select **manager** for this. The clone should now succeed. If not, try **manager-core** instead.


## Making New Branches in Sourcetree
After cloning a Company repository, it is important to manage your branches and create new ones for each Jira issue assigned. A branch is a version of a repository’s files that splits off from another version in order to make and save edits in a contained environment. We use a main branch for approved updates and branch off of it to work on changes. To do this:

1. Always make sure your **main** branch is up-do-date before branching. In Sourcetree’s repository view, locate the **Branches** section on the left pane. Double-click **main** and then click the **Pull** button towards the top of the window.
2. Double-click **main** again and click **Branch**.
3. In the new window, use the naming conventions outlined in the [Documentation Team GitHub Etiquette page *(Internal Document)*](#) to fill out the **New Branch** field.
4. Leave the rest of the settings as default and click **Create Branch**.

Sourcetree will then create a new branch and will “check it out”. Checking out a branch means that the files (and changes to them) associated with that branch will be accessible and editable on your computer.

Double-clicking on a branch in your Sourcetree **Branches** section will check it out. The currently checked out branch will always be marked by a circle to the left of its name.

With your new branch checked out, you are ready to make changes to the documentation.

> **NOTE:** Older repositories may use a **master** branch in place of **main**. The same instructions above apply, just with the different name.

> **WARNING:** Always make sure the correct branch is checked out before proceeding with changes. Do not make changes on the main branch.


## Committing Changes in Sourcetree
Commit small and commit often. Committing saves the current state of your changes to the version control system. It’s as simple as pressing the **Commit** button on the top left of the Sourcetree window.

A new view will open showing pending files you have edited since the last commit. From here:

1. Select the files you’d like to commit by checking them in the Pending files section.
2. Enter a meaningful commit message in the text box at the bottom. A general format to follow is:
   *Jira Issue Number: Description*<br>
   *- Extra Context*<br>
   *- Link to Jira Issue*
3. Check **Push changes immediately to \<remote branch\>**. This option will push your changes to GitHub so others can see and interact with them.
4. Click **Commit**.
5. If any errors occur during the commit or push, Sourcetree will alert you now.

If successful, your changes should now be visible on GitHub in the branch you just pushed to. You can view this branch on GitHub by clicking on the **main** dropdown in the **Code** view as shown below and selecting the desired branch from the options visible to you.

> **WARNING:** If attempting a merge results in a “merge conflict”, contact the Documentation Team for assistance with resolving the issue. If you are authorized to resolve these conflicts, see [Merge Conflicts and Resolving Them *(Internal Document)*](#).


## Synching with the Team
Other members of the team will also push their changes to branches to GitHub on a regular basis. You will want to Pull from the main branch frequently to have access to the latest approved updates to a repository.

It is good practice to merge these pulled updates from main to the branch you are working on before submitting a pull request as covered later in this guide. To do this:

1. Make sure your branch is checked out.
2. Right click **main** and click **Merge main into current branch**.
3. In macOS, the menu option may replace current branch with the actual name of your current branch.
4. Sourcetree will ask you to confirm the merge. Click **OK**.

Now your branch is caught up with any new approved changes currently on main.


## Working with Pull Requests in GitHub
When the work on a branch is complete and pushed to GitHub, it is time to create a pull request to merge it into the main branch. [GitHub’s documentation on creating pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) is a great place to start with understanding how to do this. You may find yourself on the reviewing end of pull requests for others and [GitHub also has documentation on that](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews).


## Next Steps
If you encounter any issues with this guide, please reach out to the Documentation Team and we will be happy to update this page accordingly.
