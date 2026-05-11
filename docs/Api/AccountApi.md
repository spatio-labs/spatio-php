# SpatioClient\AccountApi

Account-level endpoints — billing tier, quotas, today&#39;s usage, free-trial agent-task gating, and security (sign-in methods, password change, active sessions).

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**changePassword()**](AccountApi.md#changePassword) | **POST** /v1/account/security/password | Change or set the account password. |
| [**consumeAgentTask()**](AccountApi.md#consumeAgentTask) | **POST** /v1/account/usage/consume-agent-task | Atomic check + increment on the agent-task counter (one slot per turn). |
| [**getAccountPlan()**](AccountApi.md#getAccountPlan) | **GET** /v1/account/plan | The caller&#39;s subscription tier and status. |
| [**getAccountTier()**](AccountApi.md#getAccountTier) | **GET** /v1/account/tier | Capability + quota envelope for the caller&#39;s tier. |
| [**getAccountUsage()**](AccountApi.md#getAccountUsage) | **GET** /v1/account/usage | Today&#39;s usage counters across notes, sheets, slides, files, tasks, mail, API. |
| [**getAgentTaskUsage()**](AccountApi.md#getAgentTaskUsage) | **GET** /v1/account/usage/agent-tasks | Free-trial agent-task counter snapshot. Read-only; does NOT consume a slot. Use POST &#x60;/v1/account/usage/consume-agent-task&#x60; atomically per turn to gate a tool-using turn. |
| [**getSignInMethods()**](AccountApi.md#getSignInMethods) | **GET** /v1/account/security/sign-in-methods | List the linked sign-in methods (password + OAuth providers). |
| [**listConnectedApps()**](AccountApi.md#listConnectedApps) | **GET** /v1/account/connected-apps | List the OAuth clients the calling user has granted access to. |
| [**listSessions()**](AccountApi.md#listSessions) | **GET** /v1/account/security/sessions | List active sessions for the caller. |
| [**revokeConnectedApp()**](AccountApi.md#revokeConnectedApp) | **DELETE** /v1/account/connected-apps/{client_id} | Revoke a connected app and all of its active tokens. |
| [**revokeOtherSessions()**](AccountApi.md#revokeOtherSessions) | **POST** /v1/account/security/sessions/revoke-others | Revoke every session except the caller&#39;s current one. |
| [**revokeSession()**](AccountApi.md#revokeSession) | **DELETE** /v1/account/security/sessions/{id} | Revoke a specific session. |


## `changePassword()`

```php
changePassword($change_password_request)
```

Change or set the account password.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$change_password_request = new \SpatioClient\Model\ChangePasswordRequest(); // \SpatioClient\Model\ChangePasswordRequest

try {
    $apiInstance->changePassword($change_password_request);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->changePassword: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **change_password_request** | [**\SpatioClient\Model\ChangePasswordRequest**](../Model/ChangePasswordRequest.md)|  | |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `consumeAgentTask()`

```php
consumeAgentTask(): \SpatioClient\Model\ConsumeAgentTaskResponse
```

Atomic check + increment on the agent-task counter (one slot per turn).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->consumeAgentTask();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->consumeAgentTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\ConsumeAgentTaskResponse**](../Model/ConsumeAgentTaskResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAccountPlan()`

```php
getAccountPlan(): \SpatioClient\Model\AccountPlan
```

The caller's subscription tier and status.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getAccountPlan();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getAccountPlan: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\AccountPlan**](../Model/AccountPlan.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAccountTier()`

```php
getAccountTier(): \SpatioClient\Model\AccountTierDetails
```

Capability + quota envelope for the caller's tier.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getAccountTier();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getAccountTier: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\AccountTierDetails**](../Model/AccountTierDetails.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAccountUsage()`

```php
getAccountUsage(): \SpatioClient\Model\AccountUsage
```

Today's usage counters across notes, sheets, slides, files, tasks, mail, API.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getAccountUsage();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getAccountUsage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\AccountUsage**](../Model/AccountUsage.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAgentTaskUsage()`

```php
getAgentTaskUsage(): \SpatioClient\Model\AgentTaskUsage
```

Free-trial agent-task counter snapshot. Read-only; does NOT consume a slot. Use POST `/v1/account/usage/consume-agent-task` atomically per turn to gate a tool-using turn.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getAgentTaskUsage();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getAgentTaskUsage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\AgentTaskUsage**](../Model/AgentTaskUsage.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSignInMethods()`

```php
getSignInMethods(): \SpatioClient\Model\SignInMethods
```

List the linked sign-in methods (password + OAuth providers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getSignInMethods();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getSignInMethods: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\SignInMethods**](../Model/SignInMethods.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listConnectedApps()`

```php
listConnectedApps(): \SpatioClient\Model\ConnectedAppsListResponse
```

List the OAuth clients the calling user has granted access to.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listConnectedApps();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->listConnectedApps: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\ConnectedAppsListResponse**](../Model/ConnectedAppsListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSessions()`

```php
listSessions(): \SpatioClient\Model\SessionListResponse
```

List active sessions for the caller.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listSessions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->listSessions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\SessionListResponse**](../Model/SessionListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokeConnectedApp()`

```php
revokeConnectedApp($client_id)
```

Revoke a connected app and all of its active tokens.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$client_id = 'client_id_example'; // string

try {
    $apiInstance->revokeConnectedApp($client_id);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->revokeConnectedApp: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **client_id** | **string**|  | |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokeOtherSessions()`

```php
revokeOtherSessions(): \SpatioClient\Model\RevokeOtherSessionsResponse
```

Revoke every session except the caller's current one.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->revokeOtherSessions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->revokeOtherSessions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\RevokeOtherSessionsResponse**](../Model/RevokeOtherSessionsResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokeSession()`

```php
revokeSession($id)
```

Revoke a specific session.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->revokeSession($id);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->revokeSession: ', $e->getMessage(), PHP_EOL;
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
