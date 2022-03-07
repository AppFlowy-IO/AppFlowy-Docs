# Project Ideas

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
* Difficulty: High&#x20;
* Skills Required: Flutter, Rust&#x20;
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
* Difficulty: Medium&#x20;
* Skills Required: Flutter, Rust&#x20;
* Potential mentors: [visitor](https://github.com/tsuiyuenhong) (TsuiYuenHong), [Nathan.fooo](https://github.com/appflowy) (nathan.fooo)

**5. Page history**&#x20;

AppFlowy users might want to go back to a previous version of a page, and we’d like to enable page history so that they can do so.&#x20;

* Expected Outcome: the user can restore a page to a previous version through “Page history”&#x20;
* Difficulty: High&#x20;
* Skills Required: Flutter, Rust&#x20;
* Potential mentors: [Nathan.fooo](https://github.com/appflowy) (nathan.fooo), [annie](https://github.com/annieappflowy) (annie\_appflowy)

### CI tools&#x20;

**1. Report Binary Size**

We consider binary size as an important metric, although it is easy to overlook. We would like to create some GitHub integrations that would automatically do a release build of a new PR and report the difference in binary size between that PR and the current main branch.&#x20;

* Expected Outcome: an easy-to-use tool to report binary size&#x20;
* Difficulty: Easy / Medium
* Skills Required: Flutter, Rust, GitHub API&#x20;
* Potential mentors: [visitor](https://github.com/tsuiyuenhong) (TsuiYuenHong), [Nathan.fooo](https://github.com/appflowy) (nathan.fooo)

**2. Speed up building the release package**

It takes almost 20 minutes to build the AppFlowy release package. It would be nice if we can speed it up using GitHub cache or matrix.&#x20;

* Expected Outcome: the cost of the time of the PR’s GitHub actions should be reduced&#x20;
* Difficulty: Easy / Medium
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
