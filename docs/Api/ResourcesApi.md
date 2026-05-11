# SpatioClient\ResourcesApi

Per-resource ACL grants — &#x60;/v1/resources/{platform}/{resourceId}/permissions/_*&#x60;.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listResourcePermissionGrants()**](ResourcesApi.md#listResourcePermissionGrants) | **GET** /v1/resources/{platform}/{resourceId}/permissions | List access grants on a resource (per-resource ACL). |
| [**revokeResourcePermissionGrant()**](ResourcesApi.md#revokeResourcePermissionGrant) | **DELETE** /v1/resources/{platform}/{resourceId}/permissions/{grantId} | Revoke an access grant. |
| [**setResourcePermissionGrant()**](ResourcesApi.md#setResourcePermissionGrant) | **POST** /v1/resources/{platform}/{resourceId}/permissions | Create or update an access grant. |


## `listResourcePermissionGrants()`

```php
listResourcePermissionGrants($platform, $resource_id): array<string,mixed>
```

List access grants on a resource (per-resource ACL).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ResourcesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform = 'platform_example'; // string
$resource_id = 'resource_id_example'; // string

try {
    $result = $apiInstance->listResourcePermissionGrants($platform, $resource_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ResourcesApi->listResourcePermissionGrants: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform** | **string**|  | |
| **resource_id** | **string**|  | |

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

## `revokeResourcePermissionGrant()`

```php
revokeResourcePermissionGrant($platform, $resource_id, $grant_id)
```

Revoke an access grant.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ResourcesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform = 'platform_example'; // string
$resource_id = 'resource_id_example'; // string
$grant_id = 'grant_id_example'; // string

try {
    $apiInstance->revokeResourcePermissionGrant($platform, $resource_id, $grant_id);
} catch (Exception $e) {
    echo 'Exception when calling ResourcesApi->revokeResourcePermissionGrant: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform** | **string**|  | |
| **resource_id** | **string**|  | |
| **grant_id** | **string**|  | |

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

## `setResourcePermissionGrant()`

```php
setResourcePermissionGrant($platform, $resource_id, $request_body): array<string,mixed>
```

Create or update an access grant.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ResourcesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform = 'platform_example'; // string
$resource_id = 'resource_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->setResourcePermissionGrant($platform, $resource_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ResourcesApi->setResourcePermissionGrant: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform** | **string**|  | |
| **resource_id** | **string**|  | |
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
