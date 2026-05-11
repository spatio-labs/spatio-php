# SpatioClient\LogosApi

Domain/email logo lookups (CDN-cached).

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getDomainLogo()**](LogosApi.md#getDomainLogo) | **GET** /v1/logos/domain/{domain} | Resolve a domain to its logo URL (CDN-cached 24h). |
| [**getEmailLogo()**](LogosApi.md#getEmailLogo) | **GET** /v1/logos/email/{email} | Resolve an email address to its domain logo URL. |
| [**getLogosBatch()**](LogosApi.md#getLogosBatch) | **POST** /v1/logos/batch | Batch-resolve a list of domains/emails to logo URLs in one call. |


## `getDomainLogo()`

```php
getDomainLogo($domain): \SpatioClient\Model\GetDomainLogo200Response
```

Resolve a domain to its logo URL (CDN-cached 24h).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\LogosApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$domain = 'domain_example'; // string

try {
    $result = $apiInstance->getDomainLogo($domain);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LogosApi->getDomainLogo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **domain** | **string**|  | |

### Return type

[**\SpatioClient\Model\GetDomainLogo200Response**](../Model/GetDomainLogo200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEmailLogo()`

```php
getEmailLogo($email): array<string,mixed>
```

Resolve an email address to its domain logo URL.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\LogosApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$email = 'email_example'; // string

try {
    $result = $apiInstance->getEmailLogo($email);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LogosApi->getEmailLogo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **email** | **string**|  | |

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

## `getLogosBatch()`

```php
getLogosBatch($request_body): array<string,mixed>
```

Batch-resolve a list of domains/emails to logo URLs in one call.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\LogosApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->getLogosBatch($request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LogosApi->getLogosBatch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
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
