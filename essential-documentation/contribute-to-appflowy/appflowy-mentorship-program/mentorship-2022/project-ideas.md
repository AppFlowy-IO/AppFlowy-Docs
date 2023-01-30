# Project Ideas

You might notice that the ideas listed are sometimes vague or incomplete. This is on purpose, as in real-world development, you often need to define the problem and scope your solution before coding officially begins. If you wish to submit a proposal based on these ideas, you are encouraged to contact the mentors on Discord and find out more about the particular suggestion you're looking at.&#x20;



### Desktop features&#x20;

1. **Table**&#x20;

Add simple tabular content to a page

Expected Outcome:&#x20;

* The user can insert a table into a page via the slash '/' command
* The user can delete and duplicate an existing table
* The user can add/delete/duplicate/update rows and columns to an existing table
* Each table cell supports rich-text editing
* Test covered

Difficulty: Medium to High

Skills Required: Flutter

Mentor:  [Lucas](https://github.com/LucasXu0)



~~****~~[~~**2. Calendar Database**~~](mentee-projects/calendar-view-for-appflowy-database.md) ~~**(it's taken)**~~

Calendars are a great way to visualize how things connect to certain dates from any database in AppFlowy. Use them for task management and event planning.&#x20;

* Expected Outcome: the user can create a calendar page and add an item to a certain date or a range of dates in the calendar.&#x20;
* Difficulty: High&#x20;
* Skills Required: Flutter&#x20;
* Mentor: [Nathan.fooo](https://github.com/appflowy)&#x20;

****

**3. Toggle List**

Toggles can show and hide content inside.

Expected Outcome:&#x20;

* insert a toggle list via the slash '/' command
* convert highlighted lines into a toggle list
* add or move things inside a toggle
* add a toggle inside a toggle
* hide and show content inside a toggle
* toggle headings

Difficulty: Medium to High

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)



**4. The block handle and '+'** &#x20;

When you hover over any line or contents, the handle appears in the left margin. Click it to see a menu of options: Delete, Duplicate (design spec will be provided). Click '+' next to it to trigger the slash '/' menu.

Difficulty: Medium

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)



~~****~~[~~**5. Themes**~~](mentee-projects/custom-themes.md) ~~**(it's taken)**~~

Control the accent color used for interactive elements such as links, handles, and text selection. The editor cursor can also choose to use the same accent color.&#x20;

Other customizations:

* Fonts
* Font sizes, font weights
* Font colors
* Text background colors

Difficulty: Medium

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)



~~**6. Shortcuts (it's taken)**~~

Add more shortcuts and enable users to customize hotkeys

Difficulty: Easy to Medium

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)

****

### CI tools&#x20;

**1. Report Binary Size**

We consider binary size as an important metric, although it is easy to overlook. We would like to create some GitHub integrations that would automatically do a release build of a new PR and report the difference in binary size between that PR and the current main branch.&#x20;

* Expected Outcome: an easy-to-use tool to report binary size&#x20;
* Difficulty: Easy / Medium
* Skills Required: Flutter, Rust, GitHub API&#x20;
* Mentor: [Nathan.fooo](https://github.com/appflowy)&#x20;

**2. Speed up building the release package**

It takes almost 20 minutes to build the AppFlowy release package. It would be nice if we can speed it up using GitHub cache or matrix.&#x20;

* Expected Outcome: the cost of the time of the PR’s GitHub actions should be reduced&#x20;
* Difficulty: Easy / Medium
* Skills Required: Flutter, Rust, GitHub API&#x20;
* Mentor: [Nathan.fooo](https://github.com/appflowy)&#x20;



### Tracing performance regressions&#x20;

**1. Tracing performance regressions**

Performance could become a key differentiator for AppFlowy. We’d like to keep tracking it. To track it, we need to come up with a metric system. The system includes a set of metrics and a running process that collects results and persists them for analysis.&#x20;

* Expected Outcome:&#x20;
  * A metric system that measures the performance of AppFlowy&#x20;
  * A working tool that collects results and persists them for analysis&#x20;
* Difficulty: Medium / High&#x20;
* Skills Required: Rust&#x20;
* Mentor: [Nathan.fooo](https://github.com/appflowy)
