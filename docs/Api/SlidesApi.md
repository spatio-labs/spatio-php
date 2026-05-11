# SpatioClient\SlidesApi

Presentations, slides, canvas elements, sharing, and PDF export.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createPresentation()**](SlidesApi.md#createPresentation) | **POST** /v1/slides | Create a presentation. |
| [**createSlide()**](SlidesApi.md#createSlide) | **POST** /v1/slides/{id}/slides | Insert a slide. |
| [**createSlideElement()**](SlidesApi.md#createSlideElement) | **POST** /v1/slides/{id}/slides/{slideId}/elements | Add a canvas element (text/shape/image) to a slide. |
| [**deletePresentation()**](SlidesApi.md#deletePresentation) | **DELETE** /v1/slides/{id} | Delete a presentation. |
| [**deleteSlide()**](SlidesApi.md#deleteSlide) | **DELETE** /v1/slides/{id}/slides/{slideId} | Delete a slide. |
| [**deleteSlideElement()**](SlidesApi.md#deleteSlideElement) | **DELETE** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Delete a slide element. |
| [**disablePresentationShare()**](SlidesApi.md#disablePresentationShare) | **DELETE** /v1/slides/{id}/share | Disable public sharing. |
| [**enablePresentationShare()**](SlidesApi.md#enablePresentationShare) | **POST** /v1/slides/{id}/share | Enable (or update password on) public sharing. |
| [**exportPresentationPdf()**](SlidesApi.md#exportPresentationPdf) | **POST** /v1/slides/{id}/export/pdf | Render the presentation as a PDF. |
| [**exportPresentationPptx()**](SlidesApi.md#exportPresentationPptx) | **POST** /v1/slides/{id}/export/pptx | Render the presentation as a PowerPoint (.pptx) file. |
| [**getPresentation()**](SlidesApi.md#getPresentation) | **GET** /v1/slides/{id} | Fetch one presentation. |
| [**getPresentationShareSettings()**](SlidesApi.md#getPresentationShareSettings) | **GET** /v1/slides/{id}/share | Fetch share settings for a presentation. |
| [**getPublicPresentation()**](SlidesApi.md#getPublicPresentation) | **GET** /public/slides/{token} | Fetch a publicly shared presentation. |
| [**getSlide()**](SlidesApi.md#getSlide) | **GET** /v1/slides/{id}/slides/{slideId} | Fetch one slide. |
| [**getSlideElement()**](SlidesApi.md#getSlideElement) | **GET** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Fetch one slide element. |
| [**listPresentations()**](SlidesApi.md#listPresentations) | **GET** /v1/slides | List presentations across connected accounts. |
| [**listSlideElements()**](SlidesApi.md#listSlideElements) | **GET** /v1/slides/{id}/slides/{slideId}/elements | List the canvas elements on a slide. |
| [**listSlidesInPresentation()**](SlidesApi.md#listSlidesInPresentation) | **GET** /v1/slides/{id}/slides | List slides in a presentation. |
| [**rotatePresentationShareToken()**](SlidesApi.md#rotatePresentationShareToken) | **POST** /v1/slides/{id}/share/rotate | Rotate the share token, invalidating outstanding URLs. |
| [**updatePresentation()**](SlidesApi.md#updatePresentation) | **PATCH** /v1/slides/{id} | Update presentation metadata (partial). |
| [**updateSlide()**](SlidesApi.md#updateSlide) | **PATCH** /v1/slides/{id}/slides/{slideId} | Update a slide (partial). |
| [**updateSlideElement()**](SlidesApi.md#updateSlideElement) | **PATCH** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Update a slide element (partial). |


## `createPresentation()`

```php
createPresentation($create_presentation_request, $account_id, $provider, $x_workspace_id): \SpatioClient\Model\Presentation
```

Create a presentation.

Creates a new deck under the target account. Target resolution mirrors `POST /v1/notes` and `/v1/sheets`: body `accountId` → `?accountId=` → body `provider` → `?provider=` → caller's single connected account (errors with `ambiguous_account` otherwise). The new deck is auto-seeded with one blank slide so the renderer has something to display immediately.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_presentation_request = new \SpatioClient\Model\CreatePresentationRequest(); // \SpatioClient\Model\CreatePresentationRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$provider = 'provider_example'; // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createPresentation($create_presentation_request, $account_id, $provider, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->createPresentation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_presentation_request** | [**\SpatioClient\Model\CreatePresentationRequest**](../Model/CreatePresentationRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **provider** | **string**| Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Presentation**](../Model/Presentation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createSlide()`

```php
createSlide($id, $create_slide_request, $account_id, $x_workspace_id): \SpatioClient\Model\Slide
```

Insert a slide.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$create_slide_request = new \SpatioClient\Model\CreateSlideRequest(); // \SpatioClient\Model\CreateSlideRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createSlide($id, $create_slide_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->createSlide: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **create_slide_request** | [**\SpatioClient\Model\CreateSlideRequest**](../Model/CreateSlideRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Slide**](../Model/Slide.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createSlideElement()`

```php
createSlideElement($id, $slide_id, $create_slide_element_request, $account_id, $x_workspace_id): \SpatioClient\Model\SlideElement
```

Add a canvas element (text/shape/image) to a slide.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$slide_id = 'slide_id_example'; // string | Slide id within the presentation.
$create_slide_element_request = new \SpatioClient\Model\CreateSlideElementRequest(); // \SpatioClient\Model\CreateSlideElementRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createSlideElement($id, $slide_id, $create_slide_element_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->createSlideElement: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **slide_id** | **string**| Slide id within the presentation. | |
| **create_slide_element_request** | [**\SpatioClient\Model\CreateSlideElementRequest**](../Model/CreateSlideElementRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\SlideElement**](../Model/SlideElement.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deletePresentation()`

```php
deletePresentation($id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a presentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deletePresentation($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->deletePresentation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
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

## `deleteSlide()`

```php
deleteSlide($id, $slide_id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a slide.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$slide_id = 'slide_id_example'; // string | Slide id within the presentation.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteSlide($id, $slide_id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->deleteSlide: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **slide_id** | **string**| Slide id within the presentation. | |
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

## `deleteSlideElement()`

```php
deleteSlideElement($id, $slide_id, $element_id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a slide element.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$slide_id = 'slide_id_example'; // string | Slide id within the presentation.
$element_id = 'element_id_example'; // string | Slide-element id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteSlideElement($id, $slide_id, $element_id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->deleteSlideElement: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **slide_id** | **string**| Slide id within the presentation. | |
| **element_id** | **string**| Slide-element id. | |
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

## `disablePresentationShare()`

```php
disablePresentationShare($id, $account_id, $x_workspace_id)
```

Disable public sharing.

Owner-only. Subsequent public viewer requests 404.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $apiInstance->disablePresentationShare($id, $account_id, $x_workspace_id);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->disablePresentationShare: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

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

## `enablePresentationShare()`

```php
enablePresentationShare($id, $account_id, $x_workspace_id, $enable_share_request): \SpatioClient\Model\ShareSettings
```

Enable (or update password on) public sharing.

Owner-only. With `setPassword: false` (or empty body), flips the deck public without changing the password. With `setPassword: true`, applies `password` (empty clears).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$enable_share_request = new \SpatioClient\Model\EnableShareRequest(); // \SpatioClient\Model\EnableShareRequest

try {
    $result = $apiInstance->enablePresentationShare($id, $account_id, $x_workspace_id, $enable_share_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->enablePresentationShare: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **enable_share_request** | [**\SpatioClient\Model\EnableShareRequest**](../Model/EnableShareRequest.md)|  | [optional] |

### Return type

[**\SpatioClient\Model\ShareSettings**](../Model/ShareSettings.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `exportPresentationPdf()`

```php
exportPresentationPdf($id, $account_id, $x_workspace_id, $storage, $filename, $export_pdf_request): \SplFileObject
```

Render the presentation as a PDF.

Proxies to the Spatio export sidecar (Playwright). Two response modes selected via `?storage=`:    - `stream` (default) — response body is the PDF binary     (`application/pdf`).   - `r2` — uploads the rendered PDF to R2 storage and returns     a JSON envelope with a 24-hour signed URL.  Returns `503 Service Unavailable` when the export sidecar is not configured (dev fallback to the client-side exporter).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$storage = 'stream'; // string
$filename = 'filename_example'; // string | Sanitized base name for the downloaded PDF.
$export_pdf_request = new \SpatioClient\Model\ExportPDFRequest(); // \SpatioClient\Model\ExportPDFRequest

try {
    $result = $apiInstance->exportPresentationPdf($id, $account_id, $x_workspace_id, $storage, $filename, $export_pdf_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->exportPresentationPdf: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **storage** | **string**|  | [optional] [default to &#39;stream&#39;] |
| **filename** | **string**| Sanitized base name for the downloaded PDF. | [optional] |
| **export_pdf_request** | [**\SpatioClient\Model\ExportPDFRequest**](../Model/ExportPDFRequest.md)|  | [optional] |

### Return type

**\SplFileObject**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/pdf`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `exportPresentationPptx()`

```php
exportPresentationPptx($id, $account_id, $x_workspace_id, $storage, $filename, $export_pdf_request): \SplFileObject
```

Render the presentation as a PowerPoint (.pptx) file.

Proxies to the Spatio export sidecar (Playwright + pptxgenjs). Each slide is screenshotted at 2× device-pixel ratio and wrapped into a PowerPoint .pptx as a full-bleed image. Visual fidelity is preserved exactly — what renders in Spatio renders identically in PowerPoint, Keynote, Google Slides — at the cost of in-PowerPoint editability of slide content. Users edit slide content back in Spatio (the source of truth), not inside PowerPoint.  Two response modes selected via `?storage=`:    - `stream` (default) — response body is the PPTX binary     (`application/vnd.openxmlformats-officedocument.presentationml.presentation`).   - `r2` — uploads the rendered PPTX to R2 storage and returns     a JSON envelope with a 24-hour signed URL.  Returns `503 Service Unavailable` when the export sidecar is not configured.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$storage = 'stream'; // string
$filename = 'filename_example'; // string | Sanitized base name for the downloaded PPTX.
$export_pdf_request = new \SpatioClient\Model\ExportPDFRequest(); // \SpatioClient\Model\ExportPDFRequest

try {
    $result = $apiInstance->exportPresentationPptx($id, $account_id, $x_workspace_id, $storage, $filename, $export_pdf_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->exportPresentationPptx: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **storage** | **string**|  | [optional] [default to &#39;stream&#39;] |
| **filename** | **string**| Sanitized base name for the downloaded PPTX. | [optional] |
| **export_pdf_request** | [**\SpatioClient\Model\ExportPDFRequest**](../Model/ExportPDFRequest.md)|  | [optional] |

### Return type

**\SplFileObject**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/vnd.openxmlformats-officedocument.presentationml.presentation`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPresentation()`

```php
getPresentation($id, $account_id, $x_workspace_id): \SpatioClient\Model\Presentation
```

Fetch one presentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getPresentation($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->getPresentation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Presentation**](../Model/Presentation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPresentationShareSettings()`

```php
getPresentationShareSettings($id, $account_id, $x_workspace_id): \SpatioClient\Model\ShareSettings
```

Fetch share settings for a presentation.

Owner-only. Mirror of `GET /v1/notes/{id}/share` — same shape, same fields. Returns the current public-share configuration, including the share token and computed public viewer URL when the deck is currently public.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getPresentationShareSettings($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->getPresentationShareSettings: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\ShareSettings**](../Model/ShareSettings.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPublicPresentation()`

```php
getPublicPresentation($token, $password): array<string,mixed>
```

Fetch a publicly shared presentation.

Unauthenticated. Mirror of `GET /public/notes/{token}`. The share token is the credential. For password-protected decks the password is supplied via `?password=`; the response distinguishes \"no password supplied\" from \"wrong password\" so the viewer can render the right prompt. Unknown tokens and disabled-share decks both return `404` to prevent enumeration.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$token = 'token_example'; // string | Opaque public-share token.
$password = 'password_example'; // string | Optional viewer password.

try {
    $result = $apiInstance->getPublicPresentation($token, $password);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->getPublicPresentation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token** | **string**| Opaque public-share token. | |
| **password** | **string**| Optional viewer password. | [optional] |

### Return type

**array<string,mixed>**

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSlide()`

```php
getSlide($id, $slide_id, $account_id, $x_workspace_id): \SpatioClient\Model\Slide
```

Fetch one slide.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$slide_id = 'slide_id_example'; // string | Slide id within the presentation.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getSlide($id, $slide_id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->getSlide: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **slide_id** | **string**| Slide id within the presentation. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Slide**](../Model/Slide.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSlideElement()`

```php
getSlideElement($id, $slide_id, $element_id, $account_id, $x_workspace_id): \SpatioClient\Model\SlideElement
```

Fetch one slide element.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$slide_id = 'slide_id_example'; // string | Slide id within the presentation.
$element_id = 'element_id_example'; // string | Slide-element id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getSlideElement($id, $slide_id, $element_id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->getSlideElement: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **slide_id** | **string**| Slide id within the presentation. | |
| **element_id** | **string**| Slide-element id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\SlideElement**](../Model/SlideElement.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listPresentations()`

```php
listPresentations($account_id, $provider, $x_workspace_id, $limit, $offset): \SpatioClient\Model\PresentationListEnvelope
```

List presentations across connected accounts.

Fan-out list. Returns every presentation visible to the caller across every connected slides provider. Pass `?accountId=` or `?provider=` to scope to a single source.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
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
    $result = $apiInstance->listPresentations($account_id, $provider, $x_workspace_id, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->listPresentations: ', $e->getMessage(), PHP_EOL;
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

[**\SpatioClient\Model\PresentationListEnvelope**](../Model/PresentationListEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSlideElements()`

```php
listSlideElements($id, $slide_id, $account_id, $x_workspace_id): \SpatioClient\Model\SlideElementList
```

List the canvas elements on a slide.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$slide_id = 'slide_id_example'; // string | Slide id within the presentation.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->listSlideElements($id, $slide_id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->listSlideElements: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **slide_id** | **string**| Slide id within the presentation. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\SlideElementList**](../Model/SlideElementList.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSlidesInPresentation()`

```php
listSlidesInPresentation($id, $account_id, $x_workspace_id): \SpatioClient\Model\SlideList
```

List slides in a presentation.

Single-account list. Returns slides in the order set by their `position` field.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->listSlidesInPresentation($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->listSlidesInPresentation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\SlideList**](../Model/SlideList.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `rotatePresentationShareToken()`

```php
rotatePresentationShareToken($id, $account_id, $x_workspace_id): \SpatioClient\Model\ShareSettings
```

Rotate the share token, invalidating outstanding URLs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->rotatePresentationShareToken($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->rotatePresentationShareToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\ShareSettings**](../Model/ShareSettings.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updatePresentation()`

```php
updatePresentation($id, $update_presentation_request, $account_id, $x_workspace_id): \SpatioClient\Model\Presentation
```

Update presentation metadata (partial).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$update_presentation_request = new \SpatioClient\Model\UpdatePresentationRequest(); // \SpatioClient\Model\UpdatePresentationRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updatePresentation($id, $update_presentation_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->updatePresentation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **update_presentation_request** | [**\SpatioClient\Model\UpdatePresentationRequest**](../Model/UpdatePresentationRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Presentation**](../Model/Presentation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateSlide()`

```php
updateSlide($id, $slide_id, $update_slide_request, $account_id, $x_workspace_id): \SpatioClient\Model\Slide
```

Update a slide (partial).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$slide_id = 'slide_id_example'; // string | Slide id within the presentation.
$update_slide_request = new \SpatioClient\Model\UpdateSlideRequest(); // \SpatioClient\Model\UpdateSlideRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateSlide($id, $slide_id, $update_slide_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->updateSlide: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **slide_id** | **string**| Slide id within the presentation. | |
| **update_slide_request** | [**\SpatioClient\Model\UpdateSlideRequest**](../Model/UpdateSlideRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Slide**](../Model/Slide.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateSlideElement()`

```php
updateSlideElement($id, $slide_id, $element_id, $update_slide_element_request, $account_id, $x_workspace_id): \SpatioClient\Model\SlideElement
```

Update a slide element (partial).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SlidesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Presentation id.
$slide_id = 'slide_id_example'; // string | Slide id within the presentation.
$element_id = 'element_id_example'; // string | Slide-element id.
$update_slide_element_request = new \SpatioClient\Model\UpdateSlideElementRequest(); // \SpatioClient\Model\UpdateSlideElementRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateSlideElement($id, $slide_id, $element_id, $update_slide_element_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SlidesApi->updateSlideElement: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Presentation id. | |
| **slide_id** | **string**| Slide id within the presentation. | |
| **element_id** | **string**| Slide-element id. | |
| **update_slide_element_request** | [**\SpatioClient\Model\UpdateSlideElementRequest**](../Model/UpdateSlideElementRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\SlideElement**](../Model/SlideElement.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
