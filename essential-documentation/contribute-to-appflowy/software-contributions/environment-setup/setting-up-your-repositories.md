# 🏦 Setting Up Your Repositories



## Intro

Since changes contributed to open source projects will have to be peer reviewed, it's common to see a workflow which relies on git Pull Requests (PR). PRs are not allowed from a repository that is cloned directly from the original project. In order to create a PR you must fork the project and then clone your fork. This process will be explained below. If you have cloned AppFlowy without forking first, you will have to restart the process.

## Terms

Here are the terms that are used when talking about git repositories.

* **repo:** A synonym for repository.
* **origin:** This is name of the git repository instance which is in your GitHub account. A repository in your account may have been created by you, or you may have forked it.
* **forked repo, fork**: An instance of a repository in your GitHub account that was created by using the forking mechanism.
* **upstream:** This is the name of the original project's repository which is located in their GitHub account.
* **cloned repo:** This is the clone that you create on your local machine.
* **local repo:** synonum of **cloned repo**

## Relationships between repositories

Working on an open source project can get a little complicated for new users. There are 3 code repositories that are involved in the process: AppFlowy's repo, Your GitHub fork, and your cloned repository on your local computer. You can see the location and links between these repositories in the following diagram :

![](https://github.com/AppFlowy-IO/appflowy/raw/main/doc/imgs/cloned\_repository.png)

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

![](https://github.com/AppFlowy-IO/appflowy/raw/main/doc/imgs/add\_remote\_repository.png)

You're all setup! Now, it's time to start working on some code!
