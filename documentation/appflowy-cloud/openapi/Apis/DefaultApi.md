# DefaultApi

All URIs are relative to *https://beta.appflowy.cloud/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getDatabaseFields**](DefaultApi.md#getDatabaseFields) | **GET** /workspace/{workspace_id}/database/{database_id}/fields | Retrieves a list of database fields in a selected database. |
| [**getDatabaseRowIds**](DefaultApi.md#getDatabaseRowIds) | **GET** /workspace/{workspace_id}/database/{database_id}/row | Retrieves a list of database row ids in a selected database. |


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

