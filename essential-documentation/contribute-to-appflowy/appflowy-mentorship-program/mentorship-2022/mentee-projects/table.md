---
description: Mohammad Zolfaghari
---

# Table

## Introduction

Being able to add and modify tabular content is an important feature in any document writing/editing application.

Table is one of Appflowy suggested project ideas which aims implementing basic tabular content feature for Appflowy document pages. Currently, nothing related to tabular content is supported, So it will be implemented from scratch. Probably similar to other appflowy editor plugins.

## Goal

Appflowy will have a table plugin which could get added as a selection menu item (available with slash '/' command) and through Markdown syntax. Also with all related features like resizing, adding modifying rows/cols enabled and basic rich-text support in cells.

## Scope

On completion of this the user will be able to:

- Insert table command which can get added as selection menu item
- Basic table which also can get duplicate or deleted
- Being able to add/delete/duplicate/update rows and columns of existing table
- Resize column/row feature
- Support rich-text editing in table cells (basic markdown features like bold, italic, checkbox, ...)
- Drag and Drop feature for rows and columns
- Enable text color and background color for rows and columns
- Support Markdown table creation `|Col A|Col B|` should convert to a table

## Implementation design

First I have to decide using a base dart package for table or writing it from scratch. Until now after some digging for using a base package my suggested options are [DAVI](https://pub.dev/packages/davi) package and [flutter table](https://api.flutter.dev/flutter/widgets/Table-class.html). DAVI seems promising, But I'm not sure that all intended features and goals are achievable with it in a good way. Will start with DAVI and see how it goes.

After this and having a basic table the features should get implemented one by one. A table mainly consist of three parts Row, Column, Cell and all desired features are related to one or multiple of these parts.

For markdown support regarding converting a Markdown syntax table to appflowy table I will implement it within appflowy editor Markdown plugin. There will be both decoder and encoder for table.

All the way most of the code will have tests for each feature and action.