# Submitting your first Pull Request

## Thank you for helping out!

So you want to contribute to AppFlowy, that's awesome! Thank you and welcome to the team!

At this point you have already cloned AppFlowy to your local machine as shown in the "Building on XXX" documents that are available in the wiki. You've looked at the code, but haven't made any changes. Now, you want to do some work!

## Terms

Here are the terms that are used when talking about git repositories.

* **repo:** A synonym for repository.
* **origin:** This is name of the git repository instance which is in your GitHub account. A repository in your account may have been created by you, or you may have forked it.
* **forked repo, fork**: An instance of a repository in your GitHub account that was created by using the forking mechanism.
* **upstream:** This is the name of the original project's repository which is located in their GitHub account.
* **cloned repo:** This is the clone that you create on your local machine.
* **local repo:** synonum of **cloned repo**

## Intro

Since changes contributed to open source projects will have to be peer reviewed, it's common to see a workflow which relies on git Pull Requests (PR). PRs are not allowed from a repository that is cloned directly from the original project. In order to create a PR you must fork the project and then clone your fork. This process will be explained below. If you have cloned AppFlowy without forking first, you will have to restart the process.

## Relationships between repositories

Working on an open source project can get a little complicated for new users. There are 3 code repositories that are involved in the process: AppFlowy's repo, Your GitHub fork, and your cloned repository on your local computer. You can see the location and links between these repositories in the following diagram :

