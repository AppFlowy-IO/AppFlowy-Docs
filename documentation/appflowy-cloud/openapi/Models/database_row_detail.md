# database_row_detail
## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **id** | **UUID** | The unique identifier for the database row. | [optional] [default to null] |
| **cells** | [**Object**](.md) | A dictionary of cell values for the database row. {   \&quot;field_id\&quot;: cell_value,   ... } cell_value depends on the field type.  | [optional] [default to null] |
| **has\_doc** | **Boolean** | A boolean indicating whether the database row has a document.  | [optional] [default to null] |
| **doc** | **String** | text or markdown document for the database row. available if rows has doc and client request for it using &#x60;with_doc&#x60; query parameter.  | [optional] [default to null] |

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

