# SpatioClient\KeybindingsApi

User-customizable keyboard shortcuts merged with platform defaults.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteKeyBinding()**](KeybindingsApi.md#deleteKeyBinding) | **DELETE** /v1/keybindings/{id} | Reset a binding to its platform default. |
| [**getDefaultKeyBindings()**](KeybindingsApi.md#getDefaultKeyBindings) | **GET** /v1/keybindings/defaults | Platform default key bindings (no user customizations applied). |
| [**listKeyBindings()**](KeybindingsApi.md#listKeyBindings) | **GET** /v1/keybindings | User&#39;s merged key bindings (defaults + customizations). |
| [**resetAllKeyBindings()**](KeybindingsApi.md#resetAllKeyBindings) | **POST** /v1/keybindings/reset | Reset every customization to its platform default. |
| [**updateKeyBinding()**](KeybindingsApi.md#updateKeyBinding) | **PUT** /v1/keybindings/{id} | Create or update a user key-binding customization. |
| [**validateKeyBinding()**](KeybindingsApi.md#validateKeyBinding) | **POST** /v1/keybindings/validate | Check whether a proposed binding conflicts with existing ones. |


## `deleteKeyBinding()`

```php
deleteKeyBinding($id)
```

Reset a binding to its platform default.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\KeybindingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteKeyBinding($id);
} catch (Exception $e) {
    echo 'Exception when calling KeybindingsApi->deleteKeyBinding: ', $e->getMessage(), PHP_EOL;
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

## `getDefaultKeyBindings()`

```php
getDefaultKeyBindings(): \SpatioClient\Model\KeyBindingListResponse
```

Platform default key bindings (no user customizations applied).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\KeybindingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getDefaultKeyBindings();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KeybindingsApi->getDefaultKeyBindings: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\KeyBindingListResponse**](../Model/KeyBindingListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listKeyBindings()`

```php
listKeyBindings(): \SpatioClient\Model\KeyBindingListResponse
```

User's merged key bindings (defaults + customizations).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\KeybindingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listKeyBindings();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KeybindingsApi->listKeyBindings: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\KeyBindingListResponse**](../Model/KeyBindingListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `resetAllKeyBindings()`

```php
resetAllKeyBindings()
```

Reset every customization to its platform default.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\KeybindingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $apiInstance->resetAllKeyBindings();
} catch (Exception $e) {
    echo 'Exception when calling KeybindingsApi->resetAllKeyBindings: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `updateKeyBinding()`

```php
updateKeyBinding($id, $update_key_binding_request): \SpatioClient\Model\KeyBinding
```

Create or update a user key-binding customization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\KeybindingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_key_binding_request = new \SpatioClient\Model\UpdateKeyBindingRequest(); // \SpatioClient\Model\UpdateKeyBindingRequest

try {
    $result = $apiInstance->updateKeyBinding($id, $update_key_binding_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KeybindingsApi->updateKeyBinding: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_key_binding_request** | [**\SpatioClient\Model\UpdateKeyBindingRequest**](../Model/UpdateKeyBindingRequest.md)|  | |

### Return type

[**\SpatioClient\Model\KeyBinding**](../Model/KeyBinding.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `validateKeyBinding()`

```php
validateKeyBinding($validate_key_binding_request): \SpatioClient\Model\ValidateKeyBindingResponse
```

Check whether a proposed binding conflicts with existing ones.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\KeybindingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$validate_key_binding_request = new \SpatioClient\Model\ValidateKeyBindingRequest(); // \SpatioClient\Model\ValidateKeyBindingRequest

try {
    $result = $apiInstance->validateKeyBinding($validate_key_binding_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KeybindingsApi->validateKeyBinding: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **validate_key_binding_request** | [**\SpatioClient\Model\ValidateKeyBindingRequest**](../Model/ValidateKeyBindingRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ValidateKeyBindingResponse**](../Model/ValidateKeyBindingResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
