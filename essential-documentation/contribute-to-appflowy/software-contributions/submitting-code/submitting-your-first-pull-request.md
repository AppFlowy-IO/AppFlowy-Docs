# ⤴ Submitting your first Pull Request

## Thank you for helping out!

So you want to contribute to AppFlowy, that's awesome! Thank you and welcome to the team!

At this point you have already forked the AppFlowy and cloned it to your local machine as described in the [Setting Up Your Repositories](setting-up-your-repositories.md) document. You've looked at the code, but you haven't made any changes. Now, you want to do some work!

## A complete flow of the PR process

This is the process to use for every feature or bug fix that you want to propose to AppFlowy:

### Synchronize your repositories

1.  Before starting your work always make sure the main branch of your local repo is synchronized with the main branch of AppFlowy's repository (upstream):

    * Switch to the main branch on your computer.

    ```shell
    git checkout main
    ```

    * Get all the new changes from AppFlowy's repository. This command will download all the changes in the AppFlowy repository, but will **not** merge them into your main branch.

    ```shell
    git fetch upstream
    ```

    * Merge the new changes into your main branch. This might cause conflicts, resolving conflicts is beyond the scope of this document.

    ```shell
    git merge upstream/main
    ```

    * Update your Github repository (origin) with the new changes

    ```shell
    git push origin main
    ```

Now, all three repositories are synced! We're ready to start our bug fix.

### Setup a feature branch

1.  Create a new branch in your local project for the fixes that you want to contribute to AppFlowy. This branch is referred to as a "feature branch". You should choose a branch name that is short, descriptive, and unique. Some examples of good branch names are _fix-install_, _docs-cleanup_, and _add-travis-ci_. Some examples of bad branch names are _feature_, _fix_, and _patch_. You should add the issue number if applicable. In this case we're going to fix issue #180.

    * This command will create a branch in your local repository only. The command will also switch to that branch.

    ```shell
    git checkout -b fix_setup_page_180
    ```

    * Now push that branch to your origin repository.

    ```shell
    git push origin fix_setup_page_180
    ```

### Work on the code

You will loop through the following actions over and over until your fix is finished

1. Work on your code
2. Commit
3. Keep your local repository up to date
4. Keep your origin repository up to date

#### Work on your code

Work in your new branch (eg. fix\_setup\_page\_180) and commit your changes as normal. You can commit as many times as you want but don't leave uncommitted changes in the branch. As you are working on your code you may want to periodically synchronize your local repo with any changes that have been added to the AppFlowy upstream repo. This will hopefully save you from any future merge conflicts. See below.

#### Commit

1. Commit often

#### Keep your local repository up to date

**Important.** While you were working on your fixes the original upstream project repository might have changed (due to other contributors working on it). So you'll have to bring in those changes by rebasing your current feature branch. In other words you need to replay your fixes on top of the latest work from upstream repository to make sure your commits are still compatible with the latest commits upstream. The following command will result in a fast-forward merge for the pull request which is what we want:


```bash
git checkout fix_setup_page_180
```

```shell
git pull --rebase upstream main
```

This can result in conflicts but this is normal. Fixing these conflicts is part of the process (this happens more often on very active projects.) Fixing conflicts is outside of the scope of this document.

#### Keep your origin repository up to date

After you have applied your fixes on top of the latest version of upstream main, it's now time to update your origin repository. Since the pull requests are initiated from your forked repository on Github you want to keep that one in sync too:

```shell
git push origin fix_setup_page_180
```

#### Return to Work on your code :)



### Push commits to your repository

When you have completed your code changes, you can now push your code to your origin repository.

```bash
git push origin fix_setup_page_180
```

Your code is now in your origin repository and ready to send to AppFlowy.

### Create your PR

Finally, go to the [AppFlowy repository](https://github.com/AppFlowy-IO/appflowy) on GitHub and click on "Pull Request".

Upon doing this, you will be presented with a page that will show you the differences of the changes you made. Double check them to make sure you are making right pull request against the correct branch.

Things to check here are that the base fork is the upstream repo and the branch for the upstream repo is main, and that the head fork is your fork and the branch is the branch you wish to make the pull request from (fix\_setup\_page\_180).

Enter a descriptive title in the title field. This is very important, as it is what will show up in the pull request listing and in email notifications to the people in the repo. Pull Requests with undescriptive titles are more likely to be passed by. If the pull request fixes an issue, put the issue number in the pull request description, not the title. People generally do not know issues by number, so a pull request that is just titled "fix for issue #180" is more likely to be passed by, as it is unclear what it does from the title.

If there is more description or discussion about the pull request than what fits in the title field use the description field.

If the pull request fixes an issue, you should add "fixes #180" (replace 180 with the actual issue number) in the pull request description. This exact format, "fixes #180" is important, as it will cause Github to automatically close the issue when the pull request is merged.

Your PR is now sent to AppFlowy where we will review your code and supply with you with any comments and suggestions that have to be applied to your code in order for it to be merged in the AppFlowy project.

### All PRs must be peer reviewed

Every PR that is submitted will be reviewed by one or more AppFlowy maintainers. This is to ensure that there aren't any typos or mishaps in the code as the benefits of code review are widely accepted as a quality improvement and control strategy. Peer review contributes a measure of quality control practices to software development by allowing teams to review their development artifacts early and often. Open source software projects such as AppFlowy know this first hand! As we deal with the constraints presented by tight budgets and constantly rotating staff of developers all based in different time zones. We consistently experience the development challenges exacerbated by geographically dispersed and virtual teams. In our situation, the ability to review our code collaboratively breaks down the silos of isolation and helps everyone better understand the state of the project.

### Keep the main branch prestine

AppFlowy is a Continuous Integration project which means that the anyone can clone the HEAD of the main branch at any time and the application must be in working order. Therefore, the main branch must never be in an error state, it must always be deployable and in running order. A PR that does not pass the CI tests as well as peer review will not be merged into the main branch.

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

This document was heavily based on [this Stack Overflow article](https://stackoverflow.com/questions/20956154/whats-the-workflow-to-contribute-to-an-open-source-project-using-git-pull-reque)
