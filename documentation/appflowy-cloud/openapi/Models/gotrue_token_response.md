# gotrue_token_response
## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **access\_token** | **String** | The token that clients use to make authenticated requests to the server or API. It is a bearer token that provides temporary, secure access to server resources.  | [optional] [default to null] |
| **token\_type** | **String** | The type of token. It is always \&quot;Bearer\&quot;.  | [optional] [default to null] |
| **expires\_in** | **Integer** | Seconds until the access_token expires.  | [optional] [default to null] |
| **expires\_at** | **Integer** | A timestamp in seconds indicating the exact time at which the access_token will expire.  | [optional] [default to null] |
| **refresh\_token** | **String** | The refresh token is used to obtain a new access_token once the current access_token expires. Refresh tokens are usually long-lived and are stored securely by the client.  | [optional] [default to null] |
| **user** | [**Object**](.md) | The user object contains information about the user that is currently authenticated.  | [optional] [default to null] |
| **provider\_access\_token** | **String** | The access token from the provider.  | [optional] [default to null] |
| **provider\_refresh\_token** | **String** | The refresh token from the provider.  | [optional] [default to null] |

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

