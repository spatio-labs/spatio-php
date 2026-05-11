# SpatioClient\ConnectionsApi

Native + OAuth integrations and the multi-account directory backing them.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**disconnectConnection()**](ConnectionsApi.md#disconnectConnection) | **POST** /v1/connections/disconnect | Disconnect a connected account. |
| [**installConnection()**](ConnectionsApi.md#installConnection) | **POST** /v1/connections/install | Begin an OAuth install for a connection. |
| [**listAccounts()**](ConnectionsApi.md#listAccounts) | **GET** /v1/accounts | List the caller&#39;s multi-provider accounts. |
| [**listConnectionIntegrations()**](ConnectionsApi.md#listConnectionIntegrations) | **GET** /v1/connections/integrations | List supported integrations + their connection state. Legacy path; &#x60;/v1/connections/list&#x60; is the preferred alias. |
| [**listConnections()**](ConnectionsApi.md#listConnections) | **GET** /v1/connections/list | List supported integrations + their connection state. |
| [**listUserConnections()**](ConnectionsApi.md#listUserConnections) | **GET** /v1/connections/user | List the caller&#39;s connected accounts. |
| [**refreshConnection()**](ConnectionsApi.md#refreshConnection) | **POST** /v1/connections/refresh | Force a refresh of a connection&#39;s OAuth tokens. |
| [**removeAccount()**](ConnectionsApi.md#removeAccount) | **DELETE** /v1/accounts/{accountId} | Remove an account. |
| [**resolveAccount()**](ConnectionsApi.md#resolveAccount) | **GET** /v1/accounts/resolve | Resolve an account by provider/identifier. |
| [**syncAccount()**](ConnectionsApi.md#syncAccount) | **POST** /v1/accounts/{accountId}/sync | Force a sync against the upstream provider. |
| [**updateAccount()**](ConnectionsApi.md#updateAccount) | **PATCH** /v1/accounts/{accountId} | Update account metadata (label, etc.). |


## `disconnectConnection()`

```php
disconnectConnection($disconnect_connection_request): array<string,mixed>
```

Disconnect a connected account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$disconnect_connection_request = new \SpatioClient\Model\DisconnectConnectionRequest(); // \SpatioClient\Model\DisconnectConnectionRequest

try {
    $result = $apiInstance->disconnectConnection($disconnect_connection_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->disconnectConnection: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **disconnect_connection_request** | [**\SpatioClient\Model\DisconnectConnectionRequest**](../Model/DisconnectConnectionRequest.md)|  | |

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

## `installConnection()`

```php
installConnection($install_connection_request): array<string,mixed>
```

Begin an OAuth install for a connection.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$install_connection_request = new \SpatioClient\Model\InstallConnectionRequest(); // \SpatioClient\Model\InstallConnectionRequest

try {
    $result = $apiInstance->installConnection($install_connection_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->installConnection: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **install_connection_request** | [**\SpatioClient\Model\InstallConnectionRequest**](../Model/InstallConnectionRequest.md)|  | |

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

## `listAccounts()`

```php
listAccounts(): \SpatioClient\Model\AccountListResponse
```

List the caller's multi-provider accounts.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAccounts();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->listAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\AccountListResponse**](../Model/AccountListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listConnectionIntegrations()`

```php
listConnectionIntegrations(): \SpatioClient\Model\ConnectionListResponse
```

List supported integrations + their connection state. Legacy path; `/v1/connections/list` is the preferred alias.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listConnectionIntegrations();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->listConnectionIntegrations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\ConnectionListResponse**](../Model/ConnectionListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listConnections()`

```php
listConnections(): \SpatioClient\Model\ConnectionListResponse
```

List supported integrations + their connection state.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listConnections();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->listConnections: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\ConnectionListResponse**](../Model/ConnectionListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listUserConnections()`

```php
listUserConnections(): \SpatioClient\Model\ConnectionAccountListResponse
```

List the caller's connected accounts.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listUserConnections();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->listUserConnections: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\ConnectionAccountListResponse**](../Model/ConnectionAccountListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `refreshConnection()`

```php
refreshConnection($refresh_connection_request): array<string,mixed>
```

Force a refresh of a connection's OAuth tokens.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$refresh_connection_request = new \SpatioClient\Model\RefreshConnectionRequest(); // \SpatioClient\Model\RefreshConnectionRequest

try {
    $result = $apiInstance->refreshConnection($refresh_connection_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->refreshConnection: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **refresh_connection_request** | [**\SpatioClient\Model\RefreshConnectionRequest**](../Model/RefreshConnectionRequest.md)|  | |

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

## `removeAccount()`

```php
removeAccount($account_id)
```

Remove an account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_id = 'account_id_example'; // string

try {
    $apiInstance->removeAccount($account_id);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->removeAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**|  | |

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

## `resolveAccount()`

```php
resolveAccount($provider, $email): array<string,mixed>
```

Resolve an account by provider/identifier.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$provider = 'provider_example'; // string
$email = 'email_example'; // string

try {
    $result = $apiInstance->resolveAccount($provider, $email);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->resolveAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **provider** | **string**|  | [optional] |
| **email** | **string**|  | [optional] |

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

## `syncAccount()`

```php
syncAccount($account_id): array<string,mixed>
```

Force a sync against the upstream provider.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->syncAccount($account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->syncAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**|  | |

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

## `updateAccount()`

```php
updateAccount($account_id, $update_account_request): array<string,mixed>
```

Update account metadata (label, etc.).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConnectionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_id = 'account_id_example'; // string
$update_account_request = new \SpatioClient\Model\UpdateAccountRequest(); // \SpatioClient\Model\UpdateAccountRequest

try {
    $result = $apiInstance->updateAccount($account_id, $update_account_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConnectionsApi->updateAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**|  | |
| **update_account_request** | [**\SpatioClient\Model\UpdateAccountRequest**](../Model/UpdateAccountRequest.md)|  | |

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
