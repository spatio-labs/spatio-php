# SpatioClient\PersonalAccessTokensApi

User-issued API tokens (PATs) used to authenticate against this API.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createPersonalAccessToken()**](PersonalAccessTokensApi.md#createPersonalAccessToken) | **POST** /v1/tokens | Create a new PAT. The full token is returned only once on creation; the API never reveals the secret again. |
| [**listAvailablePATScopes()**](PersonalAccessTokensApi.md#listAvailablePATScopes) | **GET** /v1/tokens/scopes | List the scope strings PATs can be issued with. |
| [**listPersonalAccessTokens()**](PersonalAccessTokensApi.md#listPersonalAccessTokens) | **GET** /v1/tokens | List the caller&#39;s personal access tokens (with available scopes). |
| [**revokePersonalAccessToken()**](PersonalAccessTokensApi.md#revokePersonalAccessToken) | **DELETE** /v1/tokens/{id} | Revoke a PAT. |
| [**updatePersonalAccessToken()**](PersonalAccessTokensApi.md#updatePersonalAccessToken) | **PATCH** /v1/tokens/{id} | Rename or re-describe a PAT (scopes are immutable). |
| [**workspaceCreatePAT()**](PersonalAccessTokensApi.md#workspaceCreatePAT) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tokens |  |
| [**workspaceListPATs()**](PersonalAccessTokensApi.md#workspaceListPATs) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tokens |  |
| [**workspaceRevokePAT()**](PersonalAccessTokensApi.md#workspaceRevokePAT) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/tokens/{id} |  |
| [**workspaceUpdatePAT()**](PersonalAccessTokensApi.md#workspaceUpdatePAT) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/tokens/{id} |  |


## `createPersonalAccessToken()`

```php
createPersonalAccessToken($create_pat_request): \SpatioClient\Model\CreatePATResponse
```

Create a new PAT. The full token is returned only once on creation; the API never reveals the secret again.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_pat_request = new \SpatioClient\Model\CreatePATRequest(); // \SpatioClient\Model\CreatePATRequest

try {
    $result = $apiInstance->createPersonalAccessToken($create_pat_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->createPersonalAccessToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_pat_request** | [**\SpatioClient\Model\CreatePATRequest**](../Model/CreatePATRequest.md)|  | |

### Return type

[**\SpatioClient\Model\CreatePATResponse**](../Model/CreatePATResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAvailablePATScopes()`

```php
listAvailablePATScopes(): \SpatioClient\Model\PATScopesResponse
```

List the scope strings PATs can be issued with.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAvailablePATScopes();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->listAvailablePATScopes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\PATScopesResponse**](../Model/PATScopesResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listPersonalAccessTokens()`

```php
listPersonalAccessTokens(): \SpatioClient\Model\PATListResponse
```

List the caller's personal access tokens (with available scopes).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listPersonalAccessTokens();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->listPersonalAccessTokens: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\PATListResponse**](../Model/PATListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokePersonalAccessToken()`

```php
revokePersonalAccessToken($id)
```

Revoke a PAT.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->revokePersonalAccessToken($id);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->revokePersonalAccessToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updatePersonalAccessToken()`

```php
updatePersonalAccessToken($id, $update_pat_request): \SpatioClient\Model\PersonalAccessToken
```

Rename or re-describe a PAT (scopes are immutable).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_pat_request = new \SpatioClient\Model\UpdatePATRequest(); // \SpatioClient\Model\UpdatePATRequest

try {
    $result = $apiInstance->updatePersonalAccessToken($id, $update_pat_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->updatePersonalAccessToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_pat_request** | [**\SpatioClient\Model\UpdatePATRequest**](../Model/UpdatePATRequest.md)|  | |

### Return type

[**\SpatioClient\Model\PersonalAccessToken**](../Model/PersonalAccessToken.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `workspaceCreatePAT()`

```php
workspaceCreatePAT($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCreatePAT($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->workspaceCreatePAT: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

### Return type

**array<string,mixed>**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `workspaceListPATs()`

```php
workspaceListPATs($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListPATs($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->workspaceListPATs: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |

### Return type

**array<string,mixed>**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `workspaceRevokePAT()`

```php
workspaceRevokePAT($org, $workspace, $id)
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $apiInstance->workspaceRevokePAT($org, $workspace, $id);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->workspaceRevokePAT: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **id** | **string**|  | |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `workspaceUpdatePAT()`

```php
workspaceUpdatePAT($org, $workspace, $id, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PersonalAccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceUpdatePAT($org, $workspace, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PersonalAccessTokensApi->workspaceUpdatePAT: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

### Return type

**array<string,mixed>**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
