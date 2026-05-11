# SpatioClient\RecommendationsApi

Agent-authored proposals that surface on the home feed.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteRecommendation()**](RecommendationsApi.md#deleteRecommendation) | **DELETE** /v1/recommendations/{id} | Delete a recommendation (hard delete; status-update is preferred). |
| [**getRecommendation()**](RecommendationsApi.md#getRecommendation) | **GET** /v1/recommendations/{id} | Fetch one recommendation. |
| [**listRecommendations()**](RecommendationsApi.md#listRecommendations) | **GET** /v1/recommendations | List recommendations for a workspace. |
| [**proposeRecommendation()**](RecommendationsApi.md#proposeRecommendation) | **POST** /v1/recommendations | Agent-side propose endpoint (the &#x60;spatio_recommendations propose&#x60; MCP tool calls this). |
| [**updateRecommendationStatus()**](RecommendationsApi.md#updateRecommendationStatus) | **PATCH** /v1/recommendations/{id}/status | Accept or dismiss a recommendation. |


## `deleteRecommendation()`

```php
deleteRecommendation($id)
```

Delete a recommendation (hard delete; status-update is preferred).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteRecommendation($id);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->deleteRecommendation: ', $e->getMessage(), PHP_EOL;
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

## `getRecommendation()`

```php
getRecommendation($id): \SpatioClient\Model\Recommendation
```

Fetch one recommendation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getRecommendation($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->getRecommendation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\Recommendation**](../Model/Recommendation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRecommendations()`

```php
listRecommendations($workspace_id, $status, $limit): \SpatioClient\Model\RecommendationListResponse
```

List recommendations for a workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string
$status = 'status_example'; // string
$limit = 56; // int

try {
    $result = $apiInstance->listRecommendations($workspace_id, $status, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->listRecommendations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | [optional] |
| **status** | **string**|  | [optional] |
| **limit** | **int**|  | [optional] |

### Return type

[**\SpatioClient\Model\RecommendationListResponse**](../Model/RecommendationListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `proposeRecommendation()`

```php
proposeRecommendation($propose_recommendation_request): \SpatioClient\Model\Recommendation
```

Agent-side propose endpoint (the `spatio_recommendations propose` MCP tool calls this).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$propose_recommendation_request = new \SpatioClient\Model\ProposeRecommendationRequest(); // \SpatioClient\Model\ProposeRecommendationRequest

try {
    $result = $apiInstance->proposeRecommendation($propose_recommendation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->proposeRecommendation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **propose_recommendation_request** | [**\SpatioClient\Model\ProposeRecommendationRequest**](../Model/ProposeRecommendationRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Recommendation**](../Model/Recommendation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateRecommendationStatus()`

```php
updateRecommendationStatus($id, $update_recommendation_status_request): \SpatioClient\Model\Recommendation
```

Accept or dismiss a recommendation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_recommendation_status_request = new \SpatioClient\Model\UpdateRecommendationStatusRequest(); // \SpatioClient\Model\UpdateRecommendationStatusRequest

try {
    $result = $apiInstance->updateRecommendationStatus($id, $update_recommendation_status_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->updateRecommendationStatus: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_recommendation_status_request** | [**\SpatioClient\Model\UpdateRecommendationStatusRequest**](../Model/UpdateRecommendationStatusRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Recommendation**](../Model/Recommendation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
