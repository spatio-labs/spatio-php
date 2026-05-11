# SpatioClient\ActionsApi

Action manifest + renderer-curated \&quot;core actions\&quot; backing the command palette and key bindings.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**executeAction()**](ActionsApi.md#executeAction) | **POST** /v1/actions/execute | Renderer-side execute alias. The canonical endpoint is &#x60;POST /v1/agent/actions/execute&#x60;; this path delegates to the same handler. |
| [**getCoreAction()**](ActionsApi.md#getCoreAction) | **GET** /v1/actions/core/{id} | Fetch a single core action by id. |
| [**listAvailableActions()**](ActionsApi.md#listAvailableActions) | **GET** /v1/actions/available | List every action the agent platform exposes. |
| [**listCoreActions()**](ActionsApi.md#listCoreActions) | **GET** /v1/actions/core | List renderer-curated \&quot;core actions\&quot; (command-palette + keybindings backing). |
| [**listCoreActionsByPlatform()**](ActionsApi.md#listCoreActionsByPlatform) | **GET** /v1/actions/core/platform/{platform} | Core actions filtered to one platform. |
| [**listPlatformActions()**](ActionsApi.md#listPlatformActions) | **GET** /v1/actions/platform/{platform} | List actions tagged for a specific platform (notes, mail, ...). |


## `executeAction()`

```php
executeAction($execute_action_request): \SpatioClient\Model\ExecuteActionResponse
```

Renderer-side execute alias. The canonical endpoint is `POST /v1/agent/actions/execute`; this path delegates to the same handler.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ActionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$execute_action_request = new \SpatioClient\Model\ExecuteActionRequest(); // \SpatioClient\Model\ExecuteActionRequest

try {
    $result = $apiInstance->executeAction($execute_action_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ActionsApi->executeAction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **execute_action_request** | [**\SpatioClient\Model\ExecuteActionRequest**](../Model/ExecuteActionRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ExecuteActionResponse**](../Model/ExecuteActionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCoreAction()`

```php
getCoreAction($id): \SpatioClient\Model\CoreAction
```

Fetch a single core action by id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ActionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getCoreAction($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ActionsApi->getCoreAction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\CoreAction**](../Model/CoreAction.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAvailableActions()`

```php
listAvailableActions(): \SpatioClient\Model\ActionDescriptor[]
```

List every action the agent platform exposes.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ActionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAvailableActions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ActionsApi->listAvailableActions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\ActionDescriptor[]**](../Model/ActionDescriptor.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCoreActions()`

```php
listCoreActions(): \SpatioClient\Model\CoreActionListResponse
```

List renderer-curated \"core actions\" (command-palette + keybindings backing).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ActionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listCoreActions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ActionsApi->listCoreActions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\CoreActionListResponse**](../Model/CoreActionListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCoreActionsByPlatform()`

```php
listCoreActionsByPlatform($platform): \SpatioClient\Model\CoreActionListResponse
```

Core actions filtered to one platform.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ActionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform = 'platform_example'; // string

try {
    $result = $apiInstance->listCoreActionsByPlatform($platform);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ActionsApi->listCoreActionsByPlatform: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform** | **string**|  | |

### Return type

[**\SpatioClient\Model\CoreActionListResponse**](../Model/CoreActionListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listPlatformActions()`

```php
listPlatformActions($platform): \SpatioClient\Model\ActionDescriptor[]
```

List actions tagged for a specific platform (notes, mail, ...).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ActionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform = 'platform_example'; // string

try {
    $result = $apiInstance->listPlatformActions($platform);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ActionsApi->listPlatformActions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform** | **string**|  | |

### Return type

[**\SpatioClient\Model\ActionDescriptor[]**](../Model/ActionDescriptor.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
