# DatabaseRowsUpdatedApi

All URIs are relative to *https://beta.appflowy.cloud*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getDatabaseRowIdsUpdated**](DatabaseRowsUpdatedApi.md#getDatabaseRowIdsUpdated) | **GET** /api/workspace/{workspace_id}/database/{database_id}/row/updated | Retrieves a list of database row id which are recently updated in a selected database. |


<a name="getDatabaseRowIdsUpdated"></a>
# **getDatabaseRowIdsUpdated**
> getDatabaseRowIdsUpdated_200_response getDatabaseRowIdsUpdated(after)

Retrieves a list of database row id which are recently updated in a selected database.

    Retrieves a list of database in a selected workspace. 

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **after** | **Date**| Fetch the list of database row ids updated after the specified date and time. | [optional] [default to null] |

### Return type

[**getDatabaseRowIdsUpdated_200_response**](../Models/getDatabaseRowIdsUpdated_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

