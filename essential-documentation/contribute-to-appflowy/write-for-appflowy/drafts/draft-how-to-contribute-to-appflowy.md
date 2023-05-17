# \[Draft] How to contribute to AppFlowy


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#introduction">Introduction</a>
      <ul>
        <li><a href="#general-purpose-of-this-article">General Purpose of this Article</a></li>
      </ul>
    </li>
    <li>
      <a href="#how-to-contribute-to-appflowy">How to Contribute to Appflowy</a>
      <ul>
        <li><a href="#how-to-connect-with-the-team">How to Connect with the Team</a></li>
        <li><a href="#how-to-identify-and-solve-your-first-pr">How to identify and solve your first PR</a></li>
        <li><a href="#how-to-propose-new-features-and-changes-for-appflowy">How to propose new features for Appflowy (via GitHub Issues)</a></li>
      </ul>
    </li>
    <li><a href="#an-example-on-how-to-handle-your-first-pr">An Example on how to handle your first PR</a></li>
    <li><a href="#how-to-best-engage-with-the-community">How to best engage with the community</a></li>
    <li><a href="#links-to-resources-to-help-get-started-with-technical-contributions">Links to Resources to help get started with Technical Contributions</a></li>
    <li><a href="#other-initiatives-by-appflowy">Other Initiatives by Appflowy</a></li>
    <li><a href="#conclusion">Conclusion</a></li>
  </ol>
</details>



<!-- Introduction -->
## Introduction
<p>Appflowy is a productivity tool that streamlines note taking and task management. It is open-source, which means that its code is available to everyone for development and customization! Whether you're an aspiring developer, a seasoned programmer, or someone genuinely interested in technology, this guide is here to help you navigate the exciting world of open-source with Appflowy!</p>

### General Purpose of this Article
<p>We will explore the process of contributing to Appflowy and provide practical tips on how to make your first contribution. We'll demystify the process, highlight the benefits, and equip you with the essential tools and resources to get started on your open-source journey with Appflowy.

Throughout this guide, we'll address common questions you may have, such as:

1. How do I contribute to Appflowy?
2. How do I connect with the team?
3. How do I identify and solve my first Pull Request?
4. How do I propose new features for Appflowy?
5. How can I best engage with the community?
  
And many more. Let's dive in!</p>
<p align="right">(<a href="#introduction">back to top</a>)</p>


<!-- How to Contribute -->
## How to Contribute to Appflowy
<p>Appflowy is managed via GitHub, a popular version control system. You'll need a GitHub account to get started. We recommend getting familiar with GitHub's features, especially GitHub Workflows, before starting with contributions.</p>

### How to Connect with the Team
<p>The best ways to connect with the team are via Discord and GitHub. </p> 

