# Events and Notifications

## Events
Events are used in the [communication](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/architecture/frontend/inter-process-communication) between the frontend and the backend.
If you interested in the process about generating the events files, please check [this](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/architecture/backend/event) out.
This document explains the events defined in the database scope.


| DatabaseEvent           |                                                                                                 |
|-------------------------|-------------------------------------------------------------------------------------------------|
| GetDatabase             | Create the data including list of `Field` and list of `Row` of the database                     |
| GetDatabaseSetting      | Get the settings including filters/sorts configuration of the database                          |
| UpdateDatabaseSetting   | Update the settings of the database                                                             |
| GetAllFilters           | Return all the filter configurations that the database has                                      |
| GetAllSorts             | Return all the sort configuration that the database has                                         |
| DeleteAllSorts          | Delete all the sort configuration of the database                                               |
| GetFields               | Get all the fields of the database                                                              |
| UpdateField             | Update the field of the database                                                                |
| UpdateFieldTypeOption   | Update the `TypeOption` of the field of the database                                            |
| DeleteField             | Delete the field of the database                                                                |
| UpdateFieldType         | Modify the type of the field                                                                    |
| DuplicateField          | Duplicate the field of the database                                                             |
| GetTypeOption           | Get the `TypeOption` for specific field type of the field                                       |
| CreateTypeOption        | Create `TypeOption` for specific field type                                                     |
| CreateSelectOption      | Create a new option. It's used when the field type is SingleSelect, Multi-select, and Checklist |
| GetSelectOptionCellData | Get the cell data of the option                                                                 |
| UpdateSelectOption      | Update the option content                                                                       |
| CreateRow               | Create a new row in the database                                                                |
| GetRow                  | Get the data of the row                                                                         |
| DeleteRow               | Delete the row in the database                                                                  |
| DuplicateRow            | Duplicate a row                                                                                 |
| GetCell                 | Get the data of the cell                                                                        |
| UpdateCell              | Update the data of the cell                                                                     |
| UpdateSelectOptionCell  | Update the data of the cell when the field type is SingleSelect, Multi-select, and Checklist    |
| UpdateDateCell          | Update the data of the cell when the field type is Date                                         |


## Notifications
| DatabaseNotification        |                                                                                                                    |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------|
| DidUpdateViewRows           | Trigger after inserting/deleting/updating a row                                                                    |
| DidUpdateViewRowsVisibility | Trigger when the visibility of the row was changed. For example, updating the filter will trigger the notification |
| DidUpdateFields             | Trigger after inserting/deleting/updating a field                                                                  |
| DidUpdateCell               | Trigger after editing a cell                                                                                       |
| DidUpdateField              | Trigger after editing a field properties including rename,update type option, etc.                                 |
| DidUpdateGroups             | Trigger after the number of groups is changed                                                                      |
| DidUpdateGroupRow           | Trigger after inserting/deleting/updating/moving a row                                                             |
| DidGroupByField             | Trigger when setting a new grouping field                                                                          |
| DidUpdateFilter             | Trigger after inserting/deleting/updating a filter                                                                 |
| DidUpdateSort               | Trigger after inserting/deleting/updating a sort                                                                   |
| DidReorderRows              | Trigger after the sort configurations are changed                                                                  |
| DidReorderSingleRow         | Trigger after editing the row that hit the sort rule                                                               |
| DidUpdateSetting            | Trigger when the settings of the database are changed                                                              |
