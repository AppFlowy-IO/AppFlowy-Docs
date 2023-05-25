# \[Draft] How to Contribute to AppFlowy

<!-- TABLE OF CONTENTS -->

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#introduction">Introduction</a>
    </li>
    <li>
  		<a href="#before-you-get-started">Before You Get Started</a>
    </li>
    <li>
      <a href="#how-to-connect-with-the-team">How to Connect With the Team</a>
    </li>
    <li>
      <a href="#how-to-identify-and-resolve-your-first-pr">How to Identify and Resolve Your First PR</a>
    </li>
    <li>
      <a href="#how-to-propose-new-features-and-changes-for-appflowy">How to Propose New Features for Appflowy (Via Github Issues)</a>
    </li>
    <li><a href="#my experience-handling-my-first-pr">My Experience Handling First PR</a></li>
    <li><a href="#how-to-best-engage-with-the-community">How to Best Engage With the Community</a></li>
    <li><a href="#resources-for-getting-started-with-technical-contributions">Resources for Getting Started With Technical Contributions</a></li>
    <li><a href="#other-initiatives-by-appflowy">Other Initiatives by Appflowy</a></li>
    <li><a href="#conclusion">Conclusion</a></li>
  </ol>
</details>




<!-- Introduction -->
## Introduction
<p>AppFlowy is a productivity tool that streamlines note-taking and task management.
This is an open-source project, which means that its code is available to everyone for development and customization! 

Whether you're an aspiring developer, a seasoned programmer, or someone genuinely interested in technology, this guide is here to help you navigate the exciting world of open source development with AppFlowy!

### Overview
<p>We will explore the process of contributing to AppFlowy and provide practical tips on how to make your first contribution. 


We'll demystify the process, highlight the benefits, and equip you with the essential tools and resources to get started on your open-source journey with AppFlowy.


Throughout this guide, we'll address common questions you may have, such as:

1. How do I contribute to AppFlowy?
2. How do I connect with the team?
3. How do I identify and solve my first Pull Request?
4. How do I propose new features for AppFlowy?
5. How can I best engage with the community?

Let's dive in!
<p align="right">(<a href="#introduction">back to top</a>)</p>


<!-- How to Contribute -->
## Before You Get Started
If you are new to open source development, this document will guide you through the process.

If you've worked on open source projects before, much of this will seem familiar to you. However, we still reccomend you review this guide to make sure you are adhering to our processes and conventions.

AppFlowy is managed via GitHub, a popular version control system. 

You'll need a [GitHub account](https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account) to get started. 

We recommend getting familiar with GitHub's features, especially [GitHub Workflows](https://docs.github.com/en/actions/using-workflows), before starting with contributions.

Please also familiarize youself with the AppFlowy [Style Guide](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/submitting-code/style-guides) and 
[Code Submission Guidelines](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/submitting-code/code-submission-guidelines) before you submit your code.

## How to Connect With the Team
The best ways to connect with the team are via **Discord** and **GitHub**.

### Using Discord to Connect With the Team