1. Discord 
  - Create a Discord account and join the [Appflowy Community Server](https://discord.com/invite/9Q2xaN37tV). Don't be afraid to ask questions!
  - Start by introducing yourself in the <b>Intro's</b> section. Read carefully through the <b>welcome</b> section. You must abide by the server's rules and regulations.
  - If you have any questions, tag the Appflowy Team or Appflowy Contributors by sending a message with a tag (<b>@AppFlowy Team </b>) for the same.

![image](https://user-images.githubusercontent.com/70965472/237025457-bf33e70d-8fbd-4bea-a25e-f1d0ea2147bf.png)
*Welcome Page - Appflowy Dicord Server*

2. GitHub  
  - You can get started by asking questions in the [GitHub Discussions](https://github.com/AppFlowy-IO/AppFlowy/discussions) section of Appflowy.
  - GitHub Discussions provides a forum for Appflowy contributors to ask questions, share ideas, engage with other community members, and subsequently welcome others who join in down the road.

![image](https://user-images.githubusercontent.com/70965472/237032567-9d75b320-423e-4bc2-805d-7bcb7c96217c.png)
*The Appflowy Discussions page*

   - You can navigate through the various categories made available, including announcements, ideas, polls, etc.
   - The [General Help Wanted](https://github.com/AppFlowy-IO/AppFlowy/discussions/categories/general-help-wanted) and [Technical Help Wanted](https://github.com/AppFlowy-IO/AppFlowy/discussions/categories/technical-help-wanted) sections contain open projects for first time contributors.
   - Also, feel free to explore Appflowy's [6 Month Technical Roadmap](https://github.com/AppFlowy-IO/AppFlowy/discussions/1715), to gain a better understanding of Appflowy's current development goals over the course of the next 6 months.

3. Mail 
  - You can get in touch with the team via mail at [support@appflowy.io](support@appflowy.io).


### How to identify and solve your first PR
<p>Contributions are made via Pull Requests (PR's). We recommend getting familiar with <a href="https://docs.github.com/en/get-started/quickstart/github-flow">GitHub Flow</a> and setting up your development environment. Now that you're ready, start looking for a PR to work on. If you need help getting started, look at Appflowy's <a href="https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions">Documentation</a>. The steps are as follows:</p>

  **Step 1:** Go to [Appflowy's repository](https://github.com/orgs/AppFlowy-IO/repositories) section in GitHub. This is a list of all of Appflowy's repositories open for contributions. For the purposes of this article, we shall be looking for Issues within the main [Appflowy](https://github.com/AppFlowy-IO/AppFlowy) repository.
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/715c8a61-af5f-4856-840f-11f8604e765c)
  *Appflowy GitHub Page - with all Open-Source Repositories that can be worked on*
  
  **Step 2:** Go to the <b>Issues</b> section of the repository. It should look something like this:
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/14fdc0e3-1517-40da-9576-4646b0516b36)
  *Issues Section*
  
  **Step 3:** Go to the label subsection, and type in <b>Good First Issue for Devs</b>.
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/f5dedcd1-5f08-483d-9898-6372022060b3)
  *Label subsections within Issues*
  
  **Step 4:** Here, you can go through a list of Issues that can be worked on. They're fairly straightforward and can help you get accustomed to the  development environment as well as the codebase. Feel free to ask anyone from the Appflowy team for suggestions or to assign you to an Issue.
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/e1022103-e98e-42b5-a43d-03f5c5b08f04)
  *Label subsection within Issues*
  
  <p> Issues are generally categorised into either <b>Feature [FR]</b> or <b>Bugs [Bug]</b>. You can take a look at the description provided for the given issue. Send a message down in comments section to get the issue assigned to yourself. Once that's done, you are ready to begin coding!</p>
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/a0c1479d-8c1b-4af8-a766-dbff8ab6c3d4)
  *An example of an issue that can be worked on. Remember to message the maintainers first!*
  
  <p> As mentioned before, we expect you to go about making contributions using the <a href="https://docs.github.com/en/get-started/quickstart/github-flow">GitHub Flow</a> way. That involves some standard steps: </p>
  
1. Creating your own branch within your forked repository
2. Setting up your development environment
3. Making changes to the codebase, in accordance with the requirements and tasks present in the Issue that you have chosen to work on
4. Pushing the changes to your branch, and creating a Pull Request for the same
5. Having a code review for the same, making further changes
6. Passing all the automated tests put in place
7. Handling merge conflicts
8. Merging your branch, and subsequent deletion of the branch once Merge is successfully completed

<p>These are the steps required to handle your first PR.</p>

### How to propose new features and changes for Appflowy
<p>Congratulations on completing your first PR! We're sure this is the first of many contributions from you! As Appflowy is Open Source in nature, it also means that anyone and everyone is free to make recommendations and changes that can help improve Appflowy. If you have any ideas on how to go about doing the same, you can propose them via GitHub Issues. Let us see how:</p>

<b>Step 1:</b> Go to [Appflowy's repository](https://github.com/orgs/AppFlowy-IO/repositories) section on GitHub. Here you can see all of Appflowy's Open-Source repositories that can be contributed to. For the purposes of this article, we shall be looking at the main [Appflowy](https://github.com/AppFlowy-IO/AppFlowy) repository.
<b>Step 2:</b> Click on the <b>New Issue</b> section of the repository. The subsequent page should look something like this:

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/6d1b1efd-eb69-4083-a098-6f9e4117e11c)
*Create New Issues Page*

<b>Step 3:</b> Here, you can choose either to propose a feature change, or address a bug. For the purpose of this article, we shall choose the "Create New Feature" option.
<b>Step 4:</b> On entering the type of issue, you will be redirected to a "Feature Request" form. Fill in all the fields, including the title, a detailed description of what the feature aims to do, its potential impact, and any other additional context needed to better understand the proposed feature. 
<b>Step 5:</b> Click submit, and you're done!

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/cbccc006-7b10-47a8-886c-828352c67319)
*Feature Submit Form*

<p>Congratulations on submitting your first feature!</p>


## An Example on how to handle your first PR

<p> In this section, I shall be highlighting my personal experience with Appflowy, from why I decided to the contribute, the workflow that I followed, and the overall experience of going about Open-Source development.</p>

### Why I decided to contribute to Appflowy

<p> My first contribution for Appflowy came during the GitHub Octernship season. I had heard about the GitHub Octernships through a promotional video that I had found on YouTube. Considering how similar it was to GSOC and other Open-Source iniatives, I was interested to try it out. I registered for the event, and after carefull consideration, decided to choose Appflowy as one of my 4 entries. The initial appeal of Appflowy was clear, it was a productivity tool suite, competing with heavyweights like Notion and Todoist, and most importantly, was Open-Source in nature. That meant a 3rd year Junior like myself could have a shot at development experience, without much hassle. Appflowy is built out of Flutter and Rust, which were completely new to me. But considering the pros of the Octernship program, I decided to enroll anyway. I joined the Appflowy Discord Server, introduced myself, and quickly got down to completing the assignment. This brought me to handling a PR for any first-time issue for Junior Dev's. This was a compulsory part of the Octernship application, which officially started my Open-Source journey with Appflowy. </p>

### How I went about searching for a first time issue

<p> I began by searching for issues on the main Appflowy Repository. I had contributed to minor open-source projects before, and knew how one generally went about contributing to open-source repositories. I entered the words "good-first-issue" in the label bar. I selected the first option, i.e. good first issues for junior devs. This was my first time working on flutter, so I decided it was best that i started out with something easy. I decided to go ahead with issue <a href="https://github.com/AppFlowy-IO/AppFlowy/issues/1059">#1059 - Support markdown to italicize text</a>. The requirements were fairly simple: Add a function to enable italics via use of single asterisks. After going through the codebase, I knew it would just involve copying and editing a pre-existing function that did the same for underscores, and so I decided to go ahead with it.</p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/4f746dfb-0f50-41aa-8c04-e5660cedc5e3)
*A view of the issue that I decided to take on*

<p> I started by asking one of the moderators, if I could work on the issue. The core team got back to me on what I could work on, specifically with respect to the given issue. Once I got assigned the issue, I was ready to get started.</p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/60633c00-bf46-4d19-99a6-775213b0a370)
*Always ask questions - clarify your thoughts, as well as your plans for implementation with the team*

### How I solved it

<p> As mentioned before, it was a fairly straightforward issue, with code already present in the code base that could be reused for the same. However, I had a lot of trouble setting up my development environment. This is a common issue to first-timers, so don't worry if you have trouble setting up your environment as well. I had issues with the unpacking of the cargo files for the Rust Backend. This mostly came down to my Antivirus flagging all the incoming files needed for development. It took a while of troubleshooting, and asking for help from the community, but I was eventually able to figure it out, and get the environment up and ready. Some things that I did to smoothen my onboarding experience included: </p>

- Reading up Appflowy's documentation, and searching for cases where this bug has been encountered before, and how it was dealt with.
- Searching on online platforms for cases where such an error was encountered before. This included combing through popular sites like StackOverflow, other GitHub repositories, BitBucket, etc for any instances where this issue had occured before, and any potential fixes for the same.
- Creating an issue in the Issues tab, and highlighting the exact problem that you faced. I carefully detailed the exact issue that I was facing, including screenshots, error messages, and any other relevent information pertaining to the issue that I was facing. (You can have a look at Issue [#2045](https://github.com/AppFlowy-IO/AppFlowy/issues/2045). This is a fairly good example of how one can approach roadblocks on their development journey).

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/919bfd67-9e32-427e-b817-1ea72c06b0e2)
*An Example of an Issue created to help gain feedback from the community on how to best tackle it*

- Asking on Discord - you may do so on the <b>flutter-101</b> and <b>rust-101</b> channels.

<p> Following these steps helped me successfully fix the issue that I was facing. Also, always document everything that occurs during the lifecycle of an issue resolution within your Issue and PR. These serve well for future contributors who might encounter the same issue down the road. </p>

<p> With the environment up and running, it was down to make the changes needed to fullfill the task at hand. I added the function required, tested it manually in my local environment, and pushed the ensuing commit into my forked repository's branch. I then created a pull request for the same and awaited my first code review. </p>

### How I went about clarifying doubts with the maintainers

<p> As always, feel free to ask doubts and seek suggestions from the maintainers and the core team. You can ask questions related to any feature you'd like to implement, any bug that you've encountered, and so on. </p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/0aa7325a-7212-4df1-ba51-a127471b29d7)
*An example of a community member helping me resolve an issue*

### How I handled code reviews with the team - changes that I made, following conventions, etc.

<p> As a first time contributor to a repository, you will be asked to sign the CLA, i.e. the Contributor Liscence Agreement. You can read more on the same <a href="https://en.wikipedia.org/wiki/Contributor_License_Agreement">here</a>. Once that's done, your Pull Request will be assigned one or more reviewers. They are generally members of the core Appflowy team, or Senior contributors. They know the codebase in and out, so feel free to ask for suggestions on how to tackle any developmental issue that you may face. My reviewers left some suggested changes for the Pull Request, including changing on keyboard conventions and other small changes. </p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/242608e8-6295-4e8c-8d61-7709cb04b4cd)
*An example of a suggested review left by Reviewers during a Code Review of a Pull Request*

<p> Another requirement that was put forward by the team was to make unit tests for the new feature. Unit testing is important as it makes sure that changes made to a codebase do not break other parts of the codebase. I had a horrid time writing these Unit Tests, as I was still very new to Flutter. But as always, feel free to ask for help. </p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/7ab3576c-b392-4b23-8ba6-1aaa7e081dc0)
*Asking for help - just do it!*

<p> Also, make sure you conform to the convention put in place by the team! Be it with Pull Request naming conventions, commit names and descriptions, etc; always follow the naming conventions put in place. For more information on the naming conventions used in Appflowy, check out this <a href="https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/submitting-code/code-submission-guidelines">link</a>. </p>

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/ebd65d9e-70c5-4801-ac53-ff0459ee17f2)
*Make sure you use the naming conventions specified by the Appflowy documentation*

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/c1e546a5-9c97-4682-9b23-a44f9d39c553)
*Ended up having trouble with squashing some commits as well. This really was quite the journey 😅*

