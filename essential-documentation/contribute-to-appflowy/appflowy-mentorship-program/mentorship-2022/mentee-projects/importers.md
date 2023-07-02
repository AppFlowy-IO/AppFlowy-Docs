# Importers

### Introduction

AppFlowy is a powerful knowledge management tool that empowers users to organize their work, take notes, ideate and plan effectively. To enhance the onboarding experience and facilitate a seamless transition for new users, Importers project will allow users to migrate their existing data from Third-party applications(eg -Notion) to AppFlowy. This will contain a number of features which would help in importing data. This aims to simplify the migration process and enable users to continue working with their valuable content within AppFlowy.

### Goals

The goal of this project is to make it easy for AppFlowy users to migrate their data from Third-party applications like Notion. First I would be focusing on Notion-

* [ ] &#x20;Convert Notion document page to AppFlowy document page

<!---->

* Rust -> Right now there is a option to import a single file to import, we need to extend this functionality to support upload of a folder because when we export a page from notion it will give us a folder which will contain a markdown file and another folder containing the assets of that page. Also fix the current implementation of importing using markdown to support all elements which are supported in AppFlowy but are missing in import example codeblocks ,images.

<!---->

* [ ] Convert Notion calendar to AppFlowy calendar

<!---->

* Rust -> Support populating the Calendar page from the imported folder which contains a CSV file and a folder containing markdown file of notes for each date.
* Flutter -> Add a option on Import panel to import calendar from notion

<!---->

* [ ] Convert Notion board to AppFlowy Board

<!---->

* Rust -> Populating the board with the data from the CSV file which contains information regarding the column under which each card should be placed on the board. Then there is a folder containing the contents of each card. So we need to populate the cards with their respective contents.
* Flutter -> Add an option on Import panel to import board from notion

<!---->

* [ ] Convert Notion Database to AppFlowy Grid

<!---->

* Rust -> AppFlowy currently supports importing CSV , So we can import the grid contents from Notion but in Notion each row is a page and can contain more information than that given in the grid so have to also import those pages. When we export the Notion Database we get a folder containing a CSV file and and number of markdown files .We can use the CSV file to populate AppFlowy grid and can import the each  page from the markdown files from the folder
* Flutter -> Add a option on Import panel to import Database from notion.

<!---->

* [ ] Option to upload the contents of complete workspace form notion to AppFlowy

<!---->

* Rust -> When we export our workspace we get a folder which contains many sub folders having information regarding each page. So we need to populate all the pages and subpages in the correct manner including all databases calendars and boards
* Flutter -> Add a option on Import panel to import workspace from notion.

### Scope

On completion of this -

* There will be an option in the Import panel that says "Import from Notion." Upon clicking on it, users will be able to select what they want to import, such as boards, grids, calendars, pages, or the entire workspace.
* Users will be able to import  a single page from Notion and all contents from that page which are supported in AppFlowy will get imported
* Users will be able to import their calendars from Notion
* Users will be able to import their board from Notion
* Users will be able to import their database from Notion including the subpages.
* Users will be to import their complete workspace from Notion. There would be an option to select the folder(provided by Notion) which contains all the exported contents, and all the contents(supported by AppFlowy)  from that folder will be imported into AppFlowy with all the pages and subpages in correct manner including all databases calendars and boards

### Schedule

* [ ] By 12th July (First month) -

<!---->

* Users will be able to add image to AppFlowy from local files
* Code block will also be imported from Notion Page
* Images can also be imported from Notion page
* Start working on importing calendar from Notion

<!---->

* [ ] By 12th August(Second Month)

<!---->

* Users will be able to import Calendars form Notion&#x20;
* Users will be able to import board from Notion
* Start working on importing database from Notion

<!---->

* [ ] By 12th September(Third Month)

<!---->

* Users will be able to import database from Notion including the subpages
* Users will be able to import their whole workspace to AppFlowy

&#x20;

