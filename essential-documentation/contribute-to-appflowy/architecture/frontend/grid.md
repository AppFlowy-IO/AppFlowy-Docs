# #⃣ Grid

## Introduction

This document explains how the grid works on the Dart side. Also, it can be a development guide when you want to be a
grid contributor. This document will get updated continuously, and any suggestions would be helpful.

### Definitions

Below you will find some quick definitions to help you read through the document.

| Block       | A grid can have many rows. Rows are therefore grouped into Blocks in order to make things more efficient                                             |
| ----------- |------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cache class | Aim to reduce the time cost that getting data from the backend.                                                                                                                                                      |
| Cell        | A Cell is one individual cell in a grid. You can see more in the [Cell](grid.md#cell) section.                                                       |
| Column      | A column is a theoritical representation of data, however there is no Column class.                                                                  |
| Field       | A Field represents the configuration of a column. You can see more in the [Field](grid.md#field) section.                                            |
| Grid        | A Grid type is simple representation of items placed in column and rows. It is not a spreasheet. You can see more in the [Grid](grid.md#grid) section |
| Header      | @@@                                                                                                                                                  |
| Row         | A Row represents a group of related data                                                                                                             |

## Grid

At its core, a Grid type is a simple representation of items placed in columns and rows. It is not a spreadsheet.

Another name for a column is Field. A column's configuration is defined in the [Field](grid.md#field) class.
It is important to note though that although a grid has the concept of columns, there are no actual Column classes.

A user can add a Row, and then define the data in each of the cells created for the Grid's Field in that row.

A Grid has a list of Blocks, each Block has a list of Rows. 

>  Every class with a `PB` suffix is mean it's generated in protobuf format. You could check the [protobuf document](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/architecture/backend/protobuf) out if you interested in how the protobuf classes generated.

![file : grid.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/AppFlowy-Docs/main/uml/output/grid.svg)

## Cache

![file : grid\_data\_cache.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/AppFlowy-Docs/main/uml/output/block\_row\_cell\_relation.svg)

When you open a grid, a `GridBloc` will be initialized. There are four cache classes, as show in the diagram above.

1. `GridFieldCache`
   * Listens to the `Field`'s changes.
   * Updates the `Field` according to the `GridFieldChangesetPB`.
2.  `GridBlockCache`

    A Grid contains many `Block`s, each `Block` has a `GridRowCache`.

    * Listens to the `Block`'s changeset.
    * Updates the `GridRowCache` according to the `GridBlockChangesetPB`. The changeset contains the ids of inserted/deleted/updated `Rows`.
3. `GridRowCache`
   * Caches the `Block`'s `Row`s in memory.
   * A `Row` contains many `Cell`s, each `Cell` will be cached in the `GridCellCache`.
   * Allows to insert/delete/update `Row`s.
4. `GridCellCache`
   * Caches each `Cell` by `GridCellCacheKey` in memory.
   * Allows to remove/insert `Cell`s.

## Block

A `Grid` can hold many thousands of `Row`s. In order to streamline the fetching of data, these `Row`s are split up and
contained in `Block`s.&#x20;

![file : grid.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/AppFlowy-Docs/main/uml/output/grid_block.svg)

A `Grid` can contain many `Block`s, each `Block` has a `GridRowCache`. For the moment, we only support having one `Block`
in the Grid. This will cause a limitation on the number of rows that a user can create, however this limitation will be
lifted in the future.


## Field

### Field

A `Field` represents a column's configuration. It will contain the column's name, id, width, type (as defined in [FieldType](grid.md#fieldtype)), etc.

A `Field` is not a column of data, it does not contain a list of `Cell`s.

### FieldType

A `Field` has a `FieldType`. The `FieldType` defines the kind of data contained in a column. For example a column may contain
dates, numbers, text, multi-select list, etc.

Certain field types have user-defined options such as color, date format, number format, or a list of values for a multi-select list.
These options are defined within a specialization of the `FieldTypeOption` class.

### **FieldEditor**

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Field\_Editor.svg)

* A `FieldEditor` is a widget that is used to edit the field's shared properties. Such as the name of the field, etc. It uses the
  `FieldTypeOptionEditor` to customize the UI for each field.

* `FieldEditorBloc` use `TypeOptionDataController` to listen on the field's changed or perform rename operation.
  It will notify the widget to rebuild if its state changed.

* `TypeOptionDataController` defines how to update the field's properties. Such as the name, the field and the type option data.

* `IFieldTypeOptionLoad` defines how to load the field's type option data. For example, when we create a new field, we use
  `NewTypeOptionLoader`. We use `FieldTypeOptionLoader` to load the existing field's type option data.

* `FieldTypeOptionEditor` is a widget that provides custom UI for each field. You can provide custom UI by extending the `TypeOptionWidgetBuilder` 

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Field_Type_Option_Widget_Builder.svg)
Field_Type_Option_Widget_Builder
* `TypeOptionWidgetBuilder` 
* 

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Field\_Type\_Option\_Editor.svg)

## Cell

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Grid\_Cell\_Builder.svg)

![file : grid\_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Grid\_Cell\_Controller.svg)
