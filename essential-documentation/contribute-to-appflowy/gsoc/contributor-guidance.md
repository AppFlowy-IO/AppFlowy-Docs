# Contributor Guidance

## About AppFlowy&#x20;

https://www.appflowy.io/

AppFlowy is an open-source no-code platform for your wikis, notes, tasks, and more, available for Windows, macOS, and Linux. It is built with Flutter and Rust. You are in charge of your data and customizations.

AppFlowy started as an open-source side project built from the ground up by a single developer; afterward, it was maintained by a team of two. Since its GitHub launch in November 2021, it has accumulated more than 17,000 stars and 18,000 downloads. It also has fostered an engaged community of more than 1,000 builders.

AppFlowy is built for teams and individuals that need more control and flexibility. You have 100% control of your data. You can host AppFlowy wherever you want: there’s no vendor lock-in. It offers unlimited customizations. You can design and modify AppFlowy your way with an open core codebase. It is built with Flutter and Rust. What does this mean? Faster development, a better native experience, and more reliable performance. Better still, we are community-driven. We work with our community to collaboratively create apps that suit others’ needs by developing a versatile toolbox of plugins, templates, and more. Join us as we build a toolbox that empowers anyone to create their own system. With us, you can play and tweak without a glass ceiling on what’s possible.

## Getting Started&#x20;

