# Grid

This document explains how the grid works on the Dart side. Also, it can be a development guide when you want to be a grid contributor. This document will get updated continuously, and any suggestions would be helpful.

## Introduction&#x20;

### Definitions

Below you will find some quick definitions to help you read through the document.

| Block       | @@@                                                                                                                                                   |   |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | - |
| Cache class | @@@                                                                                                                                                   |   |
| Cell        | A Cell is one individual cell in a grid. You can see more in the [Cell](grid.md#cell) section.                                                        |   |
| Column      | A column is a theoritical representation of data, however there is no Column class.                                                                   |   |
| Field       | A Field represents the configuration of a column. You can see more in the [Field](grid.md#field) section.                                             |   |
| Grid        | A Grid type is simple representation of items placed in column and rows. It is not a spreasheet. You can see more in the [Grid](grid.md#grid) section |   |
| Header      | @@@                                                                                                                                                   |   |
| Row         | A Row represents a group of related data                                                                                                              |   |

## Grid

At its core, a Grid type is a simple representation of items placed in columns and rows. It is not a spreadsheet.&#x20;

Another name for the column is Field. A column's configuration is defined in the [Field](grid.md#field) class. It is important to note though that although a grid has the concept of columns, there are no actual Column classes.&#x20;

A user can add a Row, and then define the data in each of the cells created for the Grid's Field in that row.

A Grid has a list of blocks, each block has a list of rows.
![file : grid.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/AppFlowy-Docs/main/uml/output/grid.svg)

## Cache

![file : grid\_data\_cache.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/AppFlowy-Docs/main/uml/output/block\_row\_cell\_relation.svg)

When you open a grid, a `GridBloc` will be initialized. There are four cache classes, as show in the diagram above.

1. GridFieldCache
   * Listens to the Field's changes
   * Updates the Field according to the `GridFieldChangesetPB`.
2.  GridBlockCache

    A Grid contains lots of blocks, each block has a `GridRowCache`. For the moment, we only implement one block.

    * Listens to the block's changeset
    * Updates the `GridRowCache` according to the `GridBlockChangesetPB`. The changeset contains the ids of inserted/deleted/updated rows.
3. GridRowCache
   * Caches the block's rows in memory
   * A row contains many cells, each cell will be cached in the `GridCellCache`.
   * Allows to insert/delete/update rows
4. GridCellCache
   * Caches each cell by `GridCellCacheKey` in memory
   * Allow to remove/Insert cells

## Field

### Field

A Field represents a column's configuration. It will contain the column's name, id, width, type (as defined in [FieldType](grid.md#fieldtype)), etc.&#x20;

A Field is not a column of data, it does not contain a list of Cells.

### FieldType

A Field has a FieldType. The FieldType defines the kind of data contained in a column. For example a column may contain dates, numbers, text, multi-select list, etc.&#x20;

Certain field types have user-defined options such as color, date format, number format, or a list of values for a multi-select list. These options are defined within a specialization of the FieldTypeOption class.

### **FieldEditor**

* Loads the FieldTypeOptionData

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Field\_Editor.svg)

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Field\_Type\_Option\_Editor.svg)

## Cell

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Grid\_Cell\_Builder.svg)

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Grid\_Cell\_Controller.svg)
