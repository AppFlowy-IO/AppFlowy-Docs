# DefaultApi

All URIs are relative to *https://beta.appflowy.cloud/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createDatabaseRow**](DefaultApi.md#createDatabaseRow) | **POST** /workspace/{workspace_id}/database/{database_id}/row | Creates a new row in a selected database. |
| [**getDatabaseFields**](DefaultApi.md#getDatabaseFields) | **GET** /workspace/{workspace_id}/database/{database_id}/fields | Retrieves a list of database fields in a selected database. |
| [**getDatabaseRowDetails**](DefaultApi.md#getDatabaseRowDetails) | **GET** /workspace/{workspace_id}/database/{database_id}/row/detail | Retrieves a list of database row details in a selected database. |
| [**getDatabaseRowIds**](DefaultApi.md#getDatabaseRowIds) | **GET** /workspace/{workspace_id}/database/{database_id}/row | Retrieves a list of database row ids in a selected database. |


<a name="createDatabaseRow"></a>
# **createDatabaseRow**
> createDatabaseRow_200_response createDatabaseRow(add\_database\_row)

Creates a new row in a selected database.

    Creates a new row in a selected database. 

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **add\_database\_row** | [**add_database_row**](../Models/add_database_row.md)|  | |

### Return type

[**createDatabaseRow_200_response**](../Models/createDatabaseRow_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

<a name="getDatabaseFields"></a>
# **getDatabaseFields**
> getDatabaseFields_200_response getDatabaseFields()

Retrieves a list of database fields in a selected database.

    Retrieves a list of database in a selected workspace. 

### Parameters
This endpoint does not need any parameter.

### Return type

[**getDatabaseFields_200_response**](../Models/getDatabaseFields_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

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

<a name="getDatabaseRowIds"></a>
# **getDatabaseRowIds**
> getDatabaseRowIds_200_response getDatabaseRowIds()

Retrieves a list of database row ids in a selected database.

    Retrieves a list of database in a selected workspace. 

### Parameters
This endpoint does not need any parameter.

### Return type

[**getDatabaseRowIds_200_response**](../Models/getDatabaseRowIds_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