Please use our [first-time AppFlowy developer guide](https://github.com/annieappflowy) to get your AppFlowy development environment set up and find your first issue. If you have any trouble, please ask on our community channel.

GSoC applicants are required to complete an issue tagged with the [“good first issue for devs” ](https://github.com/AppFlowy-IO/AppFlowy/labels/good%20first%20issue%20for%20devs)in order to be selected. This requires you to get familiar with our codebase and demonstrates your interest in contributing to AppFlowy. Don’t worry if you make mistakes in your first contribution. Instead, please see it as a great opportunity to get involved in our community, receive feedback, and iterate your work - a flavor of doing GSoC with AppFlowy.

## Application Instructions&#x20;

Once your PR for an issue tagged with the “good first issue for devs” is merged, you can start developing a specific project plan. We recommend discussing your ideas with the community on [Discord](https://discord.gg/9Q2xaN37tV).

The GSoC 2022 application deadline is April 19, 2022. Please use the [suggested proposal template](proposal-template.md) when applying. Check out GSoC guides for more tips. You will need to do thorough research on the AppFlowy codebase, read documentation, and talk with potential mentors to put together a complete project proposal. It’s cool to come up with your own project idea as long as your idea falls under the umbrella of this year’s themes:&#x20;

* Desktop features&#x20;
* CI tools&#x20;
* Tracing performance regressions

Please get in touch with a mentor early on if you want to work on your own idea and make sure it is realistic and within the scope of AppFlowy. We also welcome applicants to work on one of our ideas. Please see [Project Ideas](contributor-guidance.md#project-ideas) for details.

We expect applicants to be excited about gaining real-world software experience and learning practical skills such as problem-solving and asking well-formed questions. We also expect applicants to either have experience with the technologies relevant to their project or have strong general programming experience. We are happy to accept both student and non-student participants.

## Project Ideas&#x20;

You might notice that the ideas listed are sometimes vague or incomplete. This is on purpose, as in real-world development, you often need to define the problem and scope your solution before coding officially begins. If you wish to submit a proposal based on these ideas, you are encouraged to contact the mentors on Discord and find out more about the particular suggestion you're looking at.&#x20;



### Desktop features&#x20;

**1. Calendar Database**&#x20;

Calendars are a great way to visualize how things connect to certain dates from any database in AppFlowy. Use them for task management and event planning.&#x20;

* Expected Outcome: the user can create a calendar page and add an item to a certain date or a range of dates in the calendar.&#x20;
* Difficulty: High&#x20;
* Skills Required: Flutter&#x20;
* Potential mentors: [Nathan.fooo](https://github.com/appflowy) (nathan.fooo), [annie](https://github.com/annieappflowy) (annie\_appflowy)

**2. Search**&#x20;

Users write pages in AppFlowy. We’d like to have a search function for them to easily retrieve information from their wikis or notes.&#x20;

* Expected Outcome: a search function that allows users to search pages based on keywords&#x20;
* Difficulty: High Skills&#x20;
* Required: Flutter, Rust&#x20;
* Potential mentors: [Nathan.fooo](https://github.com/appflowy) (nathan.fooo), [annie](https://github.com/annieappflowy) (annie\_appflowy)

**3. Template**&#x20;

People should be able to share their best practices via templates with others. We’d like to enable users to quickly set up a page by using a template and get inspiration from community templates.&#x20;

* Expected Outcome:&#x20;
  * A template center that allows users to view and clone a template into their workspace&#x20;
  * A system that allows people to propose a new template that can be added to the template center&#x20;
* Difficulty: Medium&#x20;
* Skills Required: Flutter, Rust&#x20;
* Potential mentors: [Nathan.fooo](https://github.com/appflowy) (nathan.fooo), [annie](https://github.com/annieappflowy) (annie\_appflowy)

**4. Add to Favorites**&#x20;

Favoriting a page allows users to quickly access it without searching it or clicking through nesting pages.&#x20;

* Expected Outcome: the user can favorite a page and access it via a “Favorites” section that resides in the navigation panel.&#x20;
* Difficulty: Medium Skills Required: Flutter, Rust&#x20;
* Potential mentors: [visitor](https://github.com/tsuiyuenhong) (TsuiYuenHong), [Nathan.fooo](https://github.com/appflowy) (nathan.fooo)

**5. Page history**&#x20;

AppFlowy users might want to go back to a previous version of a page, and we’d like to enable page history so that they can do so.&#x20;

* Expected Outcome: the user can restore a page to a previous version through “Page history”&#x20;
* Difficulty: High Skills&#x20;
* Required: Flutter, Rust&#x20;
* Potential mentors: [Nathan.fooo](https://github.com/appflowy) (nathan.fooo), [annie](https://github.com/annieappflowy) (annie\_appflowy)

### CI tools&#x20;

**1. Report Binary Size**

We consider binary size as an important metric, although it is easy to overlook. We would like to create some GitHub integrations that would automatically do a release build of a new PR and report the difference in binary size between that PR and the current main branch.&#x20;

* Expected Outcome: an easy-to-use tool to report binary size&#x20;
* Difficulty: Easy/Medium
* Skills Required: Flutter, Rust, GitHub API&#x20;
* Potential mentors: [visitor](https://github.com/tsuiyuenhong) (TsuiYuenHong), [Nathan.fooo](https://github.com/appflowy) (nathan.fooo)

**2. Speed up building the release package**

It takes almost 20 minutes to build the AppFlowy release package. It would be nice if we can speed it up using GitHub cache or matrix.&#x20;

* Expected Outcome: the cost of the time of the PR’s GitHub actions should be reduced&#x20;
* Difficulty: Easy/Medium
* Skills Required: Flutter, Rust, GitHub API&#x20;
* Potential mentors: [visitor](https://github.com/tsuiyuenhong) (TsuiYuenHong), [Nathan.fooo](https://github.com/appflowy) (nathan.fooo)&#x20;



### Tracing performance regressions&#x20;

**1. Tracing performance regressions**

Performance could become a key differentiator for AppFlowy. We’d like to keep tracking it. To track it, we need to come up with a metric system. The system includes a set of metrics and a running process that collects results and persists them for analysis.&#x20;

* Expected Outcome:&#x20;
  * A metric system that measures the performance of AppFlowy&#x20;
  * A working tool that collect results and persists them for analysis&#x20;
* Difficulty: Medium / High&#x20;
* Skills Required: Rust&#x20;
* Potential mentors: [Nathan.fooo](https://github.com/appflowy) (nathan.fooo), [visitor](https://github.com/tsuiyuenhong) (TsuiYuenHong)

## More info&#x20;

* [AppFlowy’s official website](https://www.appflowy.io)
* [GitHub](https://github.com/AppFlowy-IO/AppFlowy)
* [Discord](https://discord.gg/9Q2xaN37tV)
* [Twitter](https://twitter.com/appflowy)
