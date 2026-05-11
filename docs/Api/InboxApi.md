# SpatioClient\InboxApi

Unified inbox feed across mail, channels, DMs, mentions, and system notifications.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getInboxCounts()**](InboxApi.md#getInboxCounts) | **GET** /v1/inbox/counts | Per-bucket unread counts. |
| [**listInbox()**](InboxApi.md#listInbox) | **GET** /v1/inbox | Unified inbox feed across mail, channel mentions, DMs, system notifications. |
| [**markInboxItemRead()**](InboxApi.md#markInboxItemRead) | **PATCH** /v1/inbox/{id}/read | Mark a single inbox item as read. |
| [**workspaceGetInboxCounts()**](InboxApi.md#workspaceGetInboxCounts) | **GET** /v1/organizations/{org}/workspaces/{workspace}/inbox/counts |  |
| [**workspaceListInbox()**](InboxApi.md#workspaceListInbox) | **GET** /v1/organizations/{org}/workspaces/{workspace}/inbox |  |
| [**workspaceMarkInboxItemRead()**](InboxApi.md#workspaceMarkInboxItemRead) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/inbox/{id}/read |  |


## `getInboxCounts()`

```php
getInboxCounts(): \SpatioClient\Model\InboxCounts
```

Per-bucket unread counts.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getInboxCounts();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->getInboxCounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\InboxCounts**](../Model/InboxCounts.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listInbox()`

```php
listInbox($category, $unread_only, $limit): \SpatioClient\Model\InboxListResponse
```

Unified inbox feed across mail, channel mentions, DMs, system notifications.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$category = 'category_example'; // string
$unread_only = True; // bool
$limit = 56; // int

try {
    $result = $apiInstance->listInbox($category, $unread_only, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->listInbox: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **category** | **string**|  | [optional] |
| **unread_only** | **bool**|  | [optional] |
| **limit** | **int**|  | [optional] |

### Return type

[**\SpatioClient\Model\InboxListResponse**](../Model/InboxListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `markInboxItemRead()`

```php
markInboxItemRead($id)
```

Mark a single inbox item as read.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->markInboxItemRead($id);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->markInboxItemRead: ', $e->getMessage(), PHP_EOL;
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

## `workspaceGetInboxCounts()`

```php
workspaceGetInboxCounts($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceGetInboxCounts($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->workspaceGetInboxCounts: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListInbox()`

```php
workspaceListInbox($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListInbox($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->workspaceListInbox: ', $e->getMessage(), PHP_EOL;
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

## `workspaceMarkInboxItemRead()`

```php
workspaceMarkInboxItemRead($org, $workspace, $id)
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $apiInstance->workspaceMarkInboxItemRead($org, $workspace, $id);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->workspaceMarkInboxItemRead: ', $e->getMessage(), PHP_EOL;
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
