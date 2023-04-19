# Database View

## Introduction

This page explains how the Grid, Board and Calendar share the same data structures defined in the backend and serves as a development guide if you want to contribute to any of these database views. This document will be continuously updated and suggestions for improvement are always welcome.

## View Definitions

Below, you will find some quick definitions to help you read through the document.

|          |                                                                                                      |
| -------- | ---------------------------------------------------------------------------------------------------- |
| Database | AppFlowy self-defined database that manages the relation between columns, rows and cells.            |
| Grid     | A Grid type is a simple representation of items placed in columns and rows.                          |
| Board    | A Board is an project management tool designed to help visualize work, limit work-in-progress.       |
| Calendar | A Calendar allows you to display data associated with dates and times in day, week or month formats. |

## Relations

Currently, three types of views can represent the same database. A single database can have multiple views and these views can be converted to each other.

![file : database\_view.plantuml](../../../../../uml/output/database\_view.svg)

## Events and Notifications

The database views use [events and notifications](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/architecture/frontend/inter-process-communication) to exchange the data between the frontend and backend. When an event is triggered, some notifications may be sent back to the frontend asynchronously. The database events are defined in [here](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/architecture/frontend/database-view/events).

![file : database\_view.plantuml](../../../../../uml/output/database\_view-Events\_\_\_Notifications.svg)

## Database Definitions

Below you will find some quick definitions about the database.

|              |                                                                                        |
| ------------ | -------------------------------------------------------------------------------------- |
| Database     | A Database struct contains the list of fields and rows                                 |
| Field        | A Field represents a column of the database. Different field has different `FieldType` |
| FieldType    | A `FieldType` represents the type of column.                                           |
| TypeOption   | A `TypeOption` represents the configuration of the `Field`.                            |
| Row          | A `Row` represents a group of related cells.                                           |
| Cell         | A `Cell` contains the data of the corresponding `FieldType`                            |
| TypeCellData | Same as `Cell` but carry the `FieldType` when the `Cell` create                        |

![file : database\_view.plantuml](../../../../../uml/output/database\_view\_classes-Database\_classes\_UML.svg)

### Database

In short, a database is just a collection of rows and columns. One can insert/remove rows and columns as needed. Each row contains a list of cells and each cell corresponds to a specific column. Each column, aka `Field` determines the kind of data stored in the cells below it.

![database.png](assets/database.png)

### Field

A Field represents a column of the database. It has a property called `field_ty`, which is an enum defined in `FieldType`. This data is stored in a database's map property called`typeOptions`: the key is the `FieldType`, and the value is the `TypeOption`.

The current field type of the column is determined by the `field_ty` property. As shown in the picture below. There are two Fields in the database.

![field.png](assets/field.png)

### FieldType

A `FieldType` represents the type of the `Field`. Currently, AppFlowy supports `text`, `numbers`, `date`, `select`, `multi-select`, `checkbox`, `URL` and `checklist` as shown in the picture below.

![field\_type.png](assets/field\_type.png)

### TypeOption

A `TypeOption` represents the configuration of the `Field`. Certain `TypeOption`s have user-defined options. For example, the `TypeOption` of a select `Field` contains the field's name and a list of possible options as shown in the picture below.

![type\_option.png](assets/type\_option.png)

On the other hand, the `TypeOption` of a number `Field` contains the name and a list of format styles:

![img.png](assets/number\_type\_option.png)

### Row

A `Row` contains a list of related cells, and each cell corresponds to a specific column. This means that the number of cells in a row is equal to the number of the `Fields` that are in the database.

![grid\_row.png](assets/grid\_row.png)

### Cell

A `Cell` contains the data of the corresponding `FieldType`.

![img.png](assets/cell.png)

Most of the time, the cell data is not human-readable and requires the `Field`'s `TypeOption` to format the data. The following image describes how the cell data gets formatted step-by-step.

![file : database\_view.plantuml](../../../../../uml/output/database\_view\_classes-Read\_Cell\_Sequence.svg)

1. Get the corresponding `Database` with `database_id.`
2. Get the corresponding `Field` with `field_id.`
3. Get the corresponding `TypeOption` base on the current value of the `Field`'s `field_ty` property. Assuming the `field_ty` is `FieldType::Date`.
4. Get the corresponding `Row` with `row_id.`
5. Get the corresponding `Cell` with `field_id.`
6. Using the `DateTypeOption` to format the raw cell data.
7. Returns the formatted cell data.

The formatted cell data will be different depending on the `DateFormat` and `TimeFormat` of the `DateTypeOption`.

| DateFormat     | TimeFormat     | Raw cell data |                     |
| -------------- | -------------- | ------------- | ------------------- |
| month/day/year | TwelveHour     | 1675083591    | 01/30/2023 01:00 PM |
|                | TwentyFourHour | 1675083591    | 01/30/2023 13:00    |
|                |                |               |                     |
| year-month-day | TwelveHour     | 1675083591    | 2023-01-30 01:00 PM |
|                | TwentyFourHour | 1675083591    | 2023-01-30 13:00    |