\[\[https://github.com/AppFlowy-IO/appflowy/blob/main/doc/imgs/cloned\_repository.png|alt=Cloned Repository img]]

## Initial Project setup

The steps in this section only need to be performed once in order to contribute to AppFlowy. You will have to repeat these steps to contribute to a different project.

Here are the steps to follow to create and maintain a healthy fork and contribute to AppFlowy periodically.

1. Create a fork of the AppFlowy project.
   * You must work on your fork of the project rather than on a cloned repository pointing to AppFlowy's repository. In order to fork AppFlowy go to the [AppFlowy repository](https://github.com/AppFlowy-IO/appflowy) on GitHub, click on "Fork" and choose a suitable GitHub account for the fork eg. your personal Github account.
2.  Clone the fork you just created onto your development machine

    * In your GitHub account, in your Fork of AppFlowy, go the the "<> Code" tab which is in the upper left corner.
    * Once there, click on the green "Code" button and a dropdown will appear.
    * In the dropdown you will see choices for "HTTPS", "SSH", "GitHub CLI". We recommend using SSH, but that is beyound the scope of this tutorial. So we will be using HTTPS for simplicity. Click on HTTPS.
    * You will see the link to your Fork. Click on the icon with two boxes to copy that URL to your clipboard.
    * In a terminal, go to your preferred directory for code.
    * Clone the Fork to your local machine:

    ```shell
    git clone [URL TO YOUR FORK]
    ```

    * and cd into that directory:

    ```shell
    cd appflowy
    ```
3. Add the original project repo as an upstream repository in your forked project:

```shell
git remote add upstream https://github.com/AppFlowy-IO/appflowy.git
```

The AppFlowy project repo is now referred to as "upstream" Your GitHub project is now referred to as "origin"

\[\[https://github.com/AppFlowy-IO/appflowy/blob/main/doc/imgs/add\_remote\_repository.png|alt=Add Remote Repository img]]

You're all setup! Now, it's time to start working on some code!

## A complete flow of the PR process

This is the process to use for every feature or bug fix that you want to propose to AppFlowy:

### Synchronize your repositories

1.  Before starting your work always make sure the main branch of your local repo is synchronized with the main branch of AppFlowy's repository (upstream):

    * Swith to the main branch on your computer.

    ```shell
    git checkout main
    ```

    * Get all the new changes from AppFlowy's repository. This command will download the all the changes in the AppFlowy repository, but will not merge them into your code.

    ```shell
    git fetch upstream
    ```

    * Merge the new changes into your code. This might cause conflicts, resolving conflicts is beyond the scope of this document.

    ```shell
    git merge upstream/main
    ```

    * Update your GitHub repository (origin) with the new changes

    ```shell
    git push origin main
    ```

Now, all three repositories are synched! We're ready to start our bug fix.

### Setup a feature branch

1.  Create a new branch in your local project for the fixes that you want to contribute to AppFlowy. This branch is referred to as a "feature branch". You should make a branch name that is short, descriptive, and unique. Some examples of good branch names are _fix-install_, _docs-cleanup_, and _add-travis-ci_. Some examples of bad branch names are _feature_, _fix_, and _patch_. You should add the issue number if applicable. In this case we're going to fix issue #180.

    * This command will create a branch in your local repository only. The command will also switch to that branch.

    ```shell
    git checkout -b fix_setup_page_180
    ```

    * Now push that branch to your origin repository.

    ```shell
    git push origin fix_setup_page_180
    ```

### Work on the code

Work in your new branch (eg. fix\_setup\_page\_180) and commit your changes as normal. You can commit as many times as you want but don't leave uncommited changes in the branch. As you are working on your code you may want to periodically update your local repo with any changes that have been added to the AppFlowy upstream repo. This will hopefully save you from any future merge conflicts. See below.

### Keep your local repository up to date

**Imporant.** While you were working on your fixes the original upstream project repository might have changed (due to other contributors working on it). So you'll have bring in those changes by rebasing your current feature branch. In other words you need to replay your fixes on top of the latest work from upstream repo main branch to make sure your commits are still compatible with the latest commits in upstream. The follwing command will result in a fast-forward merge for the pull request which is what we want:

```shell
git checkout fix_setup_page_180
```

```shell
git pull --rebase upstream main
```

This can result in conflicts but this is normal. Fixing these conflicts is part of the process (this happens more often on very active projects.) Fixing conflicts is outside of the scope of this document.

### Keep your origin repository up to date

After you have applied your fixes on top of the latest version of upstream main, it's now time to update your origin repo. Since the pull requests are initiated from your forked repository on Github you want to keep that one in sync too:

```shell
git push origin fix_setup_page_180
```

### Create your PR

Finally, go to the [AppFlowy repository](https://github.com/AppFlowy-IO/appflowy) on GitHub and click on "Pull Request".

Upon doing this, you will be presented with a page. This page will show you the diff of the changes you made. Double check them to make sure you are making a pull request against the right branch.

Things to check here are that the base fork is the upstream repo and the branch for the upstream repo is main, and that the head fork is your fork and the branch is the branch you wish to make the pull request from (fix\_setup\_page\_180).

Enter a descriptive title in the title field. This is very important, as it is what will show up in the pull request listing and in email notifications to the people in the repo. Pull Requests with undescriptive titles are more likely to be passed by. If the pull request fixes an issue, we recommend putting the issue number in the pull request description, not the title. People generally do not know issues by number, so a pull request that is just titled "fix for issue #180" is more likely to be passed by, as it is unclear what it does from the title.

If there is more description or discussion about the pull request than what fits in the title field use the description field.

If the pull request fixes an issue, you can add "fixes #180" (replace 180 with the actual issue number) in the pull request description. This exact format, "fixes #180" is important, as it will cause GitHub to automatically close the issue when the pull request is merged.

Your PR is now sent to AppFlowy where we will review your code and supply with you with any comments and suggestions to have to be applied to your code in order for it to be merged in the AppFlowy project.

### React to Pull Requests comments

Once you have created the pull request, it will likely be reviewed and some additional fixes will be necessary. **Do not create a new pull request**. Rather, simply make more commits to your branch and push them to your origin repo. They will be added to the pull request automatically. Here are the steps to follow if the AppFlowy project maintainers have made any comments on your code:

1.  Update your local repository. Maybe a few days have passed since you worked on the project. So you want to make sure that your local repo is up to date.

    * Make sure you are on the correct branch

    ```shell
    git checkout fix_setup_page_180
    ```

    * Get the changes from upstream.

    ```shell
    git pull --rebase upstream main
    ```
2. Make the required changes in your branch, as normal.
3. Once you are happy with your changes, push them to your origin repository, this will automatically update your PR.

```shell
git push origin fix_setup_page_180
```

Repeat this process until the changes are accepted and merged.

### After your PR has been merged.

Congratulations!! And thank you for contributing to AppFlowy!

1.  Now you can get rid of your old fix branches that have already been merged into the code (otherwise you'll have tons of useless branches in your project). You can take a look at your local branches by issuing the following command

    ```shell
    git branch
    ```
2.  If in that list you find a branch that has already been merged with the upstream project then you can delete it:

    * Delete it locally

    ```shell
    git branch -D fix_setup_page_180
    ```

    * Delete it from your origin repository

    ```shell
    git push origin --delete fix_setup_page_180
    ```

That's it. The complete story of how to work on code in separate branches, update repositories, make and finish PRs. You're now a PR PRo! :D

We hope that you have fun working on AppFlowy and we look forward to working together with you.

This document was heavily based on [this stack overflow article](https://stackoverflow.com/questions/20956154/whats-the-workflow-to-contribute-to-an-open-source-project-using-git-pull-reque)
