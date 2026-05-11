# SpatioClient\TasksApi

To-dos, reminders, and issues with comments + bulk operations.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**bulkDeleteTasks()**](TasksApi.md#bulkDeleteTasks) | **POST** /v1/tasks/delete | Delete multiple tasks in one call. |
| [**bulkUpdateTasks()**](TasksApi.md#bulkUpdateTasks) | **POST** /v1/tasks/bulk-update | Apply the same update to multiple tasks. |
| [**completeTask()**](TasksApi.md#completeTask) | **POST** /v1/tasks/{id}/complete | Mark a task complete. |
| [**createTask()**](TasksApi.md#createTask) | **POST** /v1/tasks | Create a task. |
| [**createTaskComment()**](TasksApi.md#createTaskComment) | **POST** /v1/tasks/{id}/comments | Create a comment. |
| [**deleteTask()**](TasksApi.md#deleteTask) | **DELETE** /v1/tasks/{id} | Delete a task. |
| [**deleteTaskComment()**](TasksApi.md#deleteTaskComment) | **DELETE** /v1/tasks/{id}/comments/{commentId} | Delete a task comment. |
| [**getTask()**](TasksApi.md#getTask) | **GET** /v1/tasks/{id} | Fetch one task. |
| [**listTaskComments()**](TasksApi.md#listTaskComments) | **GET** /v1/tasks/{id}/comments | List comments on a task. |
| [**listTaskProviders()**](TasksApi.md#listTaskProviders) | **GET** /v1/tasks/providers | List supported task providers. |
| [**listTasks()**](TasksApi.md#listTasks) | **GET** /v1/tasks | List tasks across connected accounts. |
| [**updateTask()**](TasksApi.md#updateTask) | **PATCH** /v1/tasks/{id} | Update a task (partial). |
| [**updateTaskComment()**](TasksApi.md#updateTaskComment) | **PATCH** /v1/tasks/{id}/comments/{commentId} | Edit a task comment. |
| [**workspaceCompleteTask()**](TasksApi.md#workspaceCompleteTask) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id}/complete |  |
| [**workspaceCompleteTaskAlias()**](TasksApi.md#workspaceCompleteTaskAlias) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/complete/task | Renderer-compat alias for /tasks/{id}/complete. |
| [**workspaceCreateTask()**](TasksApi.md#workspaceCreateTask) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks |  |
| [**workspaceCreateTaskAlias()**](TasksApi.md#workspaceCreateTaskAlias) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/task | Renderer-compat alias for POST /tasks. |
| [**workspaceDeleteTask()**](TasksApi.md#workspaceDeleteTask) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspaceGetTask()**](TasksApi.md#workspaceGetTask) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspaceListTaskProviders()**](TasksApi.md#workspaceListTaskProviders) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/providers |  |
| [**workspaceListTasks()**](TasksApi.md#workspaceListTasks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks |  |
| [**workspaceListTasksAlias()**](TasksApi.md#workspaceListTasksAlias) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/tasks | Renderer-compat alias for /tasks. |
| [**workspaceUpdateTask()**](TasksApi.md#workspaceUpdateTask) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspaceUpdateTaskAlias()**](TasksApi.md#workspaceUpdateTaskAlias) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/tasks/task/{id} | Renderer-compat alias for PATCH /tasks/{id}. |


## `bulkDeleteTasks()`

```php
bulkDeleteTasks($bulk_delete_tasks_request): \SpatioClient\Model\BulkDeleteTasksResponse
```

Delete multiple tasks in one call.

Replaces the legacy BFF that looped DELETE /v1/tasks/:id. Per-id errors are collected in `failed` rather than failing the whole call — partial success is the norm.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$bulk_delete_tasks_request = new \SpatioClient\Model\BulkDeleteTasksRequest(); // \SpatioClient\Model\BulkDeleteTasksRequest

try {
    $result = $apiInstance->bulkDeleteTasks($bulk_delete_tasks_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->bulkDeleteTasks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **bulk_delete_tasks_request** | [**\SpatioClient\Model\BulkDeleteTasksRequest**](../Model/BulkDeleteTasksRequest.md)|  | |

### Return type

[**\SpatioClient\Model\BulkDeleteTasksResponse**](../Model/BulkDeleteTasksResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `bulkUpdateTasks()`

```php
bulkUpdateTasks($bulk_update_tasks_request): \SpatioClient\Model\BulkUpdateTasksResponse
```

Apply the same update to multiple tasks.

Same `updates` payload applied to every id in `taskIds`. As with bulk delete, per-id failures collect in `failed`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$bulk_update_tasks_request = new \SpatioClient\Model\BulkUpdateTasksRequest(); // \SpatioClient\Model\BulkUpdateTasksRequest

try {
    $result = $apiInstance->bulkUpdateTasks($bulk_update_tasks_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->bulkUpdateTasks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **bulk_update_tasks_request** | [**\SpatioClient\Model\BulkUpdateTasksRequest**](../Model/BulkUpdateTasksRequest.md)|  | |

### Return type

[**\SpatioClient\Model\BulkUpdateTasksResponse**](../Model/BulkUpdateTasksResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `completeTask()`

```php
completeTask($id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Mark a task complete.

Idempotent — completing an already-completed task is a no-op that still returns success. The legacy `POST /v1/tasks/complete/task` endpoint accepts the same operation with the task id in the JSON body instead of the URL; that variant is a renderer-compat shim and is not modeled in the spec.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Task id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->completeTask($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->completeTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Task id. | |
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

## `createTask()`

```php
createTask($create_task_request, $account_id, $provider, $x_workspace_id): \SpatioClient\Model\Task
```

Create a task.

Creates a new task under the target account. Target resolution mirrors `POST /v1/notes`: body `accountId` → `?accountId=` → body `provider` → `?provider=` → caller's single connected account (errors `ambiguous_account` if more than one and no selector).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_task_request = new \SpatioClient\Model\CreateTaskRequest(); // \SpatioClient\Model\CreateTaskRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$provider = 'provider_example'; // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createTask($create_task_request, $account_id, $provider, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->createTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_task_request** | [**\SpatioClient\Model\CreateTaskRequest**](../Model/CreateTaskRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **provider** | **string**| Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Task**](../Model/Task.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createTaskComment()`

```php
createTaskComment($id, $task_comment_request, $account_id, $x_workspace_id): \SpatioClient\Model\TaskCommentMutationResponse
```

Create a comment.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Task id.
$task_comment_request = new \SpatioClient\Model\TaskCommentRequest(); // \SpatioClient\Model\TaskCommentRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createTaskComment($id, $task_comment_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->createTaskComment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Task id. | |
| **task_comment_request** | [**\SpatioClient\Model\TaskCommentRequest**](../Model/TaskCommentRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\TaskCommentMutationResponse**](../Model/TaskCommentMutationResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteTask()`

```php
deleteTask($id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a task.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Task id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteTask($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->deleteTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Task id. | |
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

## `deleteTaskComment()`

```php
deleteTaskComment($id, $comment_id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a task comment.

Allowed for the comment author and (for native comments) for the task owner.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Task id.
$comment_id = 'comment_id_example'; // string | Comment id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteTaskComment($id, $comment_id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->deleteTaskComment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Task id. | |
| **comment_id** | **string**| Comment id. | |
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

## `getTask()`

```php
getTask($id, $account_id, $x_workspace_id): \SpatioClient\Model\Task
```

Fetch one task.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Task id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getTask($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->getTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Task id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Task**](../Model/Task.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTaskComments()`

```php
listTaskComments($id, $account_id, $x_workspace_id): \SpatioClient\Model\TaskCommentList
```

List comments on a task.

Returns active comments. When `?accountId=` targets an external provider that supports comments (e.g. Linear), the provider is queried directly; otherwise the native `TaskComment` table is used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Task id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->listTaskComments($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->listTaskComments: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Task id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\TaskCommentList**](../Model/TaskCommentList.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTaskProviders()`

```php
listTaskProviders(): \SpatioClient\Model\TaskProvidersInfo
```

List supported task providers.

Returns the registered task-provider ids and the platform's own metadata. Useful for clients that need to render provider-specific UI (icons, capability flags) before committing to a particular `provider`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listTaskProviders();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->listTaskProviders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\TaskProvidersInfo**](../Model/TaskProvidersInfo.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTasks()`

```php
listTasks($account_id, $provider, $x_workspace_id, $completed, $labels, $parent_task_id, $type, $source_platform, $source_id, $limit, $offset): \SpatioClient\Model\TaskListEnvelope
```

List tasks across connected accounts.

Fan-out list. Returns every task visible to the caller across every connected tasks provider. Pass `?accountId=` or `?provider=` to scope to a single source.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$provider = 'provider_example'; // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$completed = false; // bool | Include completed tasks. Default `false` (active tasks only).
$labels = array('labels_example'); // string[] | Repeatable. Filter to tasks carrying every label listed.
$parent_task_id = 'parent_task_id_example'; // string | Filter to subtasks of this parent.
$type = 'type_example'; // string | Discriminator filter (`todo`, `reminder`, `issue`).
$source_platform = 'source_platform_example'; // string | Filter to tasks linked to a given source platform.
$source_id = 'source_id_example'; // string | Filter to tasks linked to a specific source artifact id. Pair with `sourcePlatform` for an exact match.
$limit = 50; // int
$offset = 0; // int

try {
    $result = $apiInstance->listTasks($account_id, $provider, $x_workspace_id, $completed, $labels, $parent_task_id, $type, $source_platform, $source_id, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->listTasks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **provider** | **string**| Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **completed** | **bool**| Include completed tasks. Default &#x60;false&#x60; (active tasks only). | [optional] [default to false] |
| **labels** | [**string[]**](../Model/string.md)| Repeatable. Filter to tasks carrying every label listed. | [optional] |
| **parent_task_id** | **string**| Filter to subtasks of this parent. | [optional] |
| **type** | **string**| Discriminator filter (&#x60;todo&#x60;, &#x60;reminder&#x60;, &#x60;issue&#x60;). | [optional] |
| **source_platform** | **string**| Filter to tasks linked to a given source platform. | [optional] |
| **source_id** | **string**| Filter to tasks linked to a specific source artifact id. Pair with &#x60;sourcePlatform&#x60; for an exact match. | [optional] |
| **limit** | **int**|  | [optional] [default to 50] |
| **offset** | **int**|  | [optional] [default to 0] |

### Return type

[**\SpatioClient\Model\TaskListEnvelope**](../Model/TaskListEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateTask()`

```php
updateTask($id, $update_task_request, $account_id, $x_workspace_id): \SpatioClient\Model\Task
```

Update a task (partial).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Task id.
$update_task_request = new \SpatioClient\Model\UpdateTaskRequest(); // \SpatioClient\Model\UpdateTaskRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateTask($id, $update_task_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->updateTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Task id. | |
| **update_task_request** | [**\SpatioClient\Model\UpdateTaskRequest**](../Model/UpdateTaskRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Task**](../Model/Task.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateTaskComment()`

```php
updateTaskComment($id, $comment_id, $task_comment_request, $account_id, $x_workspace_id): \SpatioClient\Model\TaskCommentMutationResponse
```

Edit a task comment.

Only the comment author can edit.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Task id.
$comment_id = 'comment_id_example'; // string | Comment id.
$task_comment_request = new \SpatioClient\Model\TaskCommentRequest(); // \SpatioClient\Model\TaskCommentRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateTaskComment($id, $comment_id, $task_comment_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->updateTaskComment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Task id. | |
| **comment_id** | **string**| Comment id. | |
| **task_comment_request** | [**\SpatioClient\Model\TaskCommentRequest**](../Model/TaskCommentRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\TaskCommentMutationResponse**](../Model/TaskCommentMutationResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `workspaceCompleteTask()`

```php
workspaceCompleteTask($org, $workspace, $id): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $result = $apiInstance->workspaceCompleteTask($org, $workspace, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceCompleteTask: ', $e->getMessage(), PHP_EOL;
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

## `workspaceCompleteTaskAlias()`

```php
workspaceCompleteTaskAlias($org, $workspace, $request_body): array<string,mixed>
```

Renderer-compat alias for /tasks/{id}/complete.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCompleteTaskAlias($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceCompleteTaskAlias: ', $e->getMessage(), PHP_EOL;
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

## `workspaceCreateTask()`

```php
workspaceCreateTask($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCreateTask($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceCreateTask: ', $e->getMessage(), PHP_EOL;
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

## `workspaceCreateTaskAlias()`

```php
workspaceCreateTaskAlias($org, $workspace, $request_body): array<string,mixed>
```

Renderer-compat alias for POST /tasks.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCreateTaskAlias($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceCreateTaskAlias: ', $e->getMessage(), PHP_EOL;
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

## `workspaceDeleteTask()`

```php
workspaceDeleteTask($org, $workspace, $id)
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $apiInstance->workspaceDeleteTask($org, $workspace, $id);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceDeleteTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
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

## `workspaceGetTask()`

```php
workspaceGetTask($org, $workspace, $id): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $result = $apiInstance->workspaceGetTask($org, $workspace, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceGetTask: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListTaskProviders()`

```php
workspaceListTaskProviders($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListTaskProviders($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceListTaskProviders: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListTasks()`

```php
workspaceListTasks($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListTasks($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceListTasks: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListTasksAlias()`

```php
workspaceListTasksAlias($org, $workspace): array<string,mixed>
```

Renderer-compat alias for /tasks.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListTasksAlias($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceListTasksAlias: ', $e->getMessage(), PHP_EOL;
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

## `workspaceUpdateTask()`

```php
workspaceUpdateTask($org, $workspace, $id, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
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
    $result = $apiInstance->workspaceUpdateTask($org, $workspace, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceUpdateTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **id** | **string**|  | |
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

## `workspaceUpdateTaskAlias()`

```php
workspaceUpdateTaskAlias($org, $workspace, $id, $request_body): array<string,mixed>
```

Renderer-compat alias for PATCH /tasks/{id}.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\TasksApi(
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
    $result = $apiInstance->workspaceUpdateTaskAlias($org, $workspace, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TasksApi->workspaceUpdateTaskAlias: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **id** | **string**|  | |
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
