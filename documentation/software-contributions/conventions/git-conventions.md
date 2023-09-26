# 🐙 Git Conventions

The following page describes how you should prepare your code before submitting it for a PR. If you want information on how to create your PR please see [Submitting your first Pull Request](../../../essential-documentation/contribute-to-appflowy/software-contributions/submitting-code/submitting-your-first-pull-request.md).

Before your code is merged into the main branch it will be peer reviewed so that it can be deployed for everyone to use. We go through your PR line by line and make sure that everything is on the up and up. You should always carefully craft your code submission in order for your reviewer to be able to more easily understand your changes.

## Commit message guidelines

We use [commitlint](https://github.com/wagoid/commitlint-github-action) to validate each commit message. It is automatically configured to validate your commit messages when you setup your AppFlowy repo.

The commit message consists of `type`:`subject`

* type must be one of \[build, chore, ci, docs, feat, fix, perf, refactor, revert, style, test]
* no space between type and the colon
* subject is the commit message

**For example:**

* git commit -m "fix: did something"
* git commit -m "feat: did something"
* git commit -m "refactor: did something"

## Committing Process

Make small commits. A commit should be a small chunk of logic that is easy to understand and follow.

Before committing you should do a file compare on every file that you want to commit. Here, you will check to make sure that you are not committing temporary code or test code. You will also check for warnings, code formatting, and unneeded included packages.

Commit often. The process of adding commits keeps track of your progress as you work. Commits also create a transparent history of your work that others can follow to understand what you’ve done and why.

Write clear, concise commit messages. Each commit has an associated commit message, which is a description explaining why a particular change was made.

Make PRs as soon as possible. In an open source project, we all depend on each others code. The faster you get your changes into the main branch, the less chances there are of conflicts.

## Before pushing your code

Before creating your Pull Request you must ensure that your code adheres to the [Broken link](broken-reference "mention").

### No warnings

There must be no warnings in the development or main branches. No developer can check-in code that contains warnings. This is to facilitate finding warnings and errors while **you** are coding. It would be extremely difficult for you to see that your code has warnings if the code base was already polluted with hundreds of warnings.
