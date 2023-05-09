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
        <li><a href="#an-example-on-how-to-handle-your-first-pr">An Example on how to handle your first PR</a></li>
      </ul>
    </li>
    <li><a href="#how-to-best-engage-with-the-community">How to best engage with the community</a></li>
    <li><a href="#links-to-resources-to-help-get-started-with-technical-contributions">Links to Resources to help get started with Technical Contributions</a></li>
    <li><a href="#other-initiatives-by-appflowy">Other Initiatives by Appflowy</a></li>
    <li><a href="#conclusion">Conclusion</a></li>
  </ol>
</details>



<!-- Introduction -->
## Introduction
<p>Hey there! In this article, we shall discuss how to contribute to Appflowy. Appflowy is a productivity tool that can be used to help individuals or teams accomplish tasks efficiently and effectively. It is open-source in nature, which means that it's code is freely available to all for developemnt and customization! Whether you're an aspiring developer, a seasoned programmer, or someone with a genuine interest in technology, this guide is here to help you navigate the exciting world of open-source with Appflowy!</p>

### General Purpose of this Article
<p>We will explore the ins and outs of contributing to Appflowy and provide you with practical tips on how to make your first contribution. We'll demystify the process, highlight the benefits, and equip you with the essential tools and resources to get started on your open-source journey with Appflowy.

Throughout this guide, we'll address common questions you may have, such as:

1. How to contribute to Appflowy?
2. How to connect with the team?
3. How to identify and solve your first Pull Request?
4. How to propose new features for Appflowy?
5. How to best engage with the community?
  
And many more. Let's dive in!</p>
<p align="right">(<a href="#introduction">back to top</a>)</p>


<!-- How to Contribute -->
## How to Contribute to Appflowy
<p>Appflowy is managed via GitHub, a popular Content Management/Version Control Application. You'll need a GitHub account to get started for the same. We recommend getting used to GitHub's features and functions, especially Git and GitHub Workflows, before starting with contributions.</p>

### How to Connect with the Team
<p>The best ways to connect with the team are via Discord and GitHub. </p> 