Create a Discord account and join the [AppFlowy Community Server](https://discord.com/invite/9Q2xaN37tV). 

  - Start by introducing yourself in the <b>intros</b> channel. 
  - Read carefully through the <b>welcome</b> channel. You must abide by the server's rules and regulations.

Don't be afraid to ask questions!  If you have any questions, tag the AppFlowy Team or AppFlowy Contributors by sending a message with a tag (<b>@AppFlowy Team </b>) for the same.

![image](https://user-images.githubusercontent.com/70965472/237025457-bf33e70d-8fbd-4bea-a25e-f1d0ea2147bf.png)
*Welcome Page - AppFlowy Dicord Server*

### Using GitHub to Connect With the Team

You can get started by asking questions in the [GitHub Discussions](https://github.com/AppFlowy-IO/AppFlowy/discussions) section of AppFlowy.

GitHub Discussions provides a forum for AppFlowy contributors to ask questions, share ideas, engage with other community members, and subsequently welcome others who join in down the road.

![image](https://user-images.githubusercontent.com/70965472/237032567-9d75b320-423e-4bc2-805d-7bcb7c96217c.png)
*The AppFlowy Discussions Page*

   - Navigate through the various categories, including announcements, ideas, polls, etc.
   - Use the [General Help Wanted](https://github.com/AppFlowy-IO/AppFlowy/discussions/categories/general-help-wanted) and [Technical Help Wanted](https://github.com/AppFlowy-IO/AppFlowy/discussions/categories/technical-help-wanted) sections to find open projects for first time contributors.
   - Explore AppFlowy's [6 Month Technical Roadmap](https://github.com/AppFlowy-IO/AppFlowy/discussions/1715) to gain a better understanding of AppFlowy's current development goals over the course of the next 6 months.

### Using Email to Connect With the Team

You can get in touch with the team via email at [support@appflowy.io](support@appflowy.io).


## How to Identify and Resolve Your First PR
Contributions are made via Pull Requests (PR's).

We recommend getting familiar with the <a href="https://docs.github.com/en/get-started/quickstart/github-flow">GitHub flow</a> for collaborating on projects and setting up your development environment.

Once you're ready, start looking for a PR to work on. If you need help getting started, look at AppFlowy's <a href="https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions">Documentation</a>.

### Finding an Issue to Work On

**Step 1:** Go to [AppFlowy's repository](https://github.com/orgs/AppFlowy-IO/repositories) section on GitHub. This is a list of all of AppFlowy's repositories open for contributions. For the purposes of this article, we shall be looking for *Issues* within the main [AppFlowy](https://github.com/AppFlowy-IO/AppFlowy) repository.

  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/715c8a61-af5f-4856-840f-11f8604e765c)
  *AppFlowy Github Page - With all open-source repositories that can be worked on*

**Step 2:** Go to the *Issues* section of the repository. It should look something like this:

  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/14fdc0e3-1517-40da-9576-4646b0516b36)
  *Issues Section*

 **Step 3:** Go to the label subsection, and type in "Good First Issue for Devs"

  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/f5dedcd1-5f08-483d-9898-6372022060b3)
  *Label Subsections Within Issues*

**Step 4:** Here, you can go through a list of *Issues* that can be worked on. They're fairly straightforward and can help you get accustomed to the development environment as well as the codebase. 

Feel free to ask anyone from the AppFlowy team for suggestions or to assign you to an Issue.

  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/e1022103-e98e-42b5-a43d-03f5c5b08f04)
  *Good First Issue for Devs*

Issues are generally categorized into either a <b>Feature [FR]</b> or a <b>Bug [Bug]</b>. You can take a look at the description provided for the given issue. 

Send a message down in the comments section to get the issue assigned to yourself. Once that's done, you are ready to begin coding!

  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/a0c1479d-8c1b-4af8-a766-dbff8ab6c3d4)
  *An example of an issue that can be worked on. Remember to message the maintainers first!*

### Working on Your Issue

As mentioned previously, we expect you to make contributions using the <a href="https://docs.github.com/en/get-started/quickstart/github-flow">GitHub Flow</a> workflow.

That means following these standard steps:

1. Create your own branch within your forked repository
2. Set up your development environment
3. Make changes to the codebase in accordance with the requirements and tasks present in the *Issue* that you have chosen to work on
4. Add unit tests for any new features as necessary
5. Push the changes to your branch and creating a Pull Request for the same
6. Ask for a code review for your PR and make changes as required
7. Pass all the automated tests that have been put in place
8. Handle merge conflicts
9. Wait for approval from the AppFlowy team, once approved merge your branch
10. Delete your branch once the PR has been merged

Congratulations on completing your first PR!

## How to Propose New Features and Changes for AppFlowy
You can propose your own ideas for improving AppFlowy. Below is a walkthrough on how to do so using GitHub Issues:

<b>Step 1:</b> Go to [AppFlowy's repository](https://github.com/orgs/AppFlowy-IO/repositories) section on GitHub. Here you can see all of Appflowy's Open-Source repositories to which you may contribute. For the purposes of this article, we shall be looking at the main [AppFlowy](https://github.com/AppFlowy-IO/AppFlowy) repository.

<b>Step 2:</b> Click on the "New Issue" section of the repository. The subsequent page should look something like this:

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/6d1b1efd-eb69-4083-a098-6f9e4117e11c)
*Create New Issues Page*

<b>Step 3:</b> Here, you can choose either to propose a feature change, or address a bug. For the purpose of this article, we shall choose the "Create New Feature" option.

<b>Step 4:</b> On entering the type of issue, you will be redirected to a "Feature Request" form. 

Fill in all the fields, including:

* the title
* a detailed description of what the feature aims to do
* its potential impact
* any other additional context needed to better understand the proposed feature. 

<b>Step 5:</b> Click "Submit new issue" and you're done!

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/cbccc006-7b10-47a8-886c-828352c67319)
*Feature Submit Form*

<p>Congratulations on submitting your first feature!</p>


## My Experience Handling My First PR

In this section, I will highlight my personal experience with AppFlowy, from why I decided to contribute, the workflow that I followed, and the overall experience of going about Open-Source development.

### Why I Decided to Contribute to AppFlowy

My first contribution for AppFlowy came during the GitHub Octernship season. I had heard about the GitHub Octernships through a promotional video that I had found on YouTube. 

Considering how similar it was to GSOC and other Open Source initiatives, I was interested in trying it out. I registered for the event, and after careful consideration, decided to choose AppFlowy as one of my four entries. 

The initial appeal of AppFlowy was clear, it was a productivity tool suite, competing with heavyweights like Notion and Todoist, and most importantly, it was Open Source in nature. That meant a third-year junior like myself could have a shot at development experience, without much hassle. 

AppFlowy is built out of Flutter and Rust, which were completely new to me. But considering the pros of the Octernship program, I decided to enroll anyway. I joined the AppFlowy Discord Server, introduced myself, and quickly got down to completing the assignment. 

This brought me to handling a PR for any first-time issue for Junior Dev's. This was a compulsory part of the Octernship application, which officially started my Open Source journey with AppFlowy.

### Searching for My First Issue

I began by searching for issues on the main AppFlowy repository. 

I had contributed to minor open-source projects before, and knew how one generally went about contributing to open-source repositories. I entered the words "good-first-issue" in the label bar and selected the first option, i.e., good first issues for junior devs. 

This was my first time working with Flutter, so I decided it was best that I started out with something easy. I decided to go ahead with issue <a href="https://github.com/AppFlowy-IO/AppFlowy/issues/1059">#1059 - Support markdown to italicize text</a>. 

The requirements were fairly simple: *Add a function to enable italics via use of single asterisks.* 

After going through the codebase, I knew it would just involve copying and editing a pre-existing function that did the same for underscores, so I decided to go ahead with it.

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/4f746dfb-0f50-41aa-8c04-e5660cedc5e3)
*A view of the issue that I decided to take on*

<p> I started by asking one of the moderators if I could work on the issue. The core team got back to me on what I could work on, specifically with respect to the given issue. Once I got assigned the issue, I was ready to get started.</p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/60633c00-bf46-4d19-99a6-775213b0a370)
*Always Ask Questions - Clarify your thoughts, as well as your plans for implementation with the Team*

### How I Solved It

As mentioned before, it was a fairly straightforward issue, with code already present in the codebase that could be reused for the same. 

However, I had a lot of trouble setting up my development environment. This is a common issue for first-timers, so don't worry if you have trouble setting up your environment as well. 

I had issues with the unpacking of the cargo files for the Rust backend. This mostly came down to my antivirus flagging all the incoming files needed for development.

It took a while of troubleshooting, and asking for help from the community, but I was eventually able to figure it out and get the environment up and running.

 Some things that I did to smoothen my onboarding experience included:

- Reading up on AppFlowy's documentation and searching for cases where this bug has been encountered before, and how it was dealt with.
- Searching on online platforms for cases where such an error was encountered before. This included combing through popular sites like StackOverflow, other GitHub repositories, BitBucket, etc. for any instances where this issue had  occurred before, and any potential fixes for the same.
- Creating an issue in the Issues tab and highlighting the exact problem that I faced. I carefully detailed the exact issue that I was facing, including screenshots, error messages, and any other relevent information pertaining to the issue that I was facing. (You can have a look at Issue [#2045](https://github.com/AppFlowy-IO/AppFlowy/issues/2045). This is a fairly good example of how one can approach roadblocks on their development journey).

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/919bfd67-9e32-427e-b817-1ea72c06b0e2)
*An example of an issue created to help gain feedback from the community on how to best tackle it*

- Asking on Discord - you may do so on the <b>flutter-101</b> and <b>rust-101</b> channels.

Following these steps helped me successfully fix the issue that I was facing.

Also, *always document* everything that occurs during the lifecycle of an issue resolution within your Issue and PR. Doing so will help future contributors who might encounter the same issue down the road.

With the environment up and running, it was time to make the changes needed to fullfill the task at hand. 

I added the function required, tested it manually in my local environment, and pushed the ensuing commit into my forked repository's branch. I then created a pull request for the same and awaited my first code review.

### Clarifying Doubts With Maintainers

<p> As always, feel free to ask questions when you have doubts and seek suggestions from the maintainers and the core team. You can ask questions related to any feature you'd like to implement, any bug that you've encountered, and so on. </p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/0aa7325a-7212-4df1-ba51-a127471b29d7)
*An example of a community member helping me resolve an issue*

### How I Handled Code Reviews With the Team

As a first-time contributor to a repository, you will be asked to sign the CLA, i.e., the [Contributor Liscence Agreement](https://en.wikipedia.org/wiki/Contributor_License_Agreement).

Once that's done, your Pull Request will be assigned one or more reviewers. They are generally members of the core AppFlowy team or senior contributors. They know the codebase in and out, so feel free to ask for suggestions on how to tackle any developmental issue that you may face.

My reviewers left some suggested changes for the Pull Request, including changing keyboard conventions and other small changes. 

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/242608e8-6295-4e8c-8d61-7709cb04b4cd)
*An example of a suggested review left by reviewers during a dode review of a pull request*

<p> Another requirement that was put forward by the team was to make unit tests for the new feature.</p>
<p>Unit testing is important as it makes sure that indvidual changes made to a codebase function as intended. I had a horrid time writing these unit tests, as I was still very new to Flutter. But as always, feel free to ask for help. </p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/7ab3576c-b392-4b23-8ba6-1aaa7e081dc0)
*Asking for help - just do it!*

