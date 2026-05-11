# SpatioClient\RealtimeApi

WebSocket-adjacent REST endpoints (token exchange for the Yjs collaboration worker). The &#x60;/ws&#x60; hub itself is documented in &#x60;docs/realtime.md&#x60; because OpenAPI 3.0 cannot describe websockets natively.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**issueCollaborationToken()**](RealtimeApi.md#issueCollaborationToken) | **POST** /v1/realtime/collaboration-token | Exchange a bearer token for a short-lived Yjs collaboration JWT. |


## `issueCollaborationToken()`

```php
issueCollaborationToken($issue_collaboration_token_request): \SpatioClient\Model\IssueCollaborationToken200Response
```

Exchange a bearer token for a short-lived Yjs collaboration JWT.

The Yjs Cloudflare Worker that powers live document collaboration (`wss://realtime-collaboration.<account>.workers.dev`) only accepts platform-signed JWTs. Third-party clients holding an OAuth access token or PAT call this endpoint to mint a 5-minute collaboration JWT they can present to the worker.  The minted JWT inherits user + workspace identity from the presenting bearer token. Optionally scope it to a single room by supplying `room` in the request body.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RealtimeApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$issue_collaboration_token_request = new \SpatioClient\Model\IssueCollaborationTokenRequest(); // \SpatioClient\Model\IssueCollaborationTokenRequest

try {
    $result = $apiInstance->issueCollaborationToken($issue_collaboration_token_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RealtimeApi->issueCollaborationToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **issue_collaboration_token_request** | [**\SpatioClient\Model\IssueCollaborationTokenRequest**](../Model/IssueCollaborationTokenRequest.md)|  | [optional] |

### Return type

[**\SpatioClient\Model\IssueCollaborationToken200Response**](../Model/IssueCollaborationToken200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
