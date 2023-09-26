# Code Block

### Introduction <a href="#docs-internal-guid-6fac17cc-7fff-3d73-60fa-4887f8e5612c" id="docs-internal-guid-6fac17cc-7fff-3d73-60fa-4887f8e5612c"></a>

Code Block is a feature that allows you to write and display code snippets within your notes taken in the AppFlowy Editor. It provides a distinct format for code, typically using a monospaced font and syntax highlighting to enhance readability. Code blocks are helpful for developers, programmers, and anyone who wants to include code snippets or technical instructions within their notes while maintaining the visual integrity and readability of the code.

### Goal

The goal of this project is to develop a Code Block in Flutter as a standalone package that AppFlowy and other Flutter applications can use. Right now AppFlowy uses a Code Block plugin that extends BlockComponentBuilder along with a third-party open-source package called[ highlight.dart](https://github.com/git-touch/highlight.dart) for Syntax Highlighting. Our goal is to create a standalone package that extends the functionalities of the existing solution and serves as a building block for AppFlowy and the Flutter Community.

### Scope

The following will be the deliverables by the end of this project:

* A standalone flutter package for Code Block.
* Support for the following features in Code Block:
  * Syntax Highlighting
  * Support for Multiple Programming Languages
  * Copy All Code
  * Copy the entire Code Block
  * Line numbering
  * Auto-Indentation
  * Export/import functionality

### Existing Solution

At the moment we have a Code Block plugin which depends on the[ flutter highlight](https://github.com/git-touch/highlight.dart) package for syntax highlighting, along with the BlockComponentBuilder API of AppFlowy Editor. This current solution only provides the following features we want from our Code Block:

* Syntax highlighting
* Support for multiple programming languages

We are looking to extract our Code Block plugin code and create a separate package for it. We aim to extend its functionalities to support all the features we want in our Code Block solution.&#x20;

### Proposed Solution Design

This is what we expect from our implementation. We want the line numbering to appear in the left edge of our codeblock. Our actions relating to the CodeBlock will go in the top right corner as a row of icons.

<figure><img src="https://lh3.googleusercontent.com/1DTTDw1gDbnIKTiCoRQpSNguoy_QbwCmnelRFzK45xfzUhd8vFYOq8yMukBJ49UkkJ_RDbdS-N0ZYKMOxOQNGjxJ1ZqCLGuY8w1UNaOwnQ7zrxggfbFWnXwvBVV6ka2XvcIIdb9xZ2Z-Gc-dpxC8A-Y" alt=""><figcaption><p>UI mock for Code Block features</p></figcaption></figure>

### Implementation Plan

Following is a set of action plans for each proposed new feature:

**CodeBlock Action Menu:**&#x20;

*   Currently, our existing solution only has the Switch Language option at the top:\


    <figure><img src="https://lh5.googleusercontent.com/O7ZR6JUGDpmKnuTQlmBAMtVTW5cUd5mc9Ppp04uL2DGcUOQbCvylytWZtm2o1-YNW8LANHotYXvwitDyyVWhsyEk38kZT3eQ0H2Dbevc7Mu8t2CVSgh2ntnKbaHhHWpTJGQXRP2yoF3hx6R6o05XUqg" alt=""><figcaption><p>Existing code for Code Block</p></figcaption></figure>
* We will have to add a method that will return an Action Menu which will contain various action buttons, this will contain the Switch Language button, Export Code, and Import Code options. \


**Copy All Code:**

* Copy All code will be one of the actions possible in CodeBlock. It will allow the user to copy the entire code inside the CodeBlock.
* The form of copy will be plain text.\


**Copy and Paste CodeBlock Component:**&#x20;

* The CodeBlock component is a child of BlockComponent which is a part of the AppFlowy Editor package.
* Already there is a way to duplicate a CodeBlock component in AppFlowy, but there is no way to copy-paste the CodeBlock. This is because there is no way to save a CodeBlock through the Clipboard API.
* We will have to work with AppFlowy Editor API and facilitate a new Clipboard API which will be capable of copying a CodeBlock and pasting it wherever the user wants inside the AppFlowy Editor.\


**Line Numbering:**

* Line Numbering can be implemented by calculating the number of lines we have inside the CodeBlock, the line height of each line, and then showing a vertical bar of digits starting from 1 with a vertical difference in the line height.
* The vertical bar will be placed left-adjacent to the CodeBlock. This can be done if we wrap the Padding widget shown below with a Row widget with the first child being a new widget called LineNumberBar.\


**Auto Indentation:**&#x20;

* Although automatic indentation based on the programming language is a heavy feature, in terms of its cost of implementation, we can provide a clever workaround for indentation.
* We can add a Tab space whenever the user presses an Enter key after the following character: ‘{’, ‘(’, ‘\[’, ‘:’. So whenever a bracket open character is followed by an Enter key, we will insert a Tab space on the newline and we will also keep track of the Tab size value as well.
* We will need to handle some edge cases and then, this feature can help the overall user experience.\


**Export/ Import Code:**&#x20;

* Export: Users will be able to export the code inside the CodeBlock as a program file into their local device.
* To facilitate this, we will create a new file in the user’s application directory and give it an extension of the respective language that is selected in the CodeBlock.
*   Import: Users will be able to add code to a CodeBlock from an existing program file. This time we will have to allow users to submit a local program file to our CodeBlock.\


    <figure><img src="https://lh4.googleusercontent.com/218TrQ83gsXQJoYHXWh4P5Y5rb9w7QsUtzQT-weuc4KQE2pJT0Ddcpky-vzl3NrJcOdi1Icwq_-N7zbO6U0U1pY3k-Fldt3zDuEvx0QDnX3hk9p25cZMH788BiRCbx2wh0L7OHIfoATweSKV7ZK6e3U" alt=""><figcaption><p>Import a Program file into the Code Block dialog design<br></p></figcaption></figure>
* Once we receive a file we will check its extension for setting the language of the CodeBlock. Then we will extract the text program and input it inside our CodeBlock.

### Schedule

At the midterm evaluation: on 12 August 2023,\
we plan to achieve the following:

* Line Numbering feature
* Import Program into CodeBlock
* Export Program into CodeBlock
* Auto Indentation\


At the time of completion: on 12 September 2023, \
we plan to have:

* A separate package for CodeBlock which can be plugged into AppFlowy
* All the mentioned features in the scope will be implemented.

\