Always make sure you conform to the conventions put in place by the team such as:

 * Pull Request naming conventions
 * Following commit message guidelines
 * Eliminating warnings and TODOs

For more information on the naming conventions used in AppFlowy, check out our <a href="https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/submitting-code/code-submission-guidelines">code submission guidelines</a>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/ebd65d9e-70c5-4801-ac53-ff0459ee17f2)
*Make sure you use the naming conventions specified by the AppFlowy documentation*

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/c1e546a5-9c97-4682-9b23-a44f9d39c553)
*Ended up having trouble with squashing some commits as well. This really was quite the journey 😅*

Overall, I think I made quite a mess with my first Pull Request. From horrible coding  practises to terrible naming conventions, I had it all!

But thanks to the community, I was able to navigate the entire process with relative ease. A big thank you to <a href="https://github.com/Xazin">Xazin</a> and <a href="https://github.com/LucasXu0">LucasXu0</a> for all their help and support.

This really is what I admire the most at AppFlowy: the **Community**. 

So stay hungry, always be open to suggestions, and you'll be  surprised by just how much you can learn while working on a large-scale, open-source collaborative project like AppFlowy.

### The Final Merge Request

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/1a57eece-041f-4862-a99f-0bc604179740)
*The first of many more Pull Requests!*

### Things That I Learnt Through This Whole Experience

