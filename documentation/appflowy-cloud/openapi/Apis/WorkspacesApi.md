# WorkspacesApi

All URIs are relative to *https://beta.appflowy.cloud/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getWorkspaces**](WorkspacesApi.md#getWorkspaces) | **GET** /workspace | Retrieves a list of all workspaces |


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

