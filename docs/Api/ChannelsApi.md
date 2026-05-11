# SpatioClient\ChannelsApi

Group chat channels (Slack-style). Backed by the shared messaging engine; sibling of DirectMessages.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createChannel()**](ChannelsApi.md#createChannel) | **POST** /v1/channels | Create a channel. |
| [**executeChannelAction()**](ChannelsApi.md#executeChannelAction) | **POST** /v1/channels/execute | Dispatch a channel action by id. |
| [**joinChannel()**](ChannelsApi.md#joinChannel) | **POST** /v1/channels/{id}/join | Join a channel. |
| [**leaveChannel()**](ChannelsApi.md#leaveChannel) | **POST** /v1/channels/{id}/leave | Leave a channel. |
| [**listChannelActions()**](ChannelsApi.md#listChannelActions) | **GET** /v1/channels/actions | Discover the action catalog for the Channels platform. |
| [**listChannelMessages()**](ChannelsApi.md#listChannelMessages) | **GET** /v1/channels/messages | List messages in a channel. |
| [**listChannels()**](ChannelsApi.md#listChannels) | **GET** /v1/channels | List group channels across connected chat providers. |
| [**sendChannelMessage()**](ChannelsApi.md#sendChannelMessage) | **POST** /v1/channels/messages | Send a message to a channel. |
| [**workspaceCreateChannel()**](ChannelsApi.md#workspaceCreateChannel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels |  |
| [**workspaceExecuteChannelAction()**](ChannelsApi.md#workspaceExecuteChannelAction) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/execute |  |
| [**workspaceJoinChannel()**](ChannelsApi.md#workspaceJoinChannel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/{id}/join |  |
| [**workspaceLeaveChannel()**](ChannelsApi.md#workspaceLeaveChannel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/{id}/leave |  |
| [**workspaceListChannelActions()**](ChannelsApi.md#workspaceListChannelActions) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels/actions |  |
| [**workspaceListChannelMessages()**](ChannelsApi.md#workspaceListChannelMessages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels/messages |  |
| [**workspaceListChannels()**](ChannelsApi.md#workspaceListChannels) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels |  |
| [**workspaceSendChannelMessage()**](ChannelsApi.md#workspaceSendChannelMessage) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/messages |  |


## `createChannel()`

```php
createChannel($create_channel_request): \SpatioClient\Model\CreateChannelResponse
```

Create a channel.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_channel_request = new \SpatioClient\Model\CreateChannelRequest(); // \SpatioClient\Model\CreateChannelRequest

try {
    $result = $apiInstance->createChannel($create_channel_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->createChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_channel_request** | [**\SpatioClient\Model\CreateChannelRequest**](../Model/CreateChannelRequest.md)|  | |

### Return type

[**\SpatioClient\Model\CreateChannelResponse**](../Model/CreateChannelResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `executeChannelAction()`

```php
executeChannelAction($execute_chat_action_request): \SpatioClient\Model\ExecuteChatActionResponse
```

Dispatch a channel action by id.

Generic action-execution endpoint. `params` shape varies per `action_id`; consult `GET /v1/channels/actions` for the per-id contract.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$execute_chat_action_request = new \SpatioClient\Model\ExecuteChatActionRequest(); // \SpatioClient\Model\ExecuteChatActionRequest

try {
    $result = $apiInstance->executeChannelAction($execute_chat_action_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->executeChannelAction: ', $e->getMessage(), PHP_EOL;
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

## `joinChannel()`

```php
joinChannel($id, $channel_membership_request): \SpatioClient\Model\SuccessFlag
```

Join a channel.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Channel id (provider-scoped).
$channel_membership_request = new \SpatioClient\Model\ChannelMembershipRequest(); // \SpatioClient\Model\ChannelMembershipRequest

try {
    $result = $apiInstance->joinChannel($id, $channel_membership_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->joinChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Channel id (provider-scoped). | |
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

## `leaveChannel()`

```php
leaveChannel($id, $channel_membership_request): \SpatioClient\Model\SuccessFlag
```

Leave a channel.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Channel id (provider-scoped).
$channel_membership_request = new \SpatioClient\Model\ChannelMembershipRequest(); // \SpatioClient\Model\ChannelMembershipRequest

try {
    $result = $apiInstance->leaveChannel($id, $channel_membership_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->leaveChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Channel id (provider-scoped). | |
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

## `listChannelActions()`

```php
listChannelActions(): \SpatioClient\Model\ChatActionsList
```

Discover the action catalog for the Channels platform.

Returns the action descriptors the agent layer dispatches via `POST /v1/channels/execute`. Same pattern as the DirectMessages action surface.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listChannelActions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->listChannelActions: ', $e->getMessage(), PHP_EOL;
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

## `listChannelMessages()`

```php
listChannelMessages($channel, $account_id, $account_ids, $providers, $x_workspace_id, $limit, $cursor, $oldest_first): \SpatioClient\Model\ListMessagesResponse
```

List messages in a channel.

Channel ids are provider-scoped; pass `?accountId=` (preferred) or `?accountIds=` to disambiguate when the same id exists on multiple connected accounts (rare).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$channel = 'channel_example'; // string | Channel id.
$account_id = 'account_id_example'; // string
$account_ids = array('account_ids_example'); // string[] | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.
$providers = array('providers_example'); // string[] | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$limit = 56; // int
$cursor = 'cursor_example'; // string
$oldest_first = false; // bool

try {
    $result = $apiInstance->listChannelMessages($channel, $account_id, $account_ids, $providers, $x_workspace_id, $limit, $cursor, $oldest_first);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->listChannelMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **channel** | **string**| Channel id. | |
| **account_id** | **string**|  | [optional] |
| **account_ids** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used. | [optional] |
| **providers** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **limit** | **int**|  | [optional] |
| **cursor** | **string**|  | [optional] |
| **oldest_first** | **bool**|  | [optional] [default to false] |

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

## `listChannels()`

```php
listChannels($account_ids, $providers, $x_workspace_id, $limit, $cursor, $include_archived, $types): \SpatioClient\Model\ListChannelsResponse
```

List group channels across connected chat providers.

Fan-out list. The Channels surface filters to channel-type conversations only (`type: channel | private`); for direct messages use `/v1/direct-messages`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_ids = array('account_ids_example'); // string[] | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.
$providers = array('providers_example'); // string[] | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$limit = 56; // int
$cursor = 'cursor_example'; // string | Provider-specific pagination cursor.
$include_archived = false; // bool
$types = array('types_example'); // string[] | Repeatable filter on `Channel.type`. Defaults applied by the platform exclude DMs; passing this overrides.

try {
    $result = $apiInstance->listChannels($account_ids, $providers, $x_workspace_id, $limit, $cursor, $include_archived, $types);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->listChannels: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_ids** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used. | [optional] |
| **providers** | [**string[]**](../Model/string.md)| Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **limit** | **int**|  | [optional] |
| **cursor** | **string**| Provider-specific pagination cursor. | [optional] |
| **include_archived** | **bool**|  | [optional] [default to false] |
| **types** | [**string[]**](../Model/string.md)| Repeatable filter on &#x60;Channel.type&#x60;. Defaults applied by the platform exclude DMs; passing this overrides. | [optional] |

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

## `sendChannelMessage()`

```php
sendChannelMessage($send_chat_message_request): \SpatioClient\Model\SendChatMessageResponse
```

Send a message to a channel.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_chat_message_request = new \SpatioClient\Model\SendChatMessageRequest(); // \SpatioClient\Model\SendChatMessageRequest

try {
    $result = $apiInstance->sendChannelMessage($send_chat_message_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->sendChannelMessage: ', $e->getMessage(), PHP_EOL;
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

## `workspaceCreateChannel()`

```php
workspaceCreateChannel($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCreateChannel($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->workspaceCreateChannel: ', $e->getMessage(), PHP_EOL;
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

## `workspaceExecuteChannelAction()`

```php
workspaceExecuteChannelAction($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceExecuteChannelAction($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->workspaceExecuteChannelAction: ', $e->getMessage(), PHP_EOL;
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

## `workspaceJoinChannel()`

```php
workspaceJoinChannel($org, $workspace, $id, $request_body)
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $apiInstance->workspaceJoinChannel($org, $workspace, $id, $request_body);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->workspaceJoinChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **id** | **string**|  | |
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

## `workspaceLeaveChannel()`

```php
workspaceLeaveChannel($org, $workspace, $id, $request_body)
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $apiInstance->workspaceLeaveChannel($org, $workspace, $id, $request_body);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->workspaceLeaveChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **id** | **string**|  | |
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

## `workspaceListChannelActions()`

```php
workspaceListChannelActions($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListChannelActions($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->workspaceListChannelActions: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListChannelMessages()`

```php
workspaceListChannelMessages($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListChannelMessages($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->workspaceListChannelMessages: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListChannels()`

```php
workspaceListChannels($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListChannels($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->workspaceListChannels: ', $e->getMessage(), PHP_EOL;
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

## `workspaceSendChannelMessage()`

```php
workspaceSendChannelMessage($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceSendChannelMessage($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ChannelsApi->workspaceSendChannelMessage: ', $e->getMessage(), PHP_EOL;
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