<p> To summarize, here are my key takeaways from the entire experience: </p>

- Be open to suggestions and constructive criticism. We can't learn if we close our minds to change.
- Learn the languages and frameworks of the codebase! I cannot stress this enough. Try to have a firm understanding of the basics of the frameworks and languages used, namely Flutter and Rust. Feel free to refer to the Section <a href="#resources-for-getting-started-with-technical-contributions">Resources for Getting Started With Technical Contributions</a> below for the same.
- Follow the conventions and standards put in place. Be it coding or naming conventions, make sure you follow the conventions put in place by the community.
- Feel free to ask questions! But at the same time, make sure you've done your research. Whenever you encounter a roadblock, try Googling the issue first. Chances are, you'd be able to get an answer to your question without having to wait for a community member to respond. In case you're truly stuck, do not be afraid to reach out. The community is behind you every step of the way.
- Document everything! Make sure to document any bugs and issues that you encounter. These can be useful to future contributors down the road, who may encounter the same.


<p align="right">(<a href="#introduction">back to top</a>)</p>



<!-- How to best engage with the community -->
## How to Best Engage With the Community

Here are some best practices to engage with the community here at AppFlowy:

- Use welcoming and inclusive language
- Be respectful of differing viewpoints and experiences
- Gracefully accept constructive criticism
- Focus on what is best for the community
- Show empathy towards other community members

