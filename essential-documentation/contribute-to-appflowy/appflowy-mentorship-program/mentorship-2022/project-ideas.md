# Project Ideas

You might notice that the ideas listed are sometimes vague or incomplete. This is on purpose, as in real-world development, you often need to define the problem and scope your solution before coding officially begins. If you wish to submit a proposal based on these ideas, you are encouraged to contact the mentors on Discord and find out more about the particular suggestion you're looking at.

### Desktop features

1. ~~**Table (it's taken)**~~

Add simple tabular content to a page

Expected Outcome:

* The user can insert a table into a page via the slash '/' command
* The user can delete and duplicate an existing table
* The user can add/delete/duplicate/update rows and columns to an existing table
* Each table cell supports rich-text editing
* Test covered

Difficulty: Medium to High

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)



2. [~~**Calendar Database**~~](mentee-projects/calendar-view-for-appflowy-database.md) ~~**(it's taken)**~~

Calendars are a great way to visualize how things connect to certain dates from any database in AppFlowy. Use them for task management and event planning.

* Expected Outcome: the user can create a calendar page and add an item to a certain date or a range of dates in the calendar.
* Difficulty: High
* Skills Required: Flutter
* Mentor: [Nathan.fooo](https://github.com/appflowy)

***

3. [~~**Themes**~~](mentee-projects/custom-themes.md) ~~**(it's taken)**~~

Control the accent color used for interactive elements such as links, handles, and text selection. The editor cursor can also choose to use the same accent color.

Other customizations:

* Fonts
* Font sizes, font weights
* Font colors
* Text background colors

Difficulty: Medium

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)



4. ~~**Shortcuts (it's taken)**~~

Add more shortcuts and enable users to customize hotkeys

Difficulty: Easy to Medium

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)



5. **AI writers**

Utilize AI models to assist in writing. For example, generate to-do lists, outlines, and blog posts.

Difficulty: Medium

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)



6. **AI image generator**

Generate images from text and beyond

Difficulty: Medium

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)

***

7. ***

***

Difficulty: Medium to Hard

Skills Required: Flutter

Mentor: Alex&#x20;

***

8. ~~**Outline Plugin for AppFlowy Editor (it's taken)**~~

Adding the outline block to the document will automatically generate a list of anchor links to the headings within the document.

Expected Outcome:

* insert an outline via the slash '/' command
* convert highlighted lines into an outline
* the content of the outline will be generated automatically based on the document
* click on the content of the outline will take users directly to the corresponding heading
* different levels of headings are indented differently. For example, H1 will have no indentation, while H2 will be indented once, and so on.

Difficulty: Medium

Skills Required: Flutter

Mentor: [Lucas](https://github.com/LucasXu0)



9. ~~**Favorites (it's taken)**~~

Allow us to quickly access favorited pages via Favorites in the left navigation panel.

Expected Outcome:

* Favorite and unfavorite a page or subpage
* Favorited pages can be accessed from the "Favorites" list in the left panel

Difficulty: Hard

Skills Required: Flutter, Rust

Mentor: Mathias, Nathan



10. &#x20;~~**Importers (it's taken)**~~

Import data from third-party sources, eg: Notion importer, Joplin importer

Difficulty: Easy / Medium / Hard

Skills Required: Flutter, Rust

Mentor: Lucas



### CI tools

**1. Report Binary Size**

We consider binary size as an important metric, although it is easy to overlook. We would like to create some GitHub integrations that would automatically do a release build of a new PR and report the difference in binary size between that PR and the current main branch.

* Expected Outcome: an easy-to-use tool to report binary size
* Difficulty: Easy / Medium
* Skills Required: Flutter, Rust, GitHub API
* Mentor: [Nathan.fooo](https://github.com/appflowy)

**2. Speed up building the release package**

It takes almost 20 minutes to build the AppFlowy release package. It would be nice if we can speed it up using GitHub cache or matrix.

* Expected Outcome: the cost of the time of the PR’s GitHub actions should be reduced
* Difficulty: Easy / Medium
* Skills Required: Flutter, Rust, GitHub API
* Mentor: [Nathan.fooo](https://github.com/appflowy)

### Tracing performance regressions

**1. Tracing performance regressions**

Performance could become a key differentiator for AppFlowy. We’d like to keep tracking it. To track it, we need to come up with a metric system. The system includes a set of metrics and a running process that collects results and persists them for analysis.

* Expected Outcome:
  * A metric system that measures the performance of AppFlowy
  * A working tool that collects results and persists them for analysis
* Difficulty: Medium / High
* Skills Required: Rust
* Mentor: [Nathan.fooo](https://github.com/appflowy)