<p> Overall, I think I made quite a mess with my first Pull Request. From horrible coding practices, to terrible naming conventions, I had it all! But thanks to the community, I was able to navigate the entire process with relative ease. A big thank you to <a href="https://github.com/Xazin">Xazin</a> and <a href="https://github.com/LucasXu0">LucasXu0</a> for all their help and support. This really is what I admire the most at Appflowy, the <b>Community</b>. So stay hungry, always be open to suggestions, and you'd be surpsised by just how much you can learn while working on a large scaled, open-source collaborative project like Appflowy. </p>

### The final merge request

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/1a57eece-041f-4862-a99f-0bc604179740)
*The first of many more Pull Requests!*

### Things that I learnt through this whole experience

<p> To summarise, here are my key takeaways from the entire experience: </p>

- Be open to suggestions and constructive criticism. We can't learn if we close our minds to change.
- Learn up the languages and frameworks of the codebase! I cannot stress this enough. Try to have a firm understanding on the basics of the frameworks and languages used, namely Flutter and Rust. Feel free to refer to the <a href="#links-to-resources-to-help-get-started-with-technical-contributions">Links to Resources to help get started with Technical Contributions</a> Section down below for the same.
- Follow the conventions and standards put in place. Be it coding or naming conventions, make sure you follow the conventions put in place by the community.
- Feel free to ask questions! But at the same time, make sure you've done your research. Whenever you encounter a roadblock, try Googling up the issue first. Chances are you'd be able to get an answer to your question without having to wait for a community memeber to respond. In case you're truly stuck, do not be afraid to reach out. The community is behind you every step of the way.
- Document everything! Make sure to document any bugs and issues that you faced. These can be useful to future contributors down the road, who may encounter the same.


