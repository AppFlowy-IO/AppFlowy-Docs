# Documentation for AppFlowy REST API

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://beta.appflowy.cloud/api*

| Class | Method | HTTP request | Description |
|------------ | ------------- | ------------- | -------------|
| *DatabasesApi* | [**getDatabases**](Apis/DatabasesApi.md#getdatabases) | **GET** /workspace/{workspace_id}/database | Retrieves a list of database in a workspace |
| *DefaultApi* | [**getDatabaseFields**](Apis/DefaultApi.md#getdatabasefields) | **GET** /workspace/{workspace_id}/database/{database_id}/fields | Retrieves a list of database fields in a selected database. |
*DefaultApi* | [**getDatabaseRowIds**](Apis/DefaultApi.md#getdatabaserowids) | **GET** /workspace/{workspace_id}/database/{database_id}/row | Retrieves a list of database row ids in a selected database. |
| *WorkspacesApi* | [**getWorkspaces**](Apis/WorkspacesApi.md#getworkspaces) | **GET** /workspace | Retrieves a list of all workspaces |


<a name="documentation-for-models"></a>
## Documentation for Models

 - [database](./Models/database.md)
 - [database_field](./Models/database_field.md)
 - [database_row](./Models/database_row.md)
 - [folder_view_min](./Models/folder_view_min.md)
 - [getDatabaseFields_200_response](./Models/getDatabaseFields_200_response.md)
 - [getDatabaseRowIds_200_response](./Models/getDatabaseRowIds_200_response.md)
 - [getDatabases_200_response](./Models/getDatabases_200_response.md)
 - [getWorkspaces_200_response](./Models/getWorkspaces_200_response.md)
 - [icon_type](./Models/icon_type.md)
 - [response](./Models/response.md)
 - [role](./Models/role.md)
 - [view_icon](./Models/view_icon.md)
 - [view_layout](./Models/view_layout.md)
 - [workspace](./Models/workspace.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

<a name="BearerAuth"></a>
### BearerAuth

- **Type**: HTTP Bearer Token authentication (JWT)