1. Discord 
  - Create a Discord account, and join the [Appflowy Community Server](https://discord.com/invite/9Q2xaN37tV). The server is full of creative individuals from all over the world, who are always ready to help you out, so do not be afraid to ask questions!
  - Start of by introducing yourself in the <b>Intro's</b> section. Read carefully through the <b>welcome</b> Section to better abide by the server's rules and regulations.
  - Have a look around! Feel free to ask any prevalent questions to any member of the Appflowy Team or Appflowy Contributor's by sending a message with a tag (<b>@AppFlowy Team </b>) for the same.

![image](https://user-images.githubusercontent.com/70965472/237025457-bf33e70d-8fbd-4bea-a25e-f1d0ea2147bf.png)
*Welcome Page - Appflowy Dicord Server*

2. GitHub  
  - You can get started via asking questions in the [GitHub Discussions](https://github.com/AppFlowy-IO/AppFlowy/discussions) section of Appflowy.
  - GitHub Discussions provides a forum for Appflowy Contributor's to Ask questions, Share ideas, Engage with other community members and to subsequently Welcome others who join in down the road.

![image](https://user-images.githubusercontent.com/70965472/237032567-9d75b320-423e-4bc2-805d-7bcb7c96217c.png)
*The Appflowy Discussions page*

   - You can navigate through the various categories made available, including announcements, ideas, polls, etc.
   - Feel free to explore the [General Help Wanted](https://github.com/AppFlowy-IO/AppFlowy/discussions/categories/general-help-wanted) and [Technical Help Wanted](https://github.com/AppFlowy-IO/AppFlowy/discussions/categories/technical-help-wanted) Sections to check out some open projects within Appflowy that you can get started working on.
   - Also, feel free to explore Appflowy's [6 Month Technical Roadmap](https://github.com/AppFlowy-IO/AppFlowy/discussions/1715), to gain a better understanding on Appflowy's current development goal over the course of the next 6 months.

3. Mail 
  - You can get in touch with the team via mail - [support@appflowy.io](support@appflowy.io).


### How to identify and solve your first PR
<p>Contributions are made via Pull Requests (PR's). We recommend getting familiar with [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow) for the same. Once you're ready, you can begin looking for a PR to work on. A pre-cursor to this would also include setting up your developemet environment. You can find help for the same in Appflowy's Documentation, made available [here](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions). The steps are as follows:</p>

  Step 1: Go to the [Appflowy's repository](https://github.com/orgs/AppFlowy-IO/repositories) section in GitHub. Here you can see all of Appflowy's Open-Source repositories that can be contributed to. For the purposes of this article, we shall be looking for Issues within the main [Appflowy](https://github.com/AppFlowy-IO/AppFlowy) repository.
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/715c8a61-af5f-4856-840f-11f8604e765c)
  *Appflowy GitHub Page - with all Open-Source Repositories that can be worked on*
  
  Step 2: Go to the <b>Issues</b> section of the repository. It should looke something like this:
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/14fdc0e3-1517-40da-9576-4646b0516b36)
  *Issues Section*
  
  Step 3: Go to the label subsection, and type in <b>Good First Issue for Devs</b>.
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/f5dedcd1-5f08-483d-9898-6372022060b3)
  *Label subsection within Issues*
  
  Step 4: Here, you can go through a list of Issues that can be worked on. They're fairly straightforward and can help you get accustomed to the developement environment as well as the codebase. Feel free to ask anyone from the Appflowy Team for suggestions, as well as to assign you to an Issue.
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/e1022103-e98e-42b5-a43d-03f5c5b08f04)
  *Label subsection within Issues*
  
  <p> Issues are generally categorized into either <b>Feature [FR]</b> or <b>Bugs [Bug]</b>. You can proceed to have a look at the description provided for the given issue. Send a message down in comments section to get the issue assigned to yourself. Once that's done, you are ready to begin coding!</p>
  
  ![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/a0c1479d-8c1b-4af8-a766-dbff8ab6c3d4)
  *An example of an issue that can be worked on. Remember to message the maintainers first!*
  
  <p> As mentioned before, we expect you to go about contributions using the [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow) way. That involves some standard steps: </p>
  
1. Creating your own branch, either within a forked repository (recommended), or directly within the Appflowy Repository.
2. Setting up your developemnt environment.
3. Making changes to the codebase, in accordance to the requirements and tasks present in the Issue that you have chosen to work on.
4. Pushing the changes to your branch, and creating a Pull Request for the same.
5. Having a code review for the same, making further changes.
6. Passing all the automated tests put in place.
7. Handling Merge Conflicts.
8. Merging your branch, and subsequent deletion of the branch once Merge is successfully completed.

<p>These are the steps required to hande your first PR.</p>

### How to propose new features and changes for Appflowy
<p>Congratulations on completing your first PR! We're sure this is the first of many contributions from you! As Appflowy is Open Source in Nature, it also means that anyone and everyone is free to make recommendations and changes that can help improve Appflowy. If you have any ideas on how to go about doing the same, you can propose them via GitHub Issues. Let us see how:</p>

Step 1: Go to the [Appflowy's repository](https://github.com/orgs/AppFlowy-IO/repositories) section in GitHub. Here you can see all of Appflowy's Open-Source repositories that can be contributed to. For the purposes of this article, we shall be looking at the main [Appflowy](https://github.com/AppFlowy-IO/AppFlowy) repository.
Step 2: Click on the <b>New Issue</b> section of the repository. The subsequent page should look something like this:

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/6d1b1efd-eb69-4083-a098-6f9e4117e11c)
*Create New Issues Page*

Step 3: Here, you can choose either to propose a Feature change, or address a Bug. For the purpose of this article, we shall choose the Create new Feature option.
Step 4: On entering the type of issue, you will be redirected to a Feature Request form. Fill in all the fields, including the title, a detailed description of what the feature aims to do, its potential impact, and any other additional context needed to better understand the proposed feature. 
Step 5: Click submit, and you're done!

![image](https://github.com/JRS296/AppFlowy-Docs/assets/70965472/cbccc006-7b10-47a8-886c-828352c67319)
*Feature Submit Form*

<p>Congratulations! You now know how to submit a feature through the issues tab available on GitHub.</p>


### An Example on how to handle your first PR
(WIP)
<p align="right">(<a href="#introduction">back to top</a>)</p>



<!-- How to best engage with the community -->
## How to best engage with the community

<p> Here are some best practices to engage with the community here at Appflowy: </p>

- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

<p>Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by contacting the project team at annie@appflowy.io. All complaints will be reviewed and investigated and will result in a response that is deemed necessary and appropriate to the circumstances. The project team is obligated to maintain confidentiality with regard to the reporter of an incident. Further details of specific enforcement policies may be posted separately.</p>
  
<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Links to Resources to help get started with technical contributions -->
## Links to Resources to help get started with technical contributions

<p> This might be quite a lot to take in at first, especially if you're a newcomer to Software Development. We have curated some links that can help kickstart your journey with Appflowy. These include documentation for the technologies and frameworks used for maintaining and developing Appflowy. Feel free to read up on anything that might be unfamiliar to you. It goes a long way!</p>

- [Git](https://git-scm.com/)
- [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow)
- [Futter](https://flutter.dev/learn)
- [Rust](https://www.rust-lang.org/learn)
- [Appflowy Doumentation](https://appflowy.gitbook.io/docs/essential-documentation/readme)

<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Other Initiatives by Appflowy -->
## Other Initiatives by Appflowy

<p>Here at Appflowy, we foster learning through various iniatives. It's our goal to help anyone who stops by in their developmental journey as much as possible. With this in mind, here are some initatives by Appflowy for the same: </>
  
  - Appflowy Mentorship Program - The AppFlowy mentorship program is aimed at creating a hands-on learning opportunity for new developers who may otherwise lack the opportunity to gain exposure to real-world software practice and entry to the technical community. Link: [Appflowy Mentorship Program](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/appflowy-mentorship-program/contributor-guidance)
  
  - GitHub Octernships - (Currently Closed)
  
  - Write for Appflowy - Whether you’re an AppFlowy power user, a software development expert, or just a student starting to get into open source, there is knowledge you can share that will benefit the entire AppFlowy community. Click the link below to learn more. Link: [Write for Appflowy](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/write-for-appflowy)

<p align="right">(<a href="#introduction">back to top</a>)</p>

<!-- Conclusion -->
## Conclusion

<p> To summarise, we were able to understand how to Contribute to Appflowy, how to handle that first PR, How to connect with the community, and many others in this article. </p>

<p align="right">(<a href="#introduction">back to top</a>)</p>




<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

