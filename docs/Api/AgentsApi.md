# SpatioClient\AgentsApi

Agent configuration management (&#x60;/v1/agents&#x60;) plus agent runtime endpoints (&#x60;/v1/agent/_*&#x60;) — conversations, action execution, session-context bundle.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAgent()**](AgentsApi.md#createAgent) | **POST** /v1/agents | Create a new agent configuration. |
| [**createAgentConversation()**](AgentsApi.md#createAgentConversation) | **POST** /v1/agent/conversations | Create a new agent-platform conversation. |
| [**createAgentMessage()**](AgentsApi.md#createAgentMessage) | **POST** /v1/agent/conversations/{id}/messages | Append a message to an agent conversation. |
| [**deleteAgent()**](AgentsApi.md#deleteAgent) | **DELETE** /v1/agents/{id} | Delete an agent configuration. |
| [**executeAgentAction()**](AgentsApi.md#executeAgentAction) | **POST** /v1/agent/actions/execute | Execute an action through the agent platform. |
| [**getAgent()**](AgentsApi.md#getAgent) | **GET** /v1/agents/{id} | Fetch one agent configuration. |
| [**getAgentConversation()**](AgentsApi.md#getAgentConversation) | **GET** /v1/agent/conversations/{id} | Fetch one agent conversation. |
| [**getAgentSessionContext()**](AgentsApi.md#getAgentSessionContext) | **GET** /v1/agent/session-context | Identity bundle for the SessionStart hook (user + org + workspace + connected accounts) so the agent doesn&#39;t fish on its first turn. |
| [**listAgentConversationMessages()**](AgentsApi.md#listAgentConversationMessages) | **GET** /v1/agent/conversations/{id}/messages | List messages on an agent conversation. |
| [**listAgentConversations()**](AgentsApi.md#listAgentConversations) | **GET** /v1/agent/conversations | List the caller&#39;s agent-platform conversations. Distinct from &#x60;/v1/conversations&#x60; (renderer-driven sidebar persistence). |
| [**listAgents()**](AgentsApi.md#listAgents) | **GET** /v1/agents | List the caller&#39;s agent configurations. |
| [**listPreconfiguredAgents()**](AgentsApi.md#listPreconfiguredAgents) | **GET** /v1/agents/preconfigured | Curated featured agents (e.g. \&quot;Claude Code\&quot;, \&quot;Research Assistant\&quot;). Read-only — these are surfaced by the renderer&#39;s preconfigured-picker UI. |
| [**updateAgent()**](AgentsApi.md#updateAgent) | **PATCH** /v1/agents/{id} | Update an agent configuration. |


## `createAgent()`

```php
createAgent($create_agent_request): \SpatioClient\Model\Agent
```

Create a new agent configuration.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_agent_request = new \SpatioClient\Model\CreateAgentRequest(); // \SpatioClient\Model\CreateAgentRequest

try {
    $result = $apiInstance->createAgent($create_agent_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->createAgent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_agent_request** | [**\SpatioClient\Model\CreateAgentRequest**](../Model/CreateAgentRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Agent**](../Model/Agent.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createAgentConversation()`

```php
createAgentConversation($create_agent_conversation_request): \SpatioClient\Model\AgentConversation
```

Create a new agent-platform conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_agent_conversation_request = new \SpatioClient\Model\CreateAgentConversationRequest(); // \SpatioClient\Model\CreateAgentConversationRequest

try {
    $result = $apiInstance->createAgentConversation($create_agent_conversation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->createAgentConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_agent_conversation_request** | [**\SpatioClient\Model\CreateAgentConversationRequest**](../Model/CreateAgentConversationRequest.md)|  | [optional] |

### Return type

[**\SpatioClient\Model\AgentConversation**](../Model/AgentConversation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createAgentMessage()`

```php
createAgentMessage($id, $create_agent_message_request): \SpatioClient\Model\AgentMessage
```

Append a message to an agent conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$create_agent_message_request = new \SpatioClient\Model\CreateAgentMessageRequest(); // \SpatioClient\Model\CreateAgentMessageRequest

try {
    $result = $apiInstance->createAgentMessage($id, $create_agent_message_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->createAgentMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **create_agent_message_request** | [**\SpatioClient\Model\CreateAgentMessageRequest**](../Model/CreateAgentMessageRequest.md)|  | |

### Return type

[**\SpatioClient\Model\AgentMessage**](../Model/AgentMessage.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAgent()`

```php
deleteAgent($id)
```

Delete an agent configuration.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteAgent($id);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->deleteAgent: ', $e->getMessage(), PHP_EOL;
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

## `executeAgentAction()`

```php
executeAgentAction($execute_action_request): \SpatioClient\Model\ExecuteActionResponse
```

Execute an action through the agent platform.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$execute_action_request = new \SpatioClient\Model\ExecuteActionRequest(); // \SpatioClient\Model\ExecuteActionRequest

try {
    $result = $apiInstance->executeAgentAction($execute_action_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->executeAgentAction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **execute_action_request** | [**\SpatioClient\Model\ExecuteActionRequest**](../Model/ExecuteActionRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ExecuteActionResponse**](../Model/ExecuteActionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAgent()`

```php
getAgent($id): \SpatioClient\Model\Agent
```

Fetch one agent configuration.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getAgent($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->getAgent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\Agent**](../Model/Agent.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAgentConversation()`

```php
getAgentConversation($id): \SpatioClient\Model\AgentConversation
```

Fetch one agent conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getAgentConversation($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->getAgentConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\AgentConversation**](../Model/AgentConversation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAgentSessionContext()`

```php
getAgentSessionContext(): \SpatioClient\Model\AgentSessionContext
```

Identity bundle for the SessionStart hook (user + org + workspace + connected accounts) so the agent doesn't fish on its first turn.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getAgentSessionContext();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->getAgentSessionContext: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\AgentSessionContext**](../Model/AgentSessionContext.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAgentConversationMessages()`

```php
listAgentConversationMessages($id): \SpatioClient\Model\AgentMessageListResponse
```

List messages on an agent conversation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->listAgentConversationMessages($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->listAgentConversationMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\AgentMessageListResponse**](../Model/AgentMessageListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAgentConversations()`

```php
listAgentConversations(): \SpatioClient\Model\AgentConversationListResponse
```

List the caller's agent-platform conversations. Distinct from `/v1/conversations` (renderer-driven sidebar persistence).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAgentConversations();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->listAgentConversations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\AgentConversationListResponse**](../Model/AgentConversationListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAgents()`

```php
listAgents(): \SpatioClient\Model\AgentListResponse
```

List the caller's agent configurations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAgents();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->listAgents: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\AgentListResponse**](../Model/AgentListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listPreconfiguredAgents()`

```php
listPreconfiguredAgents(): \SpatioClient\Model\PreconfiguredAgent[]
```

Curated featured agents (e.g. \"Claude Code\", \"Research Assistant\"). Read-only — these are surfaced by the renderer's preconfigured-picker UI.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listPreconfiguredAgents();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->listPreconfiguredAgents: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\PreconfiguredAgent[]**](../Model/PreconfiguredAgent.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateAgent()`

```php
updateAgent($id, $update_agent_request): \SpatioClient\Model\Agent
```

Update an agent configuration.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_agent_request = new \SpatioClient\Model\UpdateAgentRequest(); // \SpatioClient\Model\UpdateAgentRequest

try {
    $result = $apiInstance->updateAgent($id, $update_agent_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->updateAgent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_agent_request** | [**\SpatioClient\Model\UpdateAgentRequest**](../Model/UpdateAgentRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Agent**](../Model/Agent.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
