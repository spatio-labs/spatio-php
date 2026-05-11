# SpatioClient\SearchApi

Cross-platform federated full-text search. Fans out to every per-platform search method in parallel.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**federatedSearch()**](SearchApi.md#federatedSearch) | **POST** /v1/search | Cross-platform federated search. |


## `federatedSearch()`

```php
federatedSearch($federated_search_request): \SpatioClient\Model\FederatedSearch200Response
```

Cross-platform federated search.

Fans out to every platform's per-platform search method in parallel, merges + dedupes results, and returns them in a relevance-then-recency ranking with per-platform cursors for pagination.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\SearchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$federated_search_request = new \SpatioClient\Model\FederatedSearchRequest(); // \SpatioClient\Model\FederatedSearchRequest

try {
    $result = $apiInstance->federatedSearch($federated_search_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SearchApi->federatedSearch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **federated_search_request** | [**\SpatioClient\Model\FederatedSearchRequest**](../Model/FederatedSearchRequest.md)|  | |

### Return type

[**\SpatioClient\Model\FederatedSearch200Response**](../Model/FederatedSearch200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
