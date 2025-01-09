# upsert_database_row
## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **pre\_hash** | **String** | A string value that that will be used to calculate the hash of the row, which will become the row&#39;s unique identifier.  | [optional] [default to null] |
| **cells** | [**Object**](.md) | The cells of the database row. {   \&quot;key\&quot;: value,   ... } key: field_id or field_name value: depends on the field type (Server will attempt to convert the value to the field type)  | [optional] [default to null] |
| **document** | **String** | The document content of the database row, in Markdown format.  | [optional] [default to null] |

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

