# SpatioClient\SheetsApi

Spreadsheets, rows, and cells.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createSheet()**](SheetsApi.md#createSheet) | **POST** /v1/sheets | Create a sheet. |
| [**createSheetRow()**](SheetsApi.md#createSheetRow) | **POST** /v1/sheets/{id}/rows | Insert a row. |
| [**deleteSheet()**](SheetsApi.md#deleteSheet) | **DELETE** /v1/sheets/{id} | Delete a sheet. |
| [**deleteSheetRow()**](SheetsApi.md#deleteSheetRow) | **DELETE** /v1/sheets/{id}/rows/{rowIndex} | Delete a row. |
| [**getSheet()**](SheetsApi.md#getSheet) | **GET** /v1/sheets/{id} | Fetch one sheet. |
| [**listSheetRows()**](SheetsApi.md#listSheetRows) | **GET** /v1/sheets/{id}/rows | List rows in a sheet. |
| [**listSheets()**](SheetsApi.md#listSheets) | **GET** /v1/sheets | List sheets across connected accounts. |
| [**updateSheet()**](SheetsApi.md#updateSheet) | **PATCH** /v1/sheets/{id} | Update a sheet (partial). |
| [**updateSheetCell()**](SheetsApi.md#updateSheetCell) | **PATCH** /v1/sheets/{id}/rows/{rowIndex}/cells/{column} | Update a single cell. |
| [**updateSheetRow()**](SheetsApi.md#updateSheetRow) | **PATCH** /v1/sheets/{id}/rows/{rowIndex} | Update a row (sparse). |


## `createSheet()`

```php
createSheet($create_sheet_request, $account_id, $provider, $x_workspace_id): \SpatioClient\Model\Sheet
```

Create a sheet.

Creates a new sheet under the target account. Target resolution mirrors `POST /v1/notes`: body `accountId` → `?accountId=` → body `provider` → `?provider=` → caller's single connected account (errors with `ambiguous_account` if more than one is connected and no selector is supplied).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_sheet_request = new \SpatioClient\Model\CreateSheetRequest(); // \SpatioClient\Model\CreateSheetRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$provider = 'provider_example'; // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createSheet($create_sheet_request, $account_id, $provider, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->createSheet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_sheet_request** | [**\SpatioClient\Model\CreateSheetRequest**](../Model/CreateSheetRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **provider** | **string**| Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Sheet**](../Model/Sheet.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createSheetRow()`

```php
createSheetRow($id, $create_row_request, $account_id, $x_workspace_id): \SpatioClient\Model\Row
```

Insert a row.

Inserts a row at `index` (zero-based) or appends to the end when `index` is omitted.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Sheet id.
$create_row_request = new \SpatioClient\Model\CreateRowRequest(); // \SpatioClient\Model\CreateRowRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createSheetRow($id, $create_row_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->createSheetRow: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Sheet id. | |
| **create_row_request** | [**\SpatioClient\Model\CreateRowRequest**](../Model/CreateRowRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Row**](../Model/Row.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteSheet()`

```php
deleteSheet($id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a sheet.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Sheet id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteSheet($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->deleteSheet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Sheet id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\SuccessFlag**](../Model/SuccessFlag.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteSheetRow()`

```php
deleteSheetRow($id, $row_index, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a row.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Sheet id.
$row_index = 56; // int | Zero-based row index.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteSheetRow($id, $row_index, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->deleteSheetRow: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Sheet id. | |
| **row_index** | **int**| Zero-based row index. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\SuccessFlag**](../Model/SuccessFlag.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSheet()`

```php
getSheet($id, $account_id, $x_workspace_id): \SpatioClient\Model\Sheet
```

Fetch one sheet.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Sheet id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getSheet($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->getSheet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Sheet id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Sheet**](../Model/Sheet.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSheetRows()`

```php
listSheetRows($id, $account_id, $x_workspace_id, $limit, $offset): \SpatioClient\Model\RowList
```

List rows in a sheet.

Single-account row list. Unlike `GET /v1/sheets`, row listing always targets the one account that owns the sheet, so the response is a plain `{ rows, total }` rather than a fan-out envelope.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Sheet id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$limit = 100; // int
$offset = 0; // int

try {
    $result = $apiInstance->listSheetRows($id, $account_id, $x_workspace_id, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->listSheetRows: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Sheet id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **limit** | **int**|  | [optional] [default to 100] |
| **offset** | **int**|  | [optional] [default to 0] |

### Return type

[**\SpatioClient\Model\RowList**](../Model/RowList.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSheets()`

```php
listSheets($account_id, $provider, $x_workspace_id, $limit, $offset): \SpatioClient\Model\SheetListEnvelope
```

List sheets across connected accounts.

Fan-out list. Returns every sheet visible to the caller across every connected sheets provider, paginated by `limit` / `offset`. Pass `?accountId=` or `?provider=` to scope to a single source.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$provider = 'provider_example'; // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$limit = 50; // int
$offset = 0; // int

try {
    $result = $apiInstance->listSheets($account_id, $provider, $x_workspace_id, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->listSheets: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **provider** | **string**| Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **limit** | **int**|  | [optional] [default to 50] |
| **offset** | **int**|  | [optional] [default to 0] |

### Return type

[**\SpatioClient\Model\SheetListEnvelope**](../Model/SheetListEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateSheet()`

```php
updateSheet($id, $update_sheet_request, $account_id, $x_workspace_id): \SpatioClient\Model\Sheet
```

Update a sheet (partial).

Partial update of sheet metadata. The renderer also calls this via `PUT /v1/sheets/{id}` for autosave parity; both verbs invoke the same handler. Per-cell and per-row mutations live on their dedicated endpoints, not here.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Sheet id.
$update_sheet_request = new \SpatioClient\Model\UpdateSheetRequest(); // \SpatioClient\Model\UpdateSheetRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateSheet($id, $update_sheet_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->updateSheet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Sheet id. | |
| **update_sheet_request** | [**\SpatioClient\Model\UpdateSheetRequest**](../Model/UpdateSheetRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Sheet**](../Model/Sheet.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateSheetCell()`

```php
updateSheetCell($id, $row_index, $column, $update_cell_request, $account_id, $x_workspace_id): \SpatioClient\Model\Cell
```

Update a single cell.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Sheet id.
$row_index = 56; // int | Zero-based row index.
$column = 'column_example'; // string | Column identifier. Provider-specific — usually a letter (`A`, `AB`) for spreadsheet providers or a column key string for structured providers.
$update_cell_request = new \SpatioClient\Model\UpdateCellRequest(); // \SpatioClient\Model\UpdateCellRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateSheetCell($id, $row_index, $column, $update_cell_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->updateSheetCell: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Sheet id. | |
| **row_index** | **int**| Zero-based row index. | |
| **column** | **string**| Column identifier. Provider-specific — usually a letter (&#x60;A&#x60;, &#x60;AB&#x60;) for spreadsheet providers or a column key string for structured providers. | |
| **update_cell_request** | [**\SpatioClient\Model\UpdateCellRequest**](../Model/UpdateCellRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Cell**](../Model/Cell.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateSheetRow()`

```php
updateSheetRow($id, $row_index, $update_row_request, $account_id, $x_workspace_id): \SpatioClient\Model\Row
```

Update a row (sparse).

Sparse update — keys present in `cells` overwrite that column; keys absent are preserved.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SheetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Sheet id.
$row_index = 56; // int | Zero-based row index.
$update_row_request = new \SpatioClient\Model\UpdateRowRequest(); // \SpatioClient\Model\UpdateRowRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateSheetRow($id, $row_index, $update_row_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SheetsApi->updateSheetRow: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Sheet id. | |
| **row_index** | **int**| Zero-based row index. | |
| **update_row_request** | [**\SpatioClient\Model\UpdateRowRequest**](../Model/UpdateRowRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Row**](../Model/Row.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
