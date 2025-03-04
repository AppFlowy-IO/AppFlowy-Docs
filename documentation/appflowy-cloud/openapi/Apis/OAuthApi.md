# OAuthApi

All URIs are relative to *https://beta.appflowy.cloud*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**gotrueToken**](OAuthApi.md#gotrueToken) | **POST** /gotrue/token | Get a new access token and refresh token based on grant type |
| [**oauthRedirectToken**](OAuthApi.md#oauthRedirectToken) | **GET** /web-api/oauth-redirect/token | Sign in with AppFlowy OAuth 2.0 |


<a name="gotrueToken"></a>
# **gotrueToken**
> gotrue_token_response gotrueToken(gotrueToken\_request)

Get a new access token and refresh token based on grant type

    This endpoint is used to obtain a new access token and refresh token based on the grant type.  

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **gotrueToken\_request** | [**gotrueToken_request**](../Models/gotrueToken_request.md)|  | |

### Return type

[**gotrue_token_response**](../Models/gotrue_token_response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

<a name="oauthRedirectToken"></a>
# **oauthRedirectToken**
> gotrue_token_response oauthRedirectToken(code, grant\_type, client\_id, client\_secret, redirect\_uri, code\_verifier)

Sign in with AppFlowy OAuth 2.0

    This endpoint is used obtain an access token from AppFlowy OAuth 2.0. This is called after user tried to sign in with AppFlowy OAuth (/web-api/oauth-redirect). This is primarily used integration with third-party applications. 

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **code** | **String**| The authorization code received from the redirect. | [default to null] |
| **grant\_type** | **String**| Type of OAuth 2.0 flow being used to exchange the authorization code for an access token. | [default to null] |
| **client\_id** | **String**| The client ID of the application | [optional] [default to null] |
| **client\_secret** | **String**| The client&#39;s secret (if applicable, for confidential clients). | [optional] [default to null] |
| **redirect\_uri** | **String**| The redirect URI used in the initial authorization request. | [optional] [default to null] |
| **code\_verifier** | **String**| Used in PKCE (Proof Key for Code Exchange) to secure public clients. | [optional] [default to null] |

### Return type

[**gotrue_token_response**](../Models/gotrue_token_response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

