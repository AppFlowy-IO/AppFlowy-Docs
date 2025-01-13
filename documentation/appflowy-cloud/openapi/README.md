# Documentation for AppFlowy REST API

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://beta.appflowy.cloud*

| Class | Method | HTTP request | Description |
|------------ | ------------- | ------------- | -------------|
| *DatabaseFieldsApi* | [**getDatabaseFields**](Apis/DatabaseFieldsApi.md#getdatabasefields) | **GET** /api/workspace/{workspace_id}/database/{database_id}/fields | Retrieves a list of database fields in a selected database. |
| *DatabaseRowDetailsApi* | [**getDatabaseRowDetails**](Apis/DatabaseRowDetailsApi.md#getdatabaserowdetails) | **GET** /api/workspace/{workspace_id}/database/{database_id}/row/detail | Retrieves a list of database row details in a selected database. |
| *DatabaseRowsApi* | [**createDatabaseRow**](Apis/DatabaseRowsApi.md#createdatabaserow) | **POST** /api/workspace/{workspace_id}/database/{database_id}/row | Creates a new row in a selected database. |
*DatabaseRowsApi* | [**getDatabaseRowIds**](Apis/DatabaseRowsApi.md#getdatabaserowids) | **GET** /api/workspace/{workspace_id}/database/{database_id}/row | Retrieves a list of database row ids in a selected database. |
*DatabaseRowsApi* | [**upsertDatabaseRow**](Apis/DatabaseRowsApi.md#upsertdatabaserow) | **PUT** /api/workspace/{workspace_id}/database/{database_id}/row | Updates or creates a row in a selected database. (Upsert) |
| *DatabaseRowsUpdatedApi* | [**getDatabaseRowIdsUpdated**](Apis/DatabaseRowsUpdatedApi.md#getdatabaserowidsupdated) | **GET** /api/workspace/{workspace_id}/database/{database_id}/row/updated | Retrieves a list of database row id which are recently updated in a selected database. |
| *DatabasesApi* | [**getDatabases**](Apis/DatabasesApi.md#getdatabases) | **GET** /api/workspace/{workspace_id}/database | Retrieves a list of database in a workspace |
| *WorkspacesApi* | [**getWorkspaces**](Apis/WorkspacesApi.md#getworkspaces) | **GET** /api/workspace | Retrieves a list of all workspaces |


<a name="documentation-for-models"></a>
## Documentation for Models

 - [add_database_row](./Models/add_database_row.md)
 - [createDatabaseRow_200_response](./Models/createDatabaseRow_200_response.md)
 - [database](./Models/database.md)
 - [database_field](./Models/database_field.md)
 - [database_row](./Models/database_row.md)
 - [database_row_detail](./Models/database_row_detail.md)
 - [database_row_updated](./Models/database_row_updated.md)
 - [folder_view_min](./Models/folder_view_min.md)
 - [getDatabaseFields_200_response](./Models/getDatabaseFields_200_response.md)
 - [getDatabaseRowDetails_200_response](./Models/getDatabaseRowDetails_200_response.md)
 - [getDatabaseRowIdsUpdated_200_response](./Models/getDatabaseRowIdsUpdated_200_response.md)
 - [getDatabaseRowIds_200_response](./Models/getDatabaseRowIds_200_response.md)
 - [getDatabases_200_response](./Models/getDatabases_200_response.md)
 - [getWorkspaces_200_response](./Models/getWorkspaces_200_response.md)
 - [icon_type](./Models/icon_type.md)
 - [response](./Models/response.md)
 - [role](./Models/role.md)
 - [upsertDatabaseRow_200_response](./Models/upsertDatabaseRow_200_response.md)
 - [upsert_database_row](./Models/upsert_database_row.md)
 - [view_icon](./Models/view_icon.md)
 - [view_layout](./Models/view_layout.md)
 - [workspace](./Models/workspace.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

<a name="BearerAuth"></a>
### BearerAuth

- **Type**: HTTP Bearer Token authentication (JWT)

