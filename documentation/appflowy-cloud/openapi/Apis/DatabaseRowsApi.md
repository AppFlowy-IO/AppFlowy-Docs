# DatabaseRowsApi

All URIs are relative to *https://beta.appflowy.cloud*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createDatabaseRow**](DatabaseRowsApi.md#createDatabaseRow) | **POST** /api/workspace/{workspace_id}/database/{database_id}/row | Creates a new row in a selected database. |
| [**getDatabaseRowIds**](DatabaseRowsApi.md#getDatabaseRowIds) | **GET** /api/workspace/{workspace_id}/database/{database_id}/row | Retrieves a list of database row ids in a selected database. |
| [**upsertDatabaseRow**](DatabaseRowsApi.md#upsertDatabaseRow) | **PUT** /api/workspace/{workspace_id}/database/{database_id}/row | Updates or creates a row in a selected database. (Upsert) |


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

<a name="upsertDatabaseRow"></a>
# **upsertDatabaseRow**
> upsertDatabaseRow_200_response upsertDatabaseRow(upsert\_database\_row)

Updates or creates a row in a selected database. (Upsert)

    Given a key, updates a row in a selected database. If the row does not exist, creates a new row. 

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **upsert\_database\_row** | [**upsert_database_row**](../Models/upsert_database_row.md)|  | |

### Return type

[**upsertDatabaseRow_200_response**](../Models/upsertDatabaseRow_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

