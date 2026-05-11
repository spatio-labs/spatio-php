# SpatioClient\FoldersApi

Email folders (inbox-side organization).

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createEmailFolder()**](FoldersApi.md#createEmailFolder) | **POST** /v1/folders | Create an email folder. |
| [**deleteEmailFolder()**](FoldersApi.md#deleteEmailFolder) | **DELETE** /v1/folders/{id} | Delete an email folder. |
| [**listEmailFolders()**](FoldersApi.md#listEmailFolders) | **GET** /v1/folders | List the caller&#39;s email folders. |
| [**listFolderEmails()**](FoldersApi.md#listFolderEmails) | **GET** /v1/folders/{id}/emails | List emails inside a folder. |
| [**moveEmailsToFolder()**](FoldersApi.md#moveEmailsToFolder) | **POST** /v1/folders/{id}/emails | Move emails into a folder. |
| [**updateEmailFolder()**](FoldersApi.md#updateEmailFolder) | **PUT** /v1/folders/{id} | Update an email folder. |


## `createEmailFolder()`

```php
createEmailFolder($create_email_folder_request): \SpatioClient\Model\EmailFolder
```

Create an email folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\FoldersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_email_folder_request = new \SpatioClient\Model\CreateEmailFolderRequest(); // \SpatioClient\Model\CreateEmailFolderRequest

try {
    $result = $apiInstance->createEmailFolder($create_email_folder_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->createEmailFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_email_folder_request** | [**\SpatioClient\Model\CreateEmailFolderRequest**](../Model/CreateEmailFolderRequest.md)|  | |

### Return type

[**\SpatioClient\Model\EmailFolder**](../Model/EmailFolder.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteEmailFolder()`

```php
deleteEmailFolder($id)
```

Delete an email folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\FoldersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteEmailFolder($id);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->deleteEmailFolder: ', $e->getMessage(), PHP_EOL;
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

## `listEmailFolders()`

```php
listEmailFolders(): \SpatioClient\Model\EmailFolderListResponse
```

List the caller's email folders.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\FoldersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listEmailFolders();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->listEmailFolders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\EmailFolderListResponse**](../Model/EmailFolderListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listFolderEmails()`

```php
listFolderEmails($id): array<string,mixed>
```

List emails inside a folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\FoldersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->listFolderEmails($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->listFolderEmails: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

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

## `moveEmailsToFolder()`

```php
moveEmailsToFolder($id, $move_emails_request): array<string,mixed>
```

Move emails into a folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\FoldersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$move_emails_request = new \SpatioClient\Model\MoveEmailsRequest(); // \SpatioClient\Model\MoveEmailsRequest

try {
    $result = $apiInstance->moveEmailsToFolder($id, $move_emails_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->moveEmailsToFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **move_emails_request** | [**\SpatioClient\Model\MoveEmailsRequest**](../Model/MoveEmailsRequest.md)|  | |

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

## `updateEmailFolder()`

```php
updateEmailFolder($id, $update_email_folder_request): \SpatioClient\Model\EmailFolder
```

Update an email folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\FoldersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_email_folder_request = new \SpatioClient\Model\UpdateEmailFolderRequest(); // \SpatioClient\Model\UpdateEmailFolderRequest

try {
    $result = $apiInstance->updateEmailFolder($id, $update_email_folder_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->updateEmailFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_email_folder_request** | [**\SpatioClient\Model\UpdateEmailFolderRequest**](../Model/UpdateEmailFolderRequest.md)|  | |

### Return type

[**\SpatioClient\Model\EmailFolder**](../Model/EmailFolder.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
