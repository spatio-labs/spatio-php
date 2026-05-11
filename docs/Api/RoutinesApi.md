# SpatioClient\RoutinesApi

Saved scheduled-agent templates (routines) and their execution runs.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**claimRoutineRun()**](RoutinesApi.md#claimRoutineRun) | **POST** /v1/routines/runs/{id}/claim | Worker claims a queued run. |
| [**completeRoutineRun()**](RoutinesApi.md#completeRoutineRun) | **POST** /v1/routines/runs/{id}/complete | Worker marks a run complete. |
| [**createRoutine()**](RoutinesApi.md#createRoutine) | **POST** /v1/routines | Create a routine. |
| [**deleteRoutine()**](RoutinesApi.md#deleteRoutine) | **DELETE** /v1/routines/{id} | Delete a routine. |
| [**getRoutine()**](RoutinesApi.md#getRoutine) | **GET** /v1/routines/{id} | Fetch a routine. |
| [**listRoutineRuns()**](RoutinesApi.md#listRoutineRuns) | **GET** /v1/routines/{id}/runs | List runs for a routine. |
| [**listRoutines()**](RoutinesApi.md#listRoutines) | **GET** /v1/routines | List routines for the caller&#39;s workspace. |
| [**runRoutineNow()**](RoutinesApi.md#runRoutineNow) | **POST** /v1/routines/{id}/run-now | Trigger an ad-hoc run. |
| [**updateRoutine()**](RoutinesApi.md#updateRoutine) | **PATCH** /v1/routines/{id} | Update a routine. |
| [**updateRoutineRunProgress()**](RoutinesApi.md#updateRoutineRunProgress) | **POST** /v1/routines/runs/{id}/progress | Worker reports progress. |


## `claimRoutineRun()`

```php
claimRoutineRun($id): \SpatioClient\Model\RoutineRun
```

Worker claims a queued run.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->claimRoutineRun($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->claimRoutineRun: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\RoutineRun**](../Model/RoutineRun.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `completeRoutineRun()`

```php
completeRoutineRun($id, $routine_run_complete_request): \SpatioClient\Model\RoutineRun
```

Worker marks a run complete.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$routine_run_complete_request = new \SpatioClient\Model\RoutineRunCompleteRequest(); // \SpatioClient\Model\RoutineRunCompleteRequest

try {
    $result = $apiInstance->completeRoutineRun($id, $routine_run_complete_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->completeRoutineRun: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **routine_run_complete_request** | [**\SpatioClient\Model\RoutineRunCompleteRequest**](../Model/RoutineRunCompleteRequest.md)|  | |

### Return type

[**\SpatioClient\Model\RoutineRun**](../Model/RoutineRun.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createRoutine()`

```php
createRoutine($create_routine_request): \SpatioClient\Model\Routine
```

Create a routine.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_routine_request = new \SpatioClient\Model\CreateRoutineRequest(); // \SpatioClient\Model\CreateRoutineRequest

try {
    $result = $apiInstance->createRoutine($create_routine_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->createRoutine: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_routine_request** | [**\SpatioClient\Model\CreateRoutineRequest**](../Model/CreateRoutineRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Routine**](../Model/Routine.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteRoutine()`

```php
deleteRoutine($id)
```

Delete a routine.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteRoutine($id);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->deleteRoutine: ', $e->getMessage(), PHP_EOL;
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

## `getRoutine()`

```php
getRoutine($id): \SpatioClient\Model\Routine
```

Fetch a routine.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getRoutine($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->getRoutine: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\Routine**](../Model/Routine.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRoutineRuns()`

```php
listRoutineRuns($id): \SpatioClient\Model\RoutineRunListResponse
```

List runs for a routine.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->listRoutineRuns($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->listRoutineRuns: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\RoutineRunListResponse**](../Model/RoutineRunListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRoutines()`

```php
listRoutines($workspace_id, $status): \SpatioClient\Model\RoutineListResponse
```

List routines for the caller's workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string
$status = 'status_example'; // string

try {
    $result = $apiInstance->listRoutines($workspace_id, $status);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->listRoutines: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | [optional] |
| **status** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\RoutineListResponse**](../Model/RoutineListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `runRoutineNow()`

```php
runRoutineNow($id): \SpatioClient\Model\RoutineRun
```

Trigger an ad-hoc run.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->runRoutineNow($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->runRoutineNow: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\RoutineRun**](../Model/RoutineRun.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateRoutine()`

```php
updateRoutine($id, $update_routine_request): \SpatioClient\Model\Routine
```

Update a routine.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_routine_request = new \SpatioClient\Model\UpdateRoutineRequest(); // \SpatioClient\Model\UpdateRoutineRequest

try {
    $result = $apiInstance->updateRoutine($id, $update_routine_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->updateRoutine: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_routine_request** | [**\SpatioClient\Model\UpdateRoutineRequest**](../Model/UpdateRoutineRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Routine**](../Model/Routine.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateRoutineRunProgress()`

```php
updateRoutineRunProgress($id, $routine_run_progress_request): \SpatioClient\Model\RoutineRun
```

Worker reports progress.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RoutinesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$routine_run_progress_request = new \SpatioClient\Model\RoutineRunProgressRequest(); // \SpatioClient\Model\RoutineRunProgressRequest

try {
    $result = $apiInstance->updateRoutineRunProgress($id, $routine_run_progress_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RoutinesApi->updateRoutineRunProgress: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **routine_run_progress_request** | [**\SpatioClient\Model\RoutineRunProgressRequest**](../Model/RoutineRunProgressRequest.md)|  | |

### Return type

[**\SpatioClient\Model\RoutineRun**](../Model/RoutineRun.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
