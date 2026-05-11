# SpatioClient\OAuthApi

OAuth 2.1 + OpenID Connect 1.0 authorization server. Third-party apps register here, redirect users through the consent flow, and receive access tokens (and id_tokens when &#x60;openid&#x60; scope is granted). See packages/api-spec/CLONE-PARITY.md for the clone-builder perspective.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getJWKS()**](OAuthApi.md#getJWKS) | **GET** /.well-known/jwks.json | JSON Web Key Set for id_token verification (RFC 7517). |
| [**getOAuthDiscovery()**](OAuthApi.md#getOAuthDiscovery) | **GET** /.well-known/oauth-authorization-server | OAuth 2.1 authorization server metadata (RFC 8414). |
| [**getOpenIDConfiguration()**](OAuthApi.md#getOpenIDConfiguration) | **GET** /.well-known/openid-configuration | OpenID Connect Discovery 1.0 metadata. |
| [**getUserInfo()**](OAuthApi.md#getUserInfo) | **GET** /oauth2/userinfo | OIDC UserInfo (OpenID Connect Core 1.0 §5.3). |
| [**oauthAuthorize()**](OAuthApi.md#oauthAuthorize) | **GET** /oauth2/authorize | OAuth 2.1 authorization endpoint (RFC 6749 + 7636 PKCE). |
| [**oauthIntrospect()**](OAuthApi.md#oauthIntrospect) | **POST** /oauth2/introspect | RFC 7662 token introspection. Accepts both OAuth access tokens and PATs. |
| [**oauthRevoke()**](OAuthApi.md#oauthRevoke) | **POST** /oauth2/revoke | RFC 7009 token revocation. Idempotent. |
| [**oauthToken()**](OAuthApi.md#oauthToken) | **POST** /oauth2/token | Exchange authorization code or refresh token for an access token (+ id_token if &#x60;openid&#x60; scope). |
| [**postUserInfo()**](OAuthApi.md#postUserInfo) | **POST** /oauth2/userinfo | Same as GET /oauth2/userinfo. Provided for clients that send the bearer in the body. |
| [**registerOAuthClient()**](OAuthApi.md#registerOAuthClient) | **POST** /oauth2/register | Register a new OAuth 2.1 client (RFC 7591 dynamic client registration). |


## `getJWKS()`

```php
getJWKS(): \SpatioClient\Model\JWKS
```

JSON Web Key Set for id_token verification (RFC 7517).

The set of public keys RPs use to verify Spatio-issued id_tokens. Cached for 5 minutes at the edge. Always includes the currently-active signing key plus any retired keys that may still be in circulation (id_token TTL is 1 hour + slack).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getJWKS();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->getJWKS: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\JWKS**](../Model/JWKS.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getOAuthDiscovery()`

```php
getOAuthDiscovery(): \SpatioClient\Model\DiscoveryDocument
```

OAuth 2.1 authorization server metadata (RFC 8414).

Returns the canonical metadata for the Spatio OAuth 2.1 + OpenID Connect server. Third-party RPs use this to auto-discover endpoint URLs, supported scopes, and signing algorithms.  Identical payload to `/.well-known/openid-configuration` — either path is acceptable; OIDC clients prefer the openid-configuration alias.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getOAuthDiscovery();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->getOAuthDiscovery: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\DiscoveryDocument**](../Model/DiscoveryDocument.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getOpenIDConfiguration()`

```php
getOpenIDConfiguration(): \SpatioClient\Model\DiscoveryDocument
```

OpenID Connect Discovery 1.0 metadata.

Alias of `/.well-known/oauth-authorization-server`. Provided so OIDC client libraries (NextAuth, Auth.js, oidc-client-ts, passport-openidconnect) auto-detect Spatio as an OIDC provider via their `wellKnown` / `discoveryUrl` config field.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getOpenIDConfiguration();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->getOpenIDConfiguration: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\DiscoveryDocument**](../Model/DiscoveryDocument.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUserInfo()`

```php
getUserInfo(): \SpatioClient\Model\UserInfoResponse
```

OIDC UserInfo (OpenID Connect Core 1.0 §5.3).

Returns user claims gated by the scopes on the presenting access token. `sub` is always returned; `email`, `name`, etc. require their respective scopes.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getUserInfo();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->getUserInfo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\UserInfoResponse**](../Model/UserInfoResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `oauthAuthorize()`

```php
oauthAuthorize($client_id, $redirect_uri, $response_type, $code_challenge, $code_challenge_method, $scope, $state, $nonce, $prompt, $max_age)
```

OAuth 2.1 authorization endpoint (RFC 6749 + 7636 PKCE).

Browser-redirect endpoint. Validates the client + redirect_uri, packs the request into a signed JWT, and 302s the user's browser to the consent UI. The consent UI then POSTs to `/oauth2/authorize/confirm` with the user's decision.  OIDC additions: `scope=openid+profile+email`, `nonce`, `prompt` (none|login|consent), `max_age`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$client_id = 'client_id_example'; // string
$redirect_uri = 'redirect_uri_example'; // string
$response_type = 'response_type_example'; // string
$code_challenge = 'code_challenge_example'; // string
$code_challenge_method = 'code_challenge_method_example'; // string
$scope = 'scope_example'; // string
$state = 'state_example'; // string
$nonce = 'nonce_example'; // string
$prompt = 'prompt_example'; // string
$max_age = 56; // int

try {
    $apiInstance->oauthAuthorize($client_id, $redirect_uri, $response_type, $code_challenge, $code_challenge_method, $scope, $state, $nonce, $prompt, $max_age);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->oauthAuthorize: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **client_id** | **string**|  | |
| **redirect_uri** | **string**|  | |
| **response_type** | **string**|  | |
| **code_challenge** | **string**|  | |
| **code_challenge_method** | **string**|  | |
| **scope** | **string**|  | [optional] |
| **state** | **string**|  | [optional] |
| **nonce** | **string**|  | [optional] |
| **prompt** | **string**|  | [optional] |
| **max_age** | **int**|  | [optional] |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `oauthIntrospect()`

```php
oauthIntrospect($token): \SpatioClient\Model\IntrospectionResponse
```

RFC 7662 token introspection. Accepts both OAuth access tokens and PATs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$token = 'token_example'; // string

try {
    $result = $apiInstance->oauthIntrospect($token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->oauthIntrospect: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token** | **string**|  | |

### Return type

[**\SpatioClient\Model\IntrospectionResponse**](../Model/IntrospectionResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `oauthRevoke()`

```php
oauthRevoke($token)
```

RFC 7009 token revocation. Idempotent.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$token = 'token_example'; // string

try {
    $apiInstance->oauthRevoke($token);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->oauthRevoke: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token** | **string**|  | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `oauthToken()`

```php
oauthToken($grant_type, $code, $code_verifier, $redirect_uri, $refresh_token, $client_id, $client_secret): \SpatioClient\Model\TokenResponse
```

Exchange authorization code or refresh token for an access token (+ id_token if `openid` scope).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$grant_type = 'grant_type_example'; // string
$code = 'code_example'; // string | Required for authorization_code grant.
$code_verifier = 'code_verifier_example'; // string | PKCE verifier — required for authorization_code grant.
$redirect_uri = 'redirect_uri_example'; // string
$refresh_token = 'refresh_token_example'; // string | Required for refresh_token grant.
$client_id = 'client_id_example'; // string
$client_secret = 'client_secret_example'; // string

try {
    $result = $apiInstance->oauthToken($grant_type, $code, $code_verifier, $redirect_uri, $refresh_token, $client_id, $client_secret);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->oauthToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **grant_type** | **string**|  | |
| **code** | **string**| Required for authorization_code grant. | [optional] |
| **code_verifier** | **string**| PKCE verifier — required for authorization_code grant. | [optional] |
| **redirect_uri** | **string**|  | [optional] |
| **refresh_token** | **string**| Required for refresh_token grant. | [optional] |
| **client_id** | **string**|  | [optional] |
| **client_secret** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\TokenResponse**](../Model/TokenResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postUserInfo()`

```php
postUserInfo(): \SpatioClient\Model\UserInfoResponse
```

Same as GET /oauth2/userinfo. Provided for clients that send the bearer in the body.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->postUserInfo();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->postUserInfo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\UserInfoResponse**](../Model/UserInfoResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `registerOAuthClient()`

```php
registerOAuthClient($client_registration_request): \SpatioClient\Model\ClientRegistrationResponse
```

Register a new OAuth 2.1 client (RFC 7591 dynamic client registration).

Returns a fresh `client_id` (and, for confidential clients, `client_secret`) plus a one-time `registration_access_token` the client can use later to update its registration. Public clients (mobile, SPA) MUST use `token_endpoint_auth_method: none` and PKCE.  Rate-limited to 10 registrations per hour per source IP.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$client_registration_request = new \SpatioClient\Model\ClientRegistrationRequest(); // \SpatioClient\Model\ClientRegistrationRequest

try {
    $result = $apiInstance->registerOAuthClient($client_registration_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->registerOAuthClient: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **client_registration_request** | [**\SpatioClient\Model\ClientRegistrationRequest**](../Model/ClientRegistrationRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ClientRegistrationResponse**](../Model/ClientRegistrationResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
