# WorkspacesApi

All URIs are relative to *https://beta.appflowy.cloud*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getWorkspaceFolder**](WorkspacesApi.md#getWorkspaceFolder) | **GET** /api/workspace/{workspace_id}/folder | Retrieves workspace folder or subfolder |
| [**getWorkspaces**](WorkspacesApi.md#getWorkspaces) | **GET** /api/workspace | Retrieves a list of all workspaces |


<a name="getWorkspaceFolder"></a>
# **getWorkspaceFolder**
> getWorkspaceFolder_200_response getWorkspaceFolder(depth, root\_view\_id)

Retrieves workspace folder or subfolder

    This endpoint fetches folder structure of a workspace. 

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **depth** | **Integer**| Maximum depth of the folder structure to return. Default is 1. | [optional] [default to null] |
| **root\_view\_id** | **String**| Root view id of the folder structure tree. By default, it is the workspace id. Use a different root view id if you want to retrieve subfolders. | [optional] [default to null] |

### Return type

[**getWorkspaceFolder_200_response**](../Models/getWorkspaceFolder_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

<a name="getWorkspaces"></a>
# **getWorkspaces**
> getWorkspaces_200_response getWorkspaces(include\_member\_count, include\_role)

Retrieves a list of all workspaces

    This endpoint fetches a list of workspaces along with detailed information about each workspace, such as the workspace ID, owner information, and workspace properties like name, type, and icon. 

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **include\_member\_count** | **Boolean**| Include the count of members in each workspace when set to true. | [optional] [default to null] |
| **include\_role** | **Boolean**| Include the role of the user making the request in the workspace details when set to true. | [optional] [default to null] |

### Return type

[**getWorkspaces_200_response**](../Models/getWorkspaces_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

