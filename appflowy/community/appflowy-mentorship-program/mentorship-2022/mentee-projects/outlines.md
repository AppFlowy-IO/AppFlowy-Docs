---
description: Aman Negi
---

# Outlines

### Introduction

**AppFlowy** is a versatile tool with a wide range of use cases. As a result, documents created in AppFlowy can vary significantly in length and complexity. To address this, it would be beneficial to develop an **Outline Plugin** that would display all of the headings in a document at the beginning, making it easier for users to scan and navigate the document.

### Goals

The goals of the AppFlowy Outline Plugin are to:

* Provide a quick and easy way to navigate through long and complex documents
* Help users to find specific information in a document more quickly
* Provide a visual overview of the document's structure
* Help users to understand the document's content

### Scope

The AppFlowy Outline Plugin will add the following new actions to the AppFlowy application:

* Users will be able to add an outline to a document using the slash (`/`) menu.
* The content of the outline will be automatically generated based on the document.
* Clicking on the content of the outline will take users directly to the corresponding heading.
* In the outline different levels of headings will be indented differently. For example, H1 will have no indentation, while H2 will be indented once, and so on.
* Only H1, H2, and H3 headings will be shown in the outline. Other elements will not be displayed or represented.

### Implementation

To keep the encapsulate the Outline feature, we created it as an `editor_plugin` and simply plugged it into the editor.

<figure><img src="../../../../../.gitbook/assets/Screenshot from 2023-08-22 21-05-33.png" alt=""><figcaption><p>Example of Outline Block</p></figcaption></figure>

### Schedule

The AppFlowy Outline Plugin has been released on 2nd July 2023 in [v0.2.5](https://github.com/AppFlowy-IO/AppFlowy/releases/tag/0.2.5).

