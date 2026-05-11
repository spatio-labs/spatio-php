# SpatioClient\RecordsApi

Org-scoped record types + records (lightweight CRM-style entities).

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createRecord()**](RecordsApi.md#createRecord) | **POST** /v1/records | Create a record. |
| [**createRecordType()**](RecordsApi.md#createRecordType) | **POST** /v1/records/types | Create a record type (org-scoped). |
| [**deleteRecord()**](RecordsApi.md#deleteRecord) | **DELETE** /v1/records/{id} | Delete a record. |
| [**getRecord()**](RecordsApi.md#getRecord) | **GET** /v1/records/{id} | Fetch a record. |
| [**listRecordTypes()**](RecordsApi.md#listRecordTypes) | **GET** /v1/records/types | List record types for an organization. |
| [**listRecords()**](RecordsApi.md#listRecords) | **GET** /v1/records | List records for an organization. &#x60;organization_id&#x60; query param is required (handler returns 400 otherwise). |
| [**updateRecord()**](RecordsApi.md#updateRecord) | **PATCH** /v1/records/{id} | Update a record. |
| [**updateRecordType()**](RecordsApi.md#updateRecordType) | **PATCH** /v1/records/types/{id} | Update a record type. |


## `createRecord()`

```php
createRecord($create_record_request): \SpatioClient\Model\Record
```

Create a record.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecordsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_record_request = new \SpatioClient\Model\CreateRecordRequest(); // \SpatioClient\Model\CreateRecordRequest

try {
    $result = $apiInstance->createRecord($create_record_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecordsApi->createRecord: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_record_request** | [**\SpatioClient\Model\CreateRecordRequest**](../Model/CreateRecordRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Record**](../Model/Record.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createRecordType()`

```php
createRecordType($create_record_type_request): \SpatioClient\Model\RecordType
```

Create a record type (org-scoped).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecordsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_record_type_request = new \SpatioClient\Model\CreateRecordTypeRequest(); // \SpatioClient\Model\CreateRecordTypeRequest

try {
    $result = $apiInstance->createRecordType($create_record_type_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecordsApi->createRecordType: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_record_type_request** | [**\SpatioClient\Model\CreateRecordTypeRequest**](../Model/CreateRecordTypeRequest.md)|  | |

### Return type

[**\SpatioClient\Model\RecordType**](../Model/RecordType.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteRecord()`

```php
deleteRecord($id)
```

Delete a record.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecordsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteRecord($id);
} catch (Exception $e) {
    echo 'Exception when calling RecordsApi->deleteRecord: ', $e->getMessage(), PHP_EOL;
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

## `getRecord()`

```php
getRecord($id): \SpatioClient\Model\Record
```

Fetch a record.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecordsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getRecord($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecordsApi->getRecord: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\Record**](../Model/Record.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRecordTypes()`

```php
listRecordTypes($organization_id): \SpatioClient\Model\RecordTypeListResponse
```

List record types for an organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecordsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$organization_id = 'organization_id_example'; // string

try {
    $result = $apiInstance->listRecordTypes($organization_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecordsApi->listRecordTypes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **organization_id** | **string**|  | |

### Return type

[**\SpatioClient\Model\RecordTypeListResponse**](../Model/RecordTypeListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRecords()`

```php
listRecords($organization_id, $record_type_id, $limit): \SpatioClient\Model\RecordListResponse
```

List records for an organization. `organization_id` query param is required (handler returns 400 otherwise).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecordsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$organization_id = 'organization_id_example'; // string
$record_type_id = 'record_type_id_example'; // string
$limit = 56; // int

try {
    $result = $apiInstance->listRecords($organization_id, $record_type_id, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecordsApi->listRecords: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **organization_id** | **string**|  | |
| **record_type_id** | **string**|  | [optional] |
| **limit** | **int**|  | [optional] |

### Return type

[**\SpatioClient\Model\RecordListResponse**](../Model/RecordListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateRecord()`

```php
updateRecord($id, $update_record_request): \SpatioClient\Model\Record
```

Update a record.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecordsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_record_request = new \SpatioClient\Model\UpdateRecordRequest(); // \SpatioClient\Model\UpdateRecordRequest

try {
    $result = $apiInstance->updateRecord($id, $update_record_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecordsApi->updateRecord: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_record_request** | [**\SpatioClient\Model\UpdateRecordRequest**](../Model/UpdateRecordRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Record**](../Model/Record.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateRecordType()`

```php
updateRecordType($id, $update_record_type_request): \SpatioClient\Model\RecordType
```

Update a record type.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecordsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_record_type_request = new \SpatioClient\Model\UpdateRecordTypeRequest(); // \SpatioClient\Model\UpdateRecordTypeRequest

try {
    $result = $apiInstance->updateRecordType($id, $update_record_type_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecordsApi->updateRecordType: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_record_type_request** | [**\SpatioClient\Model\UpdateRecordTypeRequest**](../Model/UpdateRecordTypeRequest.md)|  | |

### Return type

[**\SpatioClient\Model\RecordType**](../Model/RecordType.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
