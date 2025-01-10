# DatabaseRowDetailsApi

All URIs are relative to *https://beta.appflowy.cloud*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getDatabaseRowDetails**](DatabaseRowDetailsApi.md#getDatabaseRowDetails) | **GET** /api/workspace/{workspace_id}/database/{database_id}/row/detail | Retrieves a list of database row details in a selected database. |


<a name="getDatabaseRowDetails"></a>
# **getDatabaseRowDetails**
> getDatabaseRowDetails_200_response getDatabaseRowDetails(ids, with\_doc)

Retrieves a list of database row details in a selected database.

    Retrieves a list of database row details in a selected database. 

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **ids** | **String**| A comma-separated list of database row uuids to retrieve. (e.g., ids&#x3D;uuid1,uuid2,uuid3) | [default to null] |
| **with\_doc** | **Boolean**| Include the document data for each row when set to true. | [optional] [default to null] |

### Return type

[**getDatabaseRowDetails_200_response**](../Models/getDatabaseRowDetails_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

