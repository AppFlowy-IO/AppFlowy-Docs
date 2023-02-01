# Database View

## Introduction

This document explains how the Grid,Board, and Calendar shares the same data structs defined in the backend. It can be a development guide when you want to contribute to Grid,Board or Calendar. This document will be continuously updated, and any suggestions would be helpful.

## Definitions

Below you will find some quick definitions to help you read through the document.

|          |                                                                                                      |
| -------- | ---------------------------------------------------------------------------------------------------- |
| Database | AppFlowy self-defined database that manages the relation between columns,rows, and cells.            |
| Grid     | A Grid type is a simple representation of items placed in columns and rows                           |
| Board    | A Board is an project management tool designed to help visualize work, limit work-in-progress        |
| Calendar | A Calendar allows you to display data associated with dates and times in day, week or month formats. |
|          |                                                                                                      |

## Relations

Currently, AppFlowy has three types of views that share the same database. A single database can have multiple views and these views can be converted to each other. ![file : database\_view.plantuml](../../../../../uml/output/database\_view.svg)

From the DDD perspective, these views are kind of the presentation layer and the database is the combination of Application,Domain, and Infrastructure layer.

![file : database\_view.plantuml](../../../../../uml/output/database\_view-Database\_Views\_DDD.svg)

The main classes in Database are shown below.

|              |                                                                                                                                         |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| Database     | A Database struct contains the list of fields and rows                                                                                  |
| Field        | A Field contains list of `TypeOption` for different `FieldType`. The `field_ty` property determine which `TypeOption` will be used      |
| TypeOption   | A `TypeOption` represents the configuration of a column. A `TypeOption` will be serialized to opaque data and then saved in the `Field` |
| FieldType    | A `FieldType` represents the type of a column. Each `FieldType` has its own `TypeOption`                                                |
| Row          | A `Row` represents a group of related cells. The number of cells is equal to the number of the `Fields` that the database has           |
| Cell         | A `Cell` represents the data of the corresponding `FieldType`                                                                           |
| TypeCellData | Same as `Cell` but carry the `FieldType` when the `Cell` create                                                                         |

![file : database\_view.plantuml](../../../../../uml/output/database\_view\_classes-Database\_classes\_UML.svg)

## Formatting Cell

Most of the time, the raw data of cell is not human-readable. A cell doesn't know how to represent itself. It needs the `Field` information to format the data.

![file : database\_view.plantuml](../../../../../uml/output/database\_view\_classes-Read\_Cell\_Sequence.svg)

1. Get the corresponding `Database` with `database_id`
2. Get the corresponding `Field` with `field_id`
3. Get the corresponding `TypeOption` base on the current value of the `Field`'s `field_ty` property. Assuming the `field_ty` is `FieldType::Date`.
4. Get the corresponding `Row` with `row_id`
5. Get the corresponding `Cell` with `field_id`
6. Using the `DateTypeOption` to format the raw cell data.
7. Returns the formatted cell data

The formatted cell data will be different depending on the `DateFormat` and `TimeFormat` of the `DateTypeOption`.

| DateFormat     | TimeFormat     | Raw cell data |                     |
| -------------- | -------------- | ------------- | ------------------- |
| month/day/year | TwelveHour     | 1675083591    | 01/30/2023 01:00 PM |
|                | TwentyFourHour | 1675083591    | 01/30/2023 13:00    |
|                |                |               |                     |
| year-month-day | TwelveHour     | 1675083591    | 2023-01-30 01:00 PM |
|                | TwentyFourHour | 1675083591    | 2023-01-30 13:00    |
|                |                |               |                     |
