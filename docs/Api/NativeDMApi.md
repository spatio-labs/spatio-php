# SpatioClient\NativeDMApi

Spatio&#39;s first-party native DM messaging (&#x60;/v1/native/dm/_*&#x60;). Distinct from the cross-provider &#x60;/v1/direct-messages&#x60; directory.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addNativeDMReaction()**](NativeDMApi.md#addNativeDMReaction) | **POST** /v1/native/dm/messages/{messageId}/reactions | Add a reaction to a DM message. |
| [**attachToNativeDMMessage()**](NativeDMApi.md#attachToNativeDMMessage) | **POST** /v1/native/dm/messages/{messageId}/attachments | Attach a file to a DM message. |
| [**deleteNativeDMMessage()**](NativeDMApi.md#deleteNativeDMMessage) | **DELETE** /v1/native/dm/{dmId}/messages/{messageId} | Delete a DM message. |
| [**forwardNativeDMMessage()**](NativeDMApi.md#forwardNativeDMMessage) | **POST** /v1/native/dm/messages/{messageId}/forward | Forward a DM message to another conversation. |
| [**listNativeDMChannels()**](NativeDMApi.md#listNativeDMChannels) | **GET** /v1/native/dm | List the caller&#39;s DM channels. |
| [**listNativeDMConversations()**](NativeDMApi.md#listNativeDMConversations) | **GET** /v1/native/dm/conversations | List DM conversations with metadata (last message, unread count, etc.). |
| [**listNativeDMMessages()**](NativeDMApi.md#listNativeDMMessages) | **GET** /v1/native/dm/{dmId}/messages | List messages in a DM. |
| [**listNativeDMPinnedMessages()**](NativeDMApi.md#listNativeDMPinnedMessages) | **GET** /v1/native/dm/{dmId}/pinned | List pinned messages in a DM. |
| [**listNativeDMThreadReplies()**](NativeDMApi.md#listNativeDMThreadReplies) | **GET** /v1/native/dm/{dmId}/messages/{messageId}/replies | List threaded replies on a message. |
| [**markNativeDMRead()**](NativeDMApi.md#markNativeDMRead) | **POST** /v1/native/dm/{dmId}/read | Mark a DM as read. |
| [**muteNativeDM()**](NativeDMApi.md#muteNativeDM) | **POST** /v1/native/dm/{dmId}/mute | Mute a DM. |
| [**pinNativeDMConversation()**](NativeDMApi.md#pinNativeDMConversation) | **POST** /v1/native/dm/{dmId}/pin | Pin a DM conversation in the sidebar. |
| [**pinNativeDMMessage()**](NativeDMApi.md#pinNativeDMMessage) | **POST** /v1/native/dm/messages/{messageId}/pin | Pin a DM message. |
| [**postNativeDMMessage()**](NativeDMApi.md#postNativeDMMessage) | **POST** /v1/native/dm | Post a DM message (top-level entry). |
| [**postNativeDMThreadReply()**](NativeDMApi.md#postNativeDMThreadReply) | **POST** /v1/native/dm/{dmId}/messages/{messageId}/replies | Post a threaded reply. |
| [**removeNativeDMReaction()**](NativeDMApi.md#removeNativeDMReaction) | **DELETE** /v1/native/dm/messages/{messageId}/reactions/{emoji} | Remove a reaction. |
| [**searchNativeDMMessages()**](NativeDMApi.md#searchNativeDMMessages) | **GET** /v1/native/dm/search | Search DM messages. |
| [**setNativeDMDraft()**](NativeDMApi.md#setNativeDMDraft) | **PUT** /v1/native/dm/{dmId}/draft | Save a draft on a DM conversation. |
| [**unpinNativeDMConversation()**](NativeDMApi.md#unpinNativeDMConversation) | **DELETE** /v1/native/dm/{dmId}/pin | Unpin a DM conversation. |
| [**unpinNativeDMMessage()**](NativeDMApi.md#unpinNativeDMMessage) | **DELETE** /v1/native/dm/messages/{messageId}/pin | Unpin a DM message. |
| [**updateNativeDMMessage()**](NativeDMApi.md#updateNativeDMMessage) | **PATCH** /v1/native/dm/{dmId}/messages/{messageId} | Update a DM message body. |


## `addNativeDMReaction()`

```php
addNativeDMReaction($message_id, $request_body): array<string,mixed>
```

Add a reaction to a DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->addNativeDMReaction($message_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->addNativeDMReaction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

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

## `attachToNativeDMMessage()`

```php
attachToNativeDMMessage($message_id, $request_body): array<string,mixed>
```

Attach a file to a DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->attachToNativeDMMessage($message_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->attachToNativeDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

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

## `deleteNativeDMMessage()`

```php
deleteNativeDMMessage($dm_id, $message_id)
```

Delete a DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string
$message_id = 'message_id_example'; // string

try {
    $apiInstance->deleteNativeDMMessage($dm_id, $message_id);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->deleteNativeDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |
| **message_id** | **string**|  | |

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

## `forwardNativeDMMessage()`

```php
forwardNativeDMMessage($message_id, $request_body): array<string,mixed>
```

Forward a DM message to another conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->forwardNativeDMMessage($message_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->forwardNativeDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

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

## `listNativeDMChannels()`

```php
listNativeDMChannels(): array<string,mixed>
```

List the caller's DM channels.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listNativeDMChannels();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->listNativeDMChannels: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `listNativeDMConversations()`

```php
listNativeDMConversations(): array<string,mixed>
```

List DM conversations with metadata (last message, unread count, etc.).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listNativeDMConversations();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->listNativeDMConversations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `listNativeDMMessages()`

```php
listNativeDMMessages($dm_id): array<string,mixed>
```

List messages in a DM.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string

try {
    $result = $apiInstance->listNativeDMMessages($dm_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->listNativeDMMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |

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

## `listNativeDMPinnedMessages()`

```php
listNativeDMPinnedMessages($dm_id): array<string,mixed>
```

List pinned messages in a DM.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string

try {
    $result = $apiInstance->listNativeDMPinnedMessages($dm_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->listNativeDMPinnedMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |

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

## `listNativeDMThreadReplies()`

```php
listNativeDMThreadReplies($dm_id, $message_id): array<string,mixed>
```

List threaded replies on a message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string
$message_id = 'message_id_example'; // string

try {
    $result = $apiInstance->listNativeDMThreadReplies($dm_id, $message_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->listNativeDMThreadReplies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |
| **message_id** | **string**|  | |

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

## `markNativeDMRead()`

```php
markNativeDMRead($dm_id)
```

Mark a DM as read.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string

try {
    $apiInstance->markNativeDMRead($dm_id);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->markNativeDMRead: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |

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

## `muteNativeDM()`

```php
muteNativeDM($dm_id, $request_body)
```

Mute a DM.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $apiInstance->muteNativeDM($dm_id, $request_body);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->muteNativeDM: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | [optional] |

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

## `pinNativeDMConversation()`

```php
pinNativeDMConversation($dm_id)
```

Pin a DM conversation in the sidebar.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string

try {
    $apiInstance->pinNativeDMConversation($dm_id);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->pinNativeDMConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |

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

## `pinNativeDMMessage()`

```php
pinNativeDMMessage($message_id)
```

Pin a DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string

try {
    $apiInstance->pinNativeDMMessage($message_id);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->pinNativeDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**|  | |

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

## `postNativeDMMessage()`

```php
postNativeDMMessage($request_body): array<string,mixed>
```

Post a DM message (top-level entry).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->postNativeDMMessage($request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->postNativeDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

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

## `postNativeDMThreadReply()`

```php
postNativeDMThreadReply($dm_id, $message_id, $request_body): array<string,mixed>
```

Post a threaded reply.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string
$message_id = 'message_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->postNativeDMThreadReply($dm_id, $message_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->postNativeDMThreadReply: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |
| **message_id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

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

## `removeNativeDMReaction()`

```php
removeNativeDMReaction($message_id, $emoji)
```

Remove a reaction.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string
$emoji = 'emoji_example'; // string

try {
    $apiInstance->removeNativeDMReaction($message_id, $emoji);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->removeNativeDMReaction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**|  | |
| **emoji** | **string**|  | |

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

## `searchNativeDMMessages()`

```php
searchNativeDMMessages($q): array<string,mixed>
```

Search DM messages.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$q = 'q_example'; // string

try {
    $result = $apiInstance->searchNativeDMMessages($q);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->searchNativeDMMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **q** | **string**|  | [optional] |

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

## `setNativeDMDraft()`

```php
setNativeDMDraft($dm_id, $request_body)
```

Save a draft on a DM conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $apiInstance->setNativeDMDraft($dm_id, $request_body);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->setNativeDMDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

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

## `unpinNativeDMConversation()`

```php
unpinNativeDMConversation($dm_id)
```

Unpin a DM conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string

try {
    $apiInstance->unpinNativeDMConversation($dm_id);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->unpinNativeDMConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |

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

## `unpinNativeDMMessage()`

```php
unpinNativeDMMessage($message_id)
```

Unpin a DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string

try {
    $apiInstance->unpinNativeDMMessage($message_id);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->unpinNativeDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**|  | |

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

## `updateNativeDMMessage()`

```php
updateNativeDMMessage($dm_id, $message_id, $request_body): array<string,mixed>
```

Update a DM message body.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NativeDMApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string
$message_id = 'message_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->updateNativeDMMessage($dm_id, $message_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NativeDMApi->updateNativeDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**|  | |
| **message_id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | |

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
