# folder_view
## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **view\_id** | **UUID** | The unique identifier for a page. | [optional] [default to null] |
| **name** | **String** | The name of the page. | [optional] [default to null] |
| **icon** | [**view_icon**](view_icon.md) |  | [optional] [default to null] |
| **is\_space** | **Boolean** | Whether the page is a space. | [optional] [default to null] |
| **is\_private** | **Boolean** | Whether the space is private. | [optional] [default to null] |
| **is\_published** | **Boolean** | Whether the space is published. | [optional] [default to null] |
| **layout** | [**view_layout**](view_layout.md) |  | [optional] [default to null] |
| **created\_at** | **Date** | The ISO 8601 date and time when the page was created. | [optional] [default to null] |
| **last\_edited\_time** | **Date** | The ISO 8601 date and time when the page was last edited. | [optional] [default to null] |
| **is\_locked** | **Boolean** | Whether the page is locked. If not present, the page is not locked. | [optional] [default to null] |
| **extra** | [**Object**](.md) | Document meta data | [optional] [default to null] |
| **children** | [**List**](folder_view.md) | The children of the page. | [optional] [default to null] |

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

