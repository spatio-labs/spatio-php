# SpatioClient\DirectMessagesApi

1:1 and group direct messages with reactions, threads, mute/pin/draft state, attachments, and search.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addDMReaction()**](DirectMessagesApi.md#addDMReaction) | **POST** /v1/direct-messages/messages/{messageId}/reactions | React to a DM message. |
| [**attachToDMMessage()**](DirectMessagesApi.md#attachToDMMessage) | **POST** /v1/direct-messages/messages/{messageId}/attachments | Attach a file/image/etc. to an existing DM message. |
| [**executeDMAction()**](DirectMessagesApi.md#executeDMAction) | **POST** /v1/direct-messages/execute | Dispatch a DM action by id. |
| [**forwardDMMessage()**](DirectMessagesApi.md#forwardDMMessage) | **POST** /v1/direct-messages/messages/{messageId}/forward | Forward a DM message to another DM or channel. |
| [**getDMUser()**](DirectMessagesApi.md#getDMUser) | **GET** /v1/direct-messages/users/{id} | Fetch one chat user. |
| [**listDMActions()**](DirectMessagesApi.md#listDMActions) | **GET** /v1/direct-messages/actions | Discover the action catalog for DirectMessages. |
| [**listDMPinnedMessages()**](DirectMessagesApi.md#listDMPinnedMessages) | **GET** /v1/direct-messages/{dmId}/pinned | List pinned messages in a DM conversation. |
| [**listDMThreadReplies()**](DirectMessagesApi.md#listDMThreadReplies) | **GET** /v1/direct-messages/{dmId}/messages/{messageId}/replies | List replies in a DM message thread. |
| [**listDMUsers()**](DirectMessagesApi.md#listDMUsers) | **GET** /v1/direct-messages/users | List chat users (DM contacts) across connected accounts. |
| [**listDirectConversationsEnriched()**](DirectMessagesApi.md#listDirectConversationsEnriched) | **GET** /v1/direct-messages/conversations | Enriched DM conversation list with unread + pin + draft state. |
| [**listDirectMessageConversations()**](DirectMessagesApi.md#listDirectMessageConversations) | **GET** /v1/direct-messages | List 1:1 and group DM conversations. |
| [**listDirectMessages()**](DirectMessagesApi.md#listDirectMessages) | **GET** /v1/direct-messages/messages | List messages in a DM conversation. |
| [**markDMRead()**](DirectMessagesApi.md#markDMRead) | **POST** /v1/direct-messages/{dmId}/read | Mark a DM message read. |
| [**muteDM()**](DirectMessagesApi.md#muteDM) | **POST** /v1/direct-messages/{dmId}/mute | Mute a DM conversation (until a time, or forever). |
| [**pinDMConversation()**](DirectMessagesApi.md#pinDMConversation) | **POST** /v1/direct-messages/{dmId}/pin | Pin a DM conversation to the top of the sidebar. |
| [**pinDMMessage()**](DirectMessagesApi.md#pinDMMessage) | **POST** /v1/direct-messages/messages/{messageId}/pin | Pin a DM message. |
| [**postDMThreadReply()**](DirectMessagesApi.md#postDMThreadReply) | **POST** /v1/direct-messages/{dmId}/messages/{messageId}/replies | Reply in a DM message thread. |
| [**removeDMReaction()**](DirectMessagesApi.md#removeDMReaction) | **DELETE** /v1/direct-messages/messages/{messageId}/reactions/{emoji} | Remove a DM message reaction. |
| [**searchDirectMessages()**](DirectMessagesApi.md#searchDirectMessages) | **GET** /v1/direct-messages/search | Search across DM messages. |
| [**sendDirectMessage()**](DirectMessagesApi.md#sendDirectMessage) | **POST** /v1/direct-messages/messages | Send a DM. |
| [**setDMDraft()**](DirectMessagesApi.md#setDMDraft) | **PUT** /v1/direct-messages/{dmId}/draft | Save the unsent draft text for a DM. |
| [**unpinDMConversation()**](DirectMessagesApi.md#unpinDMConversation) | **DELETE** /v1/direct-messages/{dmId}/pin | Unpin a DM conversation. |
| [**unpinDMMessage()**](DirectMessagesApi.md#unpinDMMessage) | **DELETE** /v1/direct-messages/messages/{messageId}/pin | Unpin a DM message. |
| [**workspaceExecuteDMAction()**](DirectMessagesApi.md#workspaceExecuteDMAction) | **POST** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/execute |  |
| [**workspaceGetDMUser()**](DirectMessagesApi.md#workspaceGetDMUser) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/users/{id} |  |
| [**workspaceListDMActions()**](DirectMessagesApi.md#workspaceListDMActions) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/actions |  |
| [**workspaceListDMConversations()**](DirectMessagesApi.md#workspaceListDMConversations) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/conversations |  |
| [**workspaceListDMMessages()**](DirectMessagesApi.md#workspaceListDMMessages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/messages |  |
| [**workspaceListDMUsers()**](DirectMessagesApi.md#workspaceListDMUsers) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/users |  |
| [**workspaceListDirectMessages()**](DirectMessagesApi.md#workspaceListDirectMessages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages |  |
| [**workspaceSendDirectMessage()**](DirectMessagesApi.md#workspaceSendDirectMessage) | **POST** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/messages |  |


## `addDMReaction()`

```php
addDMReaction($message_id, $dm_reaction_request): \SpatioClient\Model\DMReactionResponse
```

React to a DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | Chat-message id.
$dm_reaction_request = new \SpatioClient\Model\DMReactionRequest(); // \SpatioClient\Model\DMReactionRequest

try {
    $result = $apiInstance->addDMReaction($message_id, $dm_reaction_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->addDMReaction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| Chat-message id. | |
| **dm_reaction_request** | [**\SpatioClient\Model\DMReactionRequest**](../Model/DMReactionRequest.md)|  | |

### Return type

[**\SpatioClient\Model\DMReactionResponse**](../Model/DMReactionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `attachToDMMessage()`

```php
attachToDMMessage($message_id, $dm_attach_request): \SpatioClient\Model\DMMessageEnvelope
```

Attach a file/image/etc. to an existing DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | Chat-message id.
$dm_attach_request = new \SpatioClient\Model\DMAttachRequest(); // \SpatioClient\Model\DMAttachRequest

try {
    $result = $apiInstance->attachToDMMessage($message_id, $dm_attach_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->attachToDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| Chat-message id. | |
| **dm_attach_request** | [**\SpatioClient\Model\DMAttachRequest**](../Model/DMAttachRequest.md)|  | |

### Return type

[**\SpatioClient\Model\DMMessageEnvelope**](../Model/DMMessageEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `executeDMAction()`

```php
executeDMAction($execute_chat_action_request): \SpatioClient\Model\ExecuteChatActionResponse
```

Dispatch a DM action by id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$execute_chat_action_request = new \SpatioClient\Model\ExecuteChatActionRequest(); // \SpatioClient\Model\ExecuteChatActionRequest

try {
    $result = $apiInstance->executeDMAction($execute_chat_action_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->executeDMAction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **execute_chat_action_request** | [**\SpatioClient\Model\ExecuteChatActionRequest**](../Model/ExecuteChatActionRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ExecuteChatActionResponse**](../Model/ExecuteChatActionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `forwardDMMessage()`

```php
forwardDMMessage($message_id, $dm_forward_request): \SpatioClient\Model\DMMessageEnvelope
```

Forward a DM message to another DM or channel.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | Chat-message id.
$dm_forward_request = new \SpatioClient\Model\DMForwardRequest(); // \SpatioClient\Model\DMForwardRequest

try {
    $result = $apiInstance->forwardDMMessage($message_id, $dm_forward_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->forwardDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| Chat-message id. | |
| **dm_forward_request** | [**\SpatioClient\Model\DMForwardRequest**](../Model/DMForwardRequest.md)|  | |

### Return type

[**\SpatioClient\Model\DMMessageEnvelope**](../Model/DMMessageEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getDMUser()`

```php
getDMUser($id, $account_id): \SpatioClient\Model\GetChatUserResponse
```

Fetch one chat user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Chat-user id (provider-scoped).
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->getDMUser($id, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->getDMUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Chat-user id (provider-scoped). | |
| **account_id** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\GetChatUserResponse**](../Model/GetChatUserResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDMActions()`

```php
listDMActions(): \SpatioClient\Model\ChatActionsList
```

Discover the action catalog for DirectMessages.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listDMActions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->listDMActions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\ChatActionsList**](../Model/ChatActionsList.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDMPinnedMessages()`

```php
listDMPinnedMessages($dm_id, $account_id): \SpatioClient\Model\DMPinnedList
```

List pinned messages in a DM conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string | Direct-message conversation id.
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->listDMPinnedMessages($dm_id, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->listDMPinnedMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**| Direct-message conversation id. | |
| **account_id** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\DMPinnedList**](../Model/DMPinnedList.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDMThreadReplies()`

```php
listDMThreadReplies($dm_id, $message_id, $account_id): array<string,mixed>
```

List replies in a DM message thread.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string | Direct-message conversation id.
$message_id = 'message_id_example'; // string | Chat-message id.
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->listDMThreadReplies($dm_id, $message_id, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->listDMThreadReplies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**| Direct-message conversation id. | |
| **message_id** | **string**| Chat-message id. | |
| **account_id** | **string**|  | [optional] |

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

## `listDMUsers()`

```php
listDMUsers($account_ids, $providers, $x_workspace_id, $limit, $cursor): \SpatioClient\Model\ListChatUsersResponse
```

List chat users (DM contacts) across connected accounts.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_ids = array('account_ids_example'); // string[] | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.
$providers = array('providers_example'); // string[] | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$limit = 56; // int
$cursor = 'cursor_example'; // string

try {
    $result = $apiInstance->listDMUsers($account_ids, $providers, $x_workspace_id, $limit, $cursor);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->listDMUsers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_ids** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used. | [optional] |
| **providers** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **limit** | **int**|  | [optional] |
| **cursor** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\ListChatUsersResponse**](../Model/ListChatUsersResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDirectConversationsEnriched()`

```php
listDirectConversationsEnriched($account_id, $x_workspace_id): array<string,mixed>
```

Enriched DM conversation list with unread + pin + draft state.

Native fast-path. Returns conversations augmented with the DM-feature state (unread counts, pinned/muted flags, saved drafts) the renderer's DM UI consumes. The shape is provider-specific and treated as opaque.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_id = 'account_id_example'; // string
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->listDirectConversationsEnriched($account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->listDirectConversationsEnriched: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**|  | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

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

## `listDirectMessageConversations()`

```php
listDirectMessageConversations($account_ids, $providers, $x_workspace_id, $limit, $cursor, $include_archived): \SpatioClient\Model\ListChannelsResponse
```

List 1:1 and group DM conversations.

Returns DM-type conversations only (`type: im | mpim`). Channel-type conversations are surfaced via `/v1/channels`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_ids = array('account_ids_example'); // string[] | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.
$providers = array('providers_example'); // string[] | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$limit = 56; // int
$cursor = 'cursor_example'; // string
$include_archived = false; // bool

try {
    $result = $apiInstance->listDirectMessageConversations($account_ids, $providers, $x_workspace_id, $limit, $cursor, $include_archived);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->listDirectMessageConversations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_ids** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used. | [optional] |
| **providers** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **limit** | **int**|  | [optional] |
| **cursor** | **string**|  | [optional] |
| **include_archived** | **bool**|  | [optional] [default to false] |

### Return type

[**\SpatioClient\Model\ListChannelsResponse**](../Model/ListChannelsResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDirectMessages()`

```php
listDirectMessages($channel, $account_id, $account_ids, $providers, $x_workspace_id, $limit, $cursor, $oldest_first): \SpatioClient\Model\ListMessagesResponse
```

List messages in a DM conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$channel = 'channel_example'; // string | DM conversation id.
$account_id = 'account_id_example'; // string
$account_ids = array('account_ids_example'); // string[] | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.
$providers = array('providers_example'); // string[] | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$limit = 56; // int
$cursor = 'cursor_example'; // string
$oldest_first = True; // bool

try {
    $result = $apiInstance->listDirectMessages($channel, $account_id, $account_ids, $providers, $x_workspace_id, $limit, $cursor, $oldest_first);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->listDirectMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **channel** | **string**| DM conversation id. | |
| **account_id** | **string**|  | [optional] |
| **account_ids** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used. | [optional] |
| **providers** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **limit** | **int**|  | [optional] |
| **cursor** | **string**|  | [optional] |
| **oldest_first** | **bool**|  | [optional] |

### Return type

[**\SpatioClient\Model\ListMessagesResponse**](../Model/ListMessagesResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `markDMRead()`

```php
markDMRead($dm_id, $dm_mark_read_request): \SpatioClient\Model\SuccessFlag
```

Mark a DM message read.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string | Direct-message conversation id.
$dm_mark_read_request = new \SpatioClient\Model\DMMarkReadRequest(); // \SpatioClient\Model\DMMarkReadRequest

try {
    $result = $apiInstance->markDMRead($dm_id, $dm_mark_read_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->markDMRead: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**| Direct-message conversation id. | |
| **dm_mark_read_request** | [**\SpatioClient\Model\DMMarkReadRequest**](../Model/DMMarkReadRequest.md)|  | |

### Return type

[**\SpatioClient\Model\SuccessFlag**](../Model/SuccessFlag.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `muteDM()`

```php
muteDM($dm_id, $dm_mute_request): \SpatioClient\Model\DMMuteResponse
```

Mute a DM conversation (until a time, or forever).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string | Direct-message conversation id.
$dm_mute_request = new \SpatioClient\Model\DMMuteRequest(); // \SpatioClient\Model\DMMuteRequest

try {
    $result = $apiInstance->muteDM($dm_id, $dm_mute_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->muteDM: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**| Direct-message conversation id. | |
| **dm_mute_request** | [**\SpatioClient\Model\DMMuteRequest**](../Model/DMMuteRequest.md)|  | |

### Return type

[**\SpatioClient\Model\DMMuteResponse**](../Model/DMMuteResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `pinDMConversation()`

```php
pinDMConversation($dm_id, $account_id): \SpatioClient\Model\SuccessFlag
```

Pin a DM conversation to the top of the sidebar.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string | Direct-message conversation id.
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->pinDMConversation($dm_id, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->pinDMConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**| Direct-message conversation id. | |
| **account_id** | **string**|  | [optional] |

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

## `pinDMMessage()`

```php
pinDMMessage($message_id, $channel_membership_request): \SpatioClient\Model\SuccessFlag
```

Pin a DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | Chat-message id.
$channel_membership_request = new \SpatioClient\Model\ChannelMembershipRequest(); // \SpatioClient\Model\ChannelMembershipRequest

try {
    $result = $apiInstance->pinDMMessage($message_id, $channel_membership_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->pinDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| Chat-message id. | |
| **channel_membership_request** | [**\SpatioClient\Model\ChannelMembershipRequest**](../Model/ChannelMembershipRequest.md)|  | [optional] |

### Return type

[**\SpatioClient\Model\SuccessFlag**](../Model/SuccessFlag.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postDMThreadReply()`

```php
postDMThreadReply($dm_id, $message_id, $dm_thread_reply_request, $account_id): \SpatioClient\Model\DMMessageEnvelope
```

Reply in a DM message thread.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string | Direct-message conversation id.
$message_id = 'message_id_example'; // string | Chat-message id.
$dm_thread_reply_request = new \SpatioClient\Model\DMThreadReplyRequest(); // \SpatioClient\Model\DMThreadReplyRequest
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->postDMThreadReply($dm_id, $message_id, $dm_thread_reply_request, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->postDMThreadReply: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**| Direct-message conversation id. | |
| **message_id** | **string**| Chat-message id. | |
| **dm_thread_reply_request** | [**\SpatioClient\Model\DMThreadReplyRequest**](../Model/DMThreadReplyRequest.md)|  | |
| **account_id** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\DMMessageEnvelope**](../Model/DMMessageEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `removeDMReaction()`

```php
removeDMReaction($message_id, $emoji, $account_id): \SpatioClient\Model\DMReactionResponse
```

Remove a DM message reaction.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | Chat-message id.
$emoji = 'emoji_example'; // string | Reaction emoji (e.g. `+1`, `eyes`, `pepper`).
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->removeDMReaction($message_id, $emoji, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->removeDMReaction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| Chat-message id. | |
| **emoji** | **string**| Reaction emoji (e.g. &#x60;+1&#x60;, &#x60;eyes&#x60;, &#x60;pepper&#x60;). | |
| **account_id** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\DMReactionResponse**](../Model/DMReactionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchDirectMessages()`

```php
searchDirectMessages($q, $limit, $dm_id, $user, $account_id): \SpatioClient\Model\DMSearchResults
```

Search across DM messages.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$q = 'q_example'; // string | Free-form query string.
$limit = 56; // int
$dm_id = 'dm_id_example'; // string | Restrict to one conversation.
$user = 'user_example'; // string | Restrict to messages from this user id.
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->searchDirectMessages($q, $limit, $dm_id, $user, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->searchDirectMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **q** | **string**| Free-form query string. | |
| **limit** | **int**|  | [optional] |
| **dm_id** | **string**| Restrict to one conversation. | [optional] |
| **user** | **string**| Restrict to messages from this user id. | [optional] |
| **account_id** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\DMSearchResults**](../Model/DMSearchResults.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendDirectMessage()`

```php
sendDirectMessage($send_chat_message_request): \SpatioClient\Model\SendChatMessageResponse
```

Send a DM.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_chat_message_request = new \SpatioClient\Model\SendChatMessageRequest(); // \SpatioClient\Model\SendChatMessageRequest

try {
    $result = $apiInstance->sendDirectMessage($send_chat_message_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->sendDirectMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_chat_message_request** | [**\SpatioClient\Model\SendChatMessageRequest**](../Model/SendChatMessageRequest.md)|  | |

### Return type

[**\SpatioClient\Model\SendChatMessageResponse**](../Model/SendChatMessageResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `setDMDraft()`

```php
setDMDraft($dm_id, $dm_set_draft_request): \SpatioClient\Model\SuccessFlag
```

Save the unsent draft text for a DM.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string | Direct-message conversation id.
$dm_set_draft_request = new \SpatioClient\Model\DMSetDraftRequest(); // \SpatioClient\Model\DMSetDraftRequest

try {
    $result = $apiInstance->setDMDraft($dm_id, $dm_set_draft_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->setDMDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**| Direct-message conversation id. | |
| **dm_set_draft_request** | [**\SpatioClient\Model\DMSetDraftRequest**](../Model/DMSetDraftRequest.md)|  | |

### Return type

[**\SpatioClient\Model\SuccessFlag**](../Model/SuccessFlag.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `unpinDMConversation()`

```php
unpinDMConversation($dm_id, $account_id): \SpatioClient\Model\SuccessFlag
```

Unpin a DM conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dm_id = 'dm_id_example'; // string | Direct-message conversation id.
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->unpinDMConversation($dm_id, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->unpinDMConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dm_id** | **string**| Direct-message conversation id. | |
| **account_id** | **string**|  | [optional] |

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

## `unpinDMMessage()`

```php
unpinDMMessage($message_id, $account_id): \SpatioClient\Model\SuccessFlag
```

Unpin a DM message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | Chat-message id.
$account_id = 'account_id_example'; // string

try {
    $result = $apiInstance->unpinDMMessage($message_id, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->unpinDMMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| Chat-message id. | |
| **account_id** | **string**|  | [optional] |

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

## `workspaceExecuteDMAction()`

```php
workspaceExecuteDMAction($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceExecuteDMAction($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->workspaceExecuteDMAction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
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

## `workspaceGetDMUser()`

```php
workspaceGetDMUser($org, $workspace, $id): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $result = $apiInstance->workspaceGetDMUser($org, $workspace, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->workspaceGetDMUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
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

## `workspaceListDMActions()`

```php
workspaceListDMActions($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListDMActions($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->workspaceListDMActions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |

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

## `workspaceListDMConversations()`

```php
workspaceListDMConversations($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListDMConversations($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->workspaceListDMConversations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |

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

## `workspaceListDMMessages()`

```php
workspaceListDMMessages($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListDMMessages($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->workspaceListDMMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |

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

## `workspaceListDMUsers()`

```php
workspaceListDMUsers($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListDMUsers($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->workspaceListDMUsers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |

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

## `workspaceListDirectMessages()`

```php
workspaceListDirectMessages($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListDirectMessages($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->workspaceListDirectMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |

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

## `workspaceSendDirectMessage()`

```php
workspaceSendDirectMessage($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\DirectMessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceSendDirectMessage($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DirectMessagesApi->workspaceSendDirectMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
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
