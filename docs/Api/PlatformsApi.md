# SpatioClient\PlatformsApi

Installable-platform catalog, manifest discovery, data plane (query/exec/migrate/tables), secrets, and backend tokens.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addPlatformProviderAccount()**](PlatformsApi.md#addPlatformProviderAccount) | **POST** /v1/platforms/{platformId}/providers/{provider}/accounts | Add a connected account for a platform/provider pair. |
| [**createOrUpdatePlatformSecret()**](PlatformsApi.md#createOrUpdatePlatformSecret) | **POST** /v1/platforms/{platformId}/secrets | Create or update a secret value. |
| [**deletePlatformSecret()**](PlatformsApi.md#deletePlatformSecret) | **DELETE** /v1/platforms/{platformId}/secrets/{name} | Delete a secret. |
| [**execPlatformData()**](PlatformsApi.md#execPlatformData) | **POST** /v1/platforms/{platformId}/exec | Run an INSERT/UPDATE/DELETE statement against a platform&#39;s store. |
| [**exportPlatformSecrets()**](PlatformsApi.md#exportPlatformSecrets) | **GET** /v1/platforms/{platformId}/secrets/export | Export all secrets for a platform (values included). Caller must be the platform owner. |
| [**generatePlatformBackendToken()**](PlatformsApi.md#generatePlatformBackendToken) | **POST** /v1/platforms/{platformId}/backend-token | Generate a short-lived backend JWT a platform&#39;s worker can use to call back into platform-service. |
| [**getPlatformCatalog()**](PlatformsApi.md#getPlatformCatalog) | **GET** /v1/catalog/platforms | List the global platform catalog — every platform that exists, not just the ones the caller has installed. |
| [**getPlatformManifest()**](PlatformsApi.md#getPlatformManifest) | **GET** /v1/platforms/{platformId}/manifest | Fetch a platform&#39;s manifest (capabilities, schema, UI metadata). |
| [**listPlatformAccounts()**](PlatformsApi.md#listPlatformAccounts) | **GET** /v1/platforms/{platformId}/accounts | List accounts the caller has connected for a platform. |
| [**listPlatformProviders()**](PlatformsApi.md#listPlatformProviders) | **GET** /v1/platforms/{platformId}/providers | Discover supported providers + capabilities for a platform. |
| [**listPlatformSecrets()**](PlatformsApi.md#listPlatformSecrets) | **GET** /v1/platforms/{platformId}/secrets | List secret keys (values redacted). |
| [**listPlatformTables()**](PlatformsApi.md#listPlatformTables) | **GET** /v1/platforms/{platformId}/tables | List tables in a platform&#39;s data store. |
| [**listPlatforms()**](PlatformsApi.md#listPlatforms) | **GET** /v1/platforms | List installed platforms for the sidebar. |
| [**queryPlatformData()**](PlatformsApi.md#queryPlatformData) | **POST** /v1/platforms/{platformId}/query | Run a SELECT query against a platform&#39;s data store. |
| [**runPlatformMigrations()**](PlatformsApi.md#runPlatformMigrations) | **POST** /v1/platforms/{platformId}/migrate | Run pending migrations for a platform. |


## `addPlatformProviderAccount()`

```php
addPlatformProviderAccount($platform_id, $provider, $request_body): array<string,mixed>
```

Add a connected account for a platform/provider pair.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string
$provider = 'provider_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->addPlatformProviderAccount($platform_id, $provider, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->addPlatformProviderAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |
| **provider** | **string**|  | |
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

## `createOrUpdatePlatformSecret()`

```php
createOrUpdatePlatformSecret($platform_id, $request_body): array<string,mixed>
```

Create or update a secret value.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->createOrUpdatePlatformSecret($platform_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->createOrUpdatePlatformSecret: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |
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

## `deletePlatformSecret()`

```php
deletePlatformSecret($platform_id, $name)
```

Delete a secret.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string
$name = 'name_example'; // string

try {
    $apiInstance->deletePlatformSecret($platform_id, $name);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->deletePlatformSecret: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |
| **name** | **string**|  | |

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

## `execPlatformData()`

```php
execPlatformData($platform_id, $request_body): array<string,mixed>
```

Run an INSERT/UPDATE/DELETE statement against a platform's store.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->execPlatformData($platform_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->execPlatformData: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |
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

## `exportPlatformSecrets()`

```php
exportPlatformSecrets($platform_id): array<string,mixed>
```

Export all secrets for a platform (values included). Caller must be the platform owner.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string

try {
    $result = $apiInstance->exportPlatformSecrets($platform_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->exportPlatformSecrets: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |

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

## `generatePlatformBackendToken()`

```php
generatePlatformBackendToken($platform_id): array<string,mixed>
```

Generate a short-lived backend JWT a platform's worker can use to call back into platform-service.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string

try {
    $result = $apiInstance->generatePlatformBackendToken($platform_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->generatePlatformBackendToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |

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

## `getPlatformCatalog()`

```php
getPlatformCatalog(): array<string,mixed>
```

List the global platform catalog — every platform that exists, not just the ones the caller has installed.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getPlatformCatalog();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->getPlatformCatalog: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `getPlatformManifest()`

```php
getPlatformManifest($platform_id): array<string,mixed>
```

Fetch a platform's manifest (capabilities, schema, UI metadata).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string

try {
    $result = $apiInstance->getPlatformManifest($platform_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->getPlatformManifest: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |

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

## `listPlatformAccounts()`

```php
listPlatformAccounts($platform_id): array<string,mixed>
```

List accounts the caller has connected for a platform.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string

try {
    $result = $apiInstance->listPlatformAccounts($platform_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->listPlatformAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |

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

## `listPlatformProviders()`

```php
listPlatformProviders($platform_id): array<string,mixed>
```

Discover supported providers + capabilities for a platform.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string

try {
    $result = $apiInstance->listPlatformProviders($platform_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->listPlatformProviders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |

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

## `listPlatformSecrets()`

```php
listPlatformSecrets($platform_id): array<string,mixed>
```

List secret keys (values redacted).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string

try {
    $result = $apiInstance->listPlatformSecrets($platform_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->listPlatformSecrets: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |

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

## `listPlatformTables()`

```php
listPlatformTables($platform_id): array<string,mixed>
```

List tables in a platform's data store.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string

try {
    $result = $apiInstance->listPlatformTables($platform_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->listPlatformTables: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |

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

## `listPlatforms()`

```php
listPlatforms(): array<string,mixed>
```

List installed platforms for the sidebar.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listPlatforms();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->listPlatforms: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `queryPlatformData()`

```php
queryPlatformData($platform_id, $request_body): array<string,mixed>
```

Run a SELECT query against a platform's data store.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->queryPlatformData($platform_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->queryPlatformData: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |
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

## `runPlatformMigrations()`

```php
runPlatformMigrations($platform_id): array<string,mixed>
```

Run pending migrations for a platform.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\PlatformsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform_id = 'platform_id_example'; // string

try {
    $result = $apiInstance->runPlatformMigrations($platform_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PlatformsApi->runPlatformMigrations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform_id** | **string**|  | |

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