You can report instances of abusive, harassing, or otherwise unacceptable behaviour by emailing the project team at annie@appflowy.io. 

All complaints will be reviewed and investigated,  resulting in a response that is deemed necessary and appropriate to the circumstances. The project team is obligated to maintain confidentiality with regard to the reporter of an incident. Further details of specific enforcement policies may be posted separately.

<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Links to Resources to help get started with technical contributions -->
## Resources For Getting Started With Technical Contributions

This might be a lot to take in, especially if you're a newcomer. 

We have curated some links to kickstart your journey with AppFlowy. These include documentation for the technologies and frameworks used for maintaining and developing AppFlowy. 

Feel free to read up on anything that might be unfamiliar to you. It goes a long way!

- [Git](https://git-scm.com/)
- [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow)
- [Flutter](https://flutter.dev/learn)
- [Rust](https://www.rust-lang.org/learn)
- [AppFlowy Doumentation](https://appflowy.gitbook.io/docs/essential-documentation/readme)

<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Other Initiatives by Appflowy -->
## Other Initiatives by AppFlowy

Here at AppFlowy, we foster learning through various initiatives. It's our goal to help anyone who stops by in their developmental journey as much as possible. 

With this in mind, here are some initiatives by AppFlowy for the same:


  - The [AppFlowy Mentorship Program](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/appflowy-mentorship-program/contributor-guidance) is aimed at creating a hands-on learning opportunity for new developers who may otherwise lack the opportunity to gain exposure to real-world software development and entry into the technical community.
  
  - GitHub Octernships - (Currently Closed)
  
  - The [Write for Appflowy](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/write-for-appflowy) initiative allows you to share your knowledge to benefit the entire AppFlowy community, whether you’re an AppFlowy power user, a software development expert, or just a student starting to get into open source.

<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Conclusion -->
## Conclusion

You should now be well-equipped to embark on your own open source journey. By following the guidelines in this article, you will be able to successfully resolve pull requests and engage meaningfully with other project contributors.

We hope you participate in AppFlowy's development and make an impact either through coding, bug reporting, feature suggestions, documentation. Contributing to this project and building relationships within the AppFlowy community not only fosters collaboration but also offers opportunities for learning and growth.

We invite you to start contributing to AppFlowy right away by selecting an [[issue to work on](https://github.com/AppFlowy-IO/AppFlowy/issues)](https://github.com/AppFlowy-IO/AppFlowy/issues).

Happy Coding!

<p align="right">(<a href="#introduction">back to top</a>)</p>




<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

