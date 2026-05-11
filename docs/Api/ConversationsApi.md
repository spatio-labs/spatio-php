# SpatioClient\ConversationsApi

Persisted LLM conversations (titles, messages, metadata) used by the agent + sidebar chats.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createConversation()**](ConversationsApi.md#createConversation) | **POST** /v1/conversations | Persist a new LLM conversation. |
| [**deleteConversation()**](ConversationsApi.md#deleteConversation) | **DELETE** /v1/conversations/{id} | Soft-delete a conversation. |
| [**getConversation()**](ConversationsApi.md#getConversation) | **GET** /v1/conversations/{id} | Fetch one conversation. |
| [**getLatestConversationForContext()**](ConversationsApi.md#getLatestConversationForContext) | **GET** /v1/conversations/latest | Fetch the most recently active conversation for a given context tag. |
| [**listConversationMessages()**](ConversationsApi.md#listConversationMessages) | **GET** /v1/conversations/{id}/messages | List messages in a conversation. |
| [**listConversations()**](ConversationsApi.md#listConversations) | **GET** /v1/conversations | List the caller&#39;s persisted LLM conversations. |
| [**saveConversationMessage()**](ConversationsApi.md#saveConversationMessage) | **POST** /v1/conversations/{id}/messages | Append a message to a conversation. |
| [**updateConversation()**](ConversationsApi.md#updateConversation) | **PATCH** /v1/conversations/{id} | Update conversation metadata (title, context, cwd, session_id, pinned). |
| [**updateConversationMessageMetadata()**](ConversationsApi.md#updateConversationMessageMetadata) | **PATCH** /v1/conversations/{id}/messages | Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message). |


## `createConversation()`

```php
createConversation($create_conversation_request): \SpatioClient\Model\Conversation
```

Persist a new LLM conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_conversation_request = new \SpatioClient\Model\CreateConversationRequest(); // \SpatioClient\Model\CreateConversationRequest

try {
    $result = $apiInstance->createConversation($create_conversation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->createConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_conversation_request** | [**\SpatioClient\Model\CreateConversationRequest**](../Model/CreateConversationRequest.md)|  | [optional] |

### Return type

[**\SpatioClient\Model\Conversation**](../Model/Conversation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteConversation()`

```php
deleteConversation($id)
```

Soft-delete a conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteConversation($id);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->deleteConversation: ', $e->getMessage(), PHP_EOL;
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

## `getConversation()`

```php
getConversation($id): \SpatioClient\Model\Conversation
```

Fetch one conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getConversation($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->getConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\Conversation**](../Model/Conversation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getLatestConversationForContext()`

```php
getLatestConversationForContext($context): \SpatioClient\Model\Conversation
```

Fetch the most recently active conversation for a given context tag.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$context = 'context_example'; // string

try {
    $result = $apiInstance->getLatestConversationForContext($context);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->getLatestConversationForContext: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **context** | **string**|  | |

### Return type

[**\SpatioClient\Model\Conversation**](../Model/Conversation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listConversationMessages()`

```php
listConversationMessages($id, $limit, $before): \SpatioClient\Model\ConversationMessage[]
```

List messages in a conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$limit = 56; // int
$before = 'before_example'; // string

try {
    $result = $apiInstance->listConversationMessages($id, $limit, $before);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->listConversationMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **limit** | **int**|  | [optional] |
| **before** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\ConversationMessage[]**](../Model/ConversationMessage.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listConversations()`

```php
listConversations($context, $limit): \SpatioClient\Model\Conversation[]
```

List the caller's persisted LLM conversations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$context = 'context_example'; // string
$limit = 56; // int

try {
    $result = $apiInstance->listConversations($context, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->listConversations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **context** | **string**|  | [optional] |
| **limit** | **int**|  | [optional] |

### Return type

[**\SpatioClient\Model\Conversation[]**](../Model/Conversation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `saveConversationMessage()`

```php
saveConversationMessage($id, $save_message_request): \SpatioClient\Model\ConversationMessage
```

Append a message to a conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$save_message_request = new \SpatioClient\Model\SaveMessageRequest(); // \SpatioClient\Model\SaveMessageRequest

try {
    $result = $apiInstance->saveConversationMessage($id, $save_message_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->saveConversationMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **save_message_request** | [**\SpatioClient\Model\SaveMessageRequest**](../Model/SaveMessageRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ConversationMessage**](../Model/ConversationMessage.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateConversation()`

```php
updateConversation($id, $update_conversation_request): \SpatioClient\Model\Conversation
```

Update conversation metadata (title, context, cwd, session_id, pinned).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_conversation_request = new \SpatioClient\Model\UpdateConversationRequest(); // \SpatioClient\Model\UpdateConversationRequest

try {
    $result = $apiInstance->updateConversation($id, $update_conversation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->updateConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_conversation_request** | [**\SpatioClient\Model\UpdateConversationRequest**](../Model/UpdateConversationRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Conversation**](../Model/Conversation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateConversationMessageMetadata()`

```php
updateConversationMessageMetadata($id, $update_message_metadata_request): \SpatioClient\Model\ConversationMessage
```

Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_message_metadata_request = new \SpatioClient\Model\UpdateMessageMetadataRequest(); // \SpatioClient\Model\UpdateMessageMetadataRequest

try {
    $result = $apiInstance->updateConversationMessageMetadata($id, $update_message_metadata_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->updateConversationMessageMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_message_metadata_request** | [**\SpatioClient\Model\UpdateMessageMetadataRequest**](../Model/UpdateMessageMetadataRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ConversationMessage**](../Model/ConversationMessage.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