<p align="right">(<a href="#introduction">back to top</a>)</p>



<!-- How to best engage with the community -->
## How to best engage with the community

<p> Here are some best practises to engage with the community here at Appflowy: </p>

- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

<p>You can report instances of abusive, harassing, or otherwise unacceptable behaviour by emailing the project team at annie@appflowy.io. All complaints will be reviewed and investigated, and will result in a response that is deemed necessary and appropriate to the circumstances. The project team is obligated to maintain confidentiality with regard to the reporter of an incident. Further details of specific enforcement policies may be posted separately.</p>
  
<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Links to Resources to help get started with technical contributions -->
## Links to Resources to Help get Started with Technical Contributions

<p> This might be lot to take in, especially if you're a newcomer. We have curated some links to kickstart your journey with Appflowy. These include documentation for the technologies and frameworks used for maintaining and developing Appflowy. Feel free to read up on anything that might be unfamiliar to you. It goes a long way!</p>

- [Git](https://git-scm.com/)
- [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow)
- [Futter](https://flutter.dev/learn)
- [Rust](https://www.rust-lang.org/learn)
- [Appflowy Doumentation](https://appflowy.gitbook.io/docs/essential-documentation/readme)

<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Other Initiatives by Appflowy -->
## Other Initiatives by Appflowy

<p>Here at Appflowy, we foster learning through various initiatives. It's our goal to help anyone who stops by in their developmental journey as much as possible. With this in mind, here are some initiatives by Appflowy for the same: </>
  
  - Appflowy Mentorship Program - The AppFlowy mentorship program is aimed at creating a hands-on learning opportunity for new developers who may otherwise lack the opportunity to gain exposure to real-world software development and entry into the technical community. Link: [Appflowy Mentorship Program](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/appflowy-mentorship-program/contributor-guidance)
  
  - GitHub Octernships - (Currently Closed)
  
  - Write for Appflowy - Whether you’re an AppFlowy power user, a software development expert, or just a student starting to get into open source, there is knowledge you can share that will benefit the entire AppFlowy community. Click the link below to learn more. Link: [Write for Appflowy](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/write-for-appflowy)

<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Conclusion -->
## Conclusion

<p> To summarise, we were able to understand how to contribute to Appflowy, how to handle that first PR, How to connect with the community, and many others in this article. </p>

<p align="right">(<a href="#introduction">back to top</a>)</p>




<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

