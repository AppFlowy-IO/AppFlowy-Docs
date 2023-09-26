---
description: Mukund Tandon
---

# Importers

### Introduction

AppFlowy is a powerful knowledge management tool that empowers users to organize their work, take notes, ideate and plan effectively. To enhance the onboarding experience and facilitate a seamless transition for new users, Importers project will allow users to migrate their existing data from Third-party applications(eg -Notion) to AppFlowy. This will contain a number of features which would help in importing data. This aims to simplify the migration process and enable users to continue working with their valuable content within AppFlowy.

### Goals

The goal of this project is to make it easy for AppFlowy users to migrate their data from Third-party applications like Notion. First I would be focusing on Notion-

* [ ] &#x20;Convert Notion document page to AppFlowy document page

<!---->

* Allow notion user to easily import a complete page to AppFlowy .When the user clicks on export on Notion page it gives us a zip file which user can import to AppFlowy . This will import the page along with the subpages of that pages and the assets of that page.
* Also fix the current implementation of importing using markdown to support all elements which are supported in AppFlowy but are missing in import example codeblocks, images.
* Enable appflowy-editor users to effortlessly convert their custom Markdown syntax into custom nodes using the `markdownToDocument` function, with the assistance of custom parsers. With custom parsers, users can specify how they want a particular Markdown syntax to be transformed into a specific node.
* Importing a large file may take a significant amount of time. If the app crashes during the import process, it can result in an incomplete import. If the user initiates another import, it may lead to the creation of duplicate files, as some files have already been imported before and are being imported again. Thus we have to handle this edge case. Also we want to perform this importing in background, so the user can continue to work while the importing is happening.
* Add a option on Import panel to import calendar from notion

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

* [ ] Option to upload the contents of complete workspace from notion to AppFlowy

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

## Implementation Details



### Importing Page from Notion-

#### What does a page look like when exported from Notion-

We get a zip file containing the the main page markdown and a folder containing assets of the main page and also markdown files of subpages of the main page and folders containing the assets of the subpages and the sub-sub pages markdown files and so on.

<figure><img src="../../../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

#### How our main page markdown file look

We can see on line 5,6 we have two images inside the round brackets is the path where images are located and on line 19,21,23 are sub-pages

<figure><img src="../../../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

#### Markdown file of sub-page

Here we have to look at the image path it starts with AppFlowy Subpage 1 instead of instead of AppFlowy Test which is the parent folder. This is because it’s asset lies in AppFlowy Sub 1 folder which is at the same level where the subpage markdown file is . This fact will be used late while importing.

<figure><img src="../../../../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

***

<figure><img src="../../../../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

#### How is the Importing working

* First we iterate through the unzipped files list and store all files and assets in there respective level in the `levels` list
* Next step will be importing all the pages present starting from the last level.we are importing from the last level to handle the case of subpages . For parent page to show `MentionBlock` of the subpage it requires the SubPage viewID which can only be generated once it is imported so we import the lowest level sub page first and then go up storing each page viewID in a map (**nameToID**) which has key as the page name and value as the page viewID.
* Next once we have all page imported we would move them under their respective parent

&#x20;

<figure><img src="../../../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

This class contains details of each page to be imported and the parent of that page which will be used for moving the page under correct parent in later steps&#x20;

<figure><img src="../../../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

This class contains details of each level of the files. Like For example the main page will be level one , if it has a subpage it will be level 2 and if that subpage will have another subpage that would belong to level 3

<figure><img src="../../../../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

#### When we are importing a markdown page how are we dealing with images

* To deal with images we take all contents of a markdown file and pass it through `_preProcessMarkdownFile` function which returns us a string which is the contents of the markdown file but with changes. The changes this function performs are related to images . It will iterate through each line and if it finds something like `![name](path)` this is how a image is represented in markdown . When we get this line is detected we get the path from this this path is actually the file name of image from the above list of unzip images so with the help of path we will get the image file and save it locally and change the current path to the path where the image is saved locally
* Now the problem we can see here is as discussed before the path name in a sub page starts with AppFlowy Sub page instead of Appflowy test which is the root . In the above list also you can see that all the file name are starting from AppFlowy Test so if we directly pass this list to `_preProcessMarkdownFile` it wont be able find the image file.So this issue was solve by only passing the assets of a particular level to the \_preProcessMarkdownFile function instead of all the assets and also during the process of adding files/assets in the levels list if a file is not added in the particular level then the first part(parent) from it name would be removed

#### How does Subpages are handled while importing a page ?

<figure><img src="../../../../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

We are imported from level 3 to level 1. This is done because to handle the subpages . We use `markdownToDocument` function of appflowy-editor package to chick we pass the markdown contents of our page and it return us a Document. We also pass a custom-parser to this function which handles our subpage. Whenever it detects a subpage it replace the part with a `MentionBlock`(It contains the pageID of the page that is being Mentioned) . This is reason we are importing the lower level page first . We will import them and store their viewID in a map where the key is pageName and value is the pageID. When above level are being imported and there contents are passed through `_preProcessMarkdownFile` function this map(nameToId) is also passed in the function , whenever it finds a subpage which looks like name to `{{AppFlowy-Subpage}}{$subpageName}{$subPageID}` , this pattern is used in custom parser to detect the subpage part and convert it to mention block. We have stored the pageIds with name as key so we can easily get the pageID of subpage by using name from name .

## What all have been implemented

* Support for code block to imported from markdown ([PR](https://github.com/AppFlowy-IO/appflowy-editor/pull/197), [PR](https://github.com/AppFlowy-IO/appflowy-editor/pull/347))
* Users can upload images from their local system ([PR](https://github.com/AppFlowy-IO/appflowy-editor/pull/232))
* Support importing image assets from markdown file ([PR](https://github.com/AppFlowy-IO/appflowy-editor/pull/316))
* Support Number List being properly imported from markdown ([PR](https://github.com/AppFlowy-IO/appflowy-editor/pull/335))
* Custom parsers support in appflowy-editor for importing custom nodes ([PR](https://github.com/AppFlowy-IO/appflowy-editor/pull/403))
* importing a complete page from Notion along with all its assets and subpages ([PR](https://github.com/AppFlowy-IO/AppFlowy/pull/3146) is still under review)
* Small Bug Fixes([PR](https://github.com/AppFlowy-IO/appflowy-editor/pull/371) , [PR](https://github.com/AppFlowy-IO/appflowy-editor/pull/349) )

&#x20;

