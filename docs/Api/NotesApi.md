# SpatioClient\NotesApi

Markdown notes, blocks, comments, and public share links.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createBlock()**](NotesApi.md#createBlock) | **POST** /v1/notes/{id}/blocks | Insert a block in a note. |
| [**createNote()**](NotesApi.md#createNote) | **POST** /v1/notes | Create a note. |
| [**createNoteComment()**](NotesApi.md#createNoteComment) | **POST** /v1/notes/{id}/comments | Create a comment or reply. |
| [**deleteBlock()**](NotesApi.md#deleteBlock) | **DELETE** /v1/notes/blocks/{id} | Delete a block. |
| [**deleteNote()**](NotesApi.md#deleteNote) | **DELETE** /v1/notes/{id} | Delete a note. |
| [**deleteNoteComment()**](NotesApi.md#deleteNoteComment) | **DELETE** /v1/notes/{id}/comments/{commentId} | Soft-delete (native) or hard-delete (provider) a comment. |
| [**disableNoteShare()**](NotesApi.md#disableNoteShare) | **DELETE** /v1/notes/{id}/share | Disable public sharing. |
| [**enableNoteShare()**](NotesApi.md#enableNoteShare) | **POST** /v1/notes/{id}/share | Enable (or update password on) public sharing. |
| [**getBlock()**](NotesApi.md#getBlock) | **GET** /v1/notes/blocks/{id} | Fetch one block. |
| [**getNote()**](NotesApi.md#getNote) | **GET** /v1/notes/{id} | Fetch one note. |
| [**getNoteComment()**](NotesApi.md#getNoteComment) | **GET** /v1/notes/{id}/comments/{commentId} | Fetch one comment. |
| [**getNoteShareSettings()**](NotesApi.md#getNoteShareSettings) | **GET** /v1/notes/{id}/share | Fetch share settings for a note. |
| [**getPublicNote()**](NotesApi.md#getPublicNote) | **GET** /public/notes/{token} | Fetch a publicly shared note. |
| [**listBlocks()**](NotesApi.md#listBlocks) | **GET** /v1/notes/{id}/blocks | List blocks under a note. |
| [**listNoteComments()**](NotesApi.md#listNoteComments) | **GET** /v1/notes/{id}/comments | List comments on a note. |
| [**listNotes()**](NotesApi.md#listNotes) | **GET** /v1/notes | List notes across connected accounts. |
| [**moveBlock()**](NotesApi.md#moveBlock) | **POST** /v1/notes/blocks/{id}/move | Reparent or reorder a block. |
| [**rotateNoteShareToken()**](NotesApi.md#rotateNoteShareToken) | **POST** /v1/notes/{id}/share/rotate | Rotate the share token, invalidating any outstanding URLs. |
| [**updateBlock()**](NotesApi.md#updateBlock) | **PATCH** /v1/notes/blocks/{id} | Update a block (partial). |
| [**updateNote()**](NotesApi.md#updateNote) | **PATCH** /v1/notes/{id} | Update a note (partial). |
| [**updateNoteComment()**](NotesApi.md#updateNoteComment) | **PATCH** /v1/notes/{id}/comments/{commentId} | Edit a comment. |
| [**workspaceCreateNote()**](NotesApi.md#workspaceCreateNote) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes |  |
| [**workspaceCreateNoteBlock()**](NotesApi.md#workspaceCreateNoteBlock) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes/{id}/blocks |  |
| [**workspaceDeleteNote()**](NotesApi.md#workspaceDeleteNote) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**workspaceDeleteNoteBlock()**](NotesApi.md#workspaceDeleteNoteBlock) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |
| [**workspaceGetNote()**](NotesApi.md#workspaceGetNote) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**workspaceGetNoteBlock()**](NotesApi.md#workspaceGetNoteBlock) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |
| [**workspaceListNoteBlocks()**](NotesApi.md#workspaceListNoteBlocks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/{id}/blocks |  |
| [**workspaceListNotes()**](NotesApi.md#workspaceListNotes) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes |  |
| [**workspaceMoveNoteBlock()**](NotesApi.md#workspaceMoveNoteBlock) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id}/move |  |
| [**workspaceUpdateNote()**](NotesApi.md#workspaceUpdateNote) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**workspaceUpdateNoteBlock()**](NotesApi.md#workspaceUpdateNoteBlock) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |


## `createBlock()`

```php
createBlock($id, $create_block_request, $account_id, $x_workspace_id): \SpatioClient\Model\Block
```

Insert a block in a note.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$create_block_request = new \SpatioClient\Model\CreateBlockRequest(); // \SpatioClient\Model\CreateBlockRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createBlock($id, $create_block_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->createBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
| **create_block_request** | [**\SpatioClient\Model\CreateBlockRequest**](../Model/CreateBlockRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Block**](../Model/Block.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createNote()`

```php
createNote($create_note_request, $account_id, $provider, $x_workspace_id): \SpatioClient\Model\Note
```

Create a note.

Creates a new note under the target account. The target is resolved in this order: `accountId` field on the body → `?accountId=` query → `provider` field on the body → `?provider=` query → the caller's single connected account (errors with `ambiguous_account` if more than one is connected and no selector is supplied).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_note_request = new \SpatioClient\Model\CreateNoteRequest(); // \SpatioClient\Model\CreateNoteRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$provider = 'provider_example'; // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createNote($create_note_request, $account_id, $provider, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->createNote: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_note_request** | [**\SpatioClient\Model\CreateNoteRequest**](../Model/CreateNoteRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **provider** | **string**| Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Note**](../Model/Note.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createNoteComment()`

```php
createNoteComment($id, $create_comment_request, $account_id, $x_workspace_id): \SpatioClient\Model\CommentMutationResponse
```

Create a comment or reply.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$create_comment_request = new \SpatioClient\Model\CreateCommentRequest(); // \SpatioClient\Model\CreateCommentRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->createNoteComment($id, $create_comment_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->createNoteComment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
| **create_comment_request** | [**\SpatioClient\Model\CreateCommentRequest**](../Model/CreateCommentRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\CommentMutationResponse**](../Model/CommentMutationResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteBlock()`

```php
deleteBlock($id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a block.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Block id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteBlock($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->deleteBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Block id. | |
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

## `deleteNote()`

```php
deleteNote($id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Delete a note.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteNote($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->deleteNote: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
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

## `deleteNoteComment()`

```php
deleteNoteComment($id, $comment_id, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Soft-delete (native) or hard-delete (provider) a comment.

Allowed for the comment author and for the note owner.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$comment_id = 'comment_id_example'; // string | Comment id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->deleteNoteComment($id, $comment_id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->deleteNoteComment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
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

## `disableNoteShare()`

```php
disableNoteShare($id, $account_id, $x_workspace_id)
```

Disable public sharing.

Owner-only. Subsequent public viewer requests 404.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $apiInstance->disableNoteShare($id, $account_id, $x_workspace_id);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->disableNoteShare: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
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

## `enableNoteShare()`

```php
enableNoteShare($id, $account_id, $x_workspace_id, $enable_share_request): \SpatioClient\Model\ShareSettings
```

Enable (or update password on) public sharing.

Owner-only. Calling with an empty body or `setPassword: false` flips the note public without changing the password. With `setPassword: true`, applies `password` (empty string clears).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$enable_share_request = new \SpatioClient\Model\EnableShareRequest(); // \SpatioClient\Model\EnableShareRequest

try {
    $result = $apiInstance->enableNoteShare($id, $account_id, $x_workspace_id, $enable_share_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->enableNoteShare: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
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

## `getBlock()`

```php
getBlock($id, $account_id, $x_workspace_id): \SpatioClient\Model\Block
```

Fetch one block.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Block id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getBlock($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->getBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Block id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Block**](../Model/Block.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getNote()`

```php
getNote($id, $account_id, $x_workspace_id): \SpatioClient\Model\Note
```

Fetch one note.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getNote($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->getNote: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Note**](../Model/Note.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getNoteComment()`

```php
getNoteComment($id, $comment_id, $account_id, $x_workspace_id): \SpatioClient\Model\CommentResponse
```

Fetch one comment.

Useful for permalink hydration when the renderer deep-links into a reply thread.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$comment_id = 'comment_id_example'; // string | Comment id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getNoteComment($id, $comment_id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->getNoteComment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
| **comment_id** | **string**| Comment id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\CommentResponse**](../Model/CommentResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getNoteShareSettings()`

```php
getNoteShareSettings($id, $account_id, $x_workspace_id): \SpatioClient\Model\ShareSettings
```

Fetch share settings for a note.

Owner-only. Returns the current public-share configuration, including the share token and computed public viewer URL when the note is currently public.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->getNoteShareSettings($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->getNoteShareSettings: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
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

## `getPublicNote()`

```php
getPublicNote($token, $password): array<string,mixed>
```

Fetch a publicly shared note.

Unauthenticated. The share token is the credential. For password-protected notes the password is supplied via the `?password=` query param; the response distinguishes \"no password supplied\" from \"wrong password\" so the viewer can render the right prompt.  Unknown tokens and disabled-share notes both return `404` to prevent token enumeration.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$token = 'token_example'; // string | Opaque public-share token.
$password = 'password_example'; // string | Optional viewer password.

try {
    $result = $apiInstance->getPublicNote($token, $password);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->getPublicNote: ', $e->getMessage(), PHP_EOL;
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

## `listBlocks()`

```php
listBlocks($id, $account_id, $x_workspace_id, $parent_id, $limit, $offset): \SpatioClient\Model\BlockListResponse
```

List blocks under a note.

Returns the block tree for a note, paginated. Block listing always targets a single account (the one that owns the note) so it does not fan out — the response is a plain `{ blocks, total }`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$parent_id = 'parent_id_example'; // string | Filter to children of this block id. Omit to list root-level blocks.
$limit = 100; // int
$offset = 0; // int

try {
    $result = $apiInstance->listBlocks($id, $account_id, $x_workspace_id, $parent_id, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->listBlocks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **parent_id** | **string**| Filter to children of this block id. Omit to list root-level blocks. | [optional] |
| **limit** | **int**|  | [optional] [default to 100] |
| **offset** | **int**|  | [optional] [default to 0] |

### Return type

[**\SpatioClient\Model\BlockListResponse**](../Model/BlockListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listNoteComments()`

```php
listNoteComments($id, $account_id, $x_workspace_id): \SpatioClient\Model\CommentListResponse
```

List comments on a note.

Returns active (non-deleted) comments. When `?accountId=` targets an external provider that supports comments (e.g. Notion), the provider is queried directly; otherwise the native store is used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->listNoteComments($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->listNoteComments: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\CommentListResponse**](../Model/CommentListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listNotes()`

```php
listNotes($account_id, $provider, $x_workspace_id, $archived, $parent_id, $tags, $limit, $offset, $sort_by, $sort_order): \SpatioClient\Model\NoteListEnvelope
```

List notes across connected accounts.

Fan-out list. Returns every note visible to the caller across every connected notes provider, paginated by `limit` / `offset`. Pass `?accountId=` or `?provider=` to scope to a single source.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$provider = 'provider_example'; // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.
$archived = false; // bool | When `true`, return archived notes instead of active ones.
$parent_id = 'parent_id_example'; // string | Filter to notes nested under this parent note id.
$tags = array('tags_example'); // string[] | Repeatable. Filter to notes carrying every tag listed.
$limit = 50; // int | Max items to return. Defaults to 50.
$offset = 0; // int | Number of items to skip.
$sort_by = 'updated_at'; // string | Sort field. Provider-dependent; the native provider supports `updated_at`, `created_at`, `title`.
$sort_order = 'desc'; // string

try {
    $result = $apiInstance->listNotes($account_id, $provider, $x_workspace_id, $archived, $parent_id, $tags, $limit, $offset, $sort_by, $sort_order);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->listNotes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **provider** | **string**| Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |
| **archived** | **bool**| When &#x60;true&#x60;, return archived notes instead of active ones. | [optional] [default to false] |
| **parent_id** | **string**| Filter to notes nested under this parent note id. | [optional] |
| **tags** | [**string[]**](../Model/string.md)| Repeatable. Filter to notes carrying every tag listed. | [optional] |
| **limit** | **int**| Max items to return. Defaults to 50. | [optional] [default to 50] |
| **offset** | **int**| Number of items to skip. | [optional] [default to 0] |
| **sort_by** | **string**| Sort field. Provider-dependent; the native provider supports &#x60;updated_at&#x60;, &#x60;created_at&#x60;, &#x60;title&#x60;. | [optional] [default to &#39;updated_at&#39;] |
| **sort_order** | **string**|  | [optional] [default to &#39;desc&#39;] |

### Return type

[**\SpatioClient\Model\NoteListEnvelope**](../Model/NoteListEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `moveBlock()`

```php
moveBlock($id, $move_block_request, $account_id, $x_workspace_id): \SpatioClient\Model\SuccessFlag
```

Reparent or reorder a block.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Block id.
$move_block_request = new \SpatioClient\Model\MoveBlockRequest(); // \SpatioClient\Model\MoveBlockRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->moveBlock($id, $move_block_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->moveBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Block id. | |
| **move_block_request** | [**\SpatioClient\Model\MoveBlockRequest**](../Model/MoveBlockRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

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

## `rotateNoteShareToken()`

```php
rotateNoteShareToken($id, $account_id, $x_workspace_id): \SpatioClient\Model\ShareSettings
```

Rotate the share token, invalidating any outstanding URLs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->rotateNoteShareToken($id, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->rotateNoteShareToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
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

## `updateBlock()`

```php
updateBlock($id, $update_block_request, $account_id, $x_workspace_id): \SpatioClient\Model\Block
```

Update a block (partial).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Block id.
$update_block_request = new \SpatioClient\Model\UpdateBlockRequest(); // \SpatioClient\Model\UpdateBlockRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateBlock($id, $update_block_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->updateBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Block id. | |
| **update_block_request** | [**\SpatioClient\Model\UpdateBlockRequest**](../Model/UpdateBlockRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Block**](../Model/Block.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateNote()`

```php
updateNote($id, $update_note_request, $account_id, $x_workspace_id): \SpatioClient\Model\Note
```

Update a note (partial).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$update_note_request = new \SpatioClient\Model\UpdateNoteRequest(); // \SpatioClient\Model\UpdateNoteRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateNote($id, $update_note_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->updateNote: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
| **update_note_request** | [**\SpatioClient\Model\UpdateNoteRequest**](../Model/UpdateNoteRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\Note**](../Model/Note.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateNoteComment()`

```php
updateNoteComment($id, $comment_id, $update_comment_request, $account_id, $x_workspace_id): \SpatioClient\Model\CommentMutationResponse
```

Edit a comment.

Only the comment author can edit. The note owner can delete via `DELETE` but cannot rewrite.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Note id.
$comment_id = 'comment_id_example'; // string | Comment id.
$update_comment_request = new \SpatioClient\Model\UpdateCommentRequest(); // \SpatioClient\Model\UpdateCommentRequest
$account_id = 'account_id_example'; // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.
$x_workspace_id = 'x_workspace_id_example'; // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.

try {
    $result = $apiInstance->updateNoteComment($id, $comment_id, $update_comment_request, $account_id, $x_workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->updateNoteComment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Note id. | |
| **comment_id** | **string**| Comment id. | |
| **update_comment_request** | [**\SpatioClient\Model\UpdateCommentRequest**](../Model/UpdateCommentRequest.md)|  | |
| **account_id** | **string**| Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account. | [optional] |
| **x_workspace_id** | **string**| Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. | [optional] |

### Return type

[**\SpatioClient\Model\CommentMutationResponse**](../Model/CommentMutationResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `workspaceCreateNote()`

```php
workspaceCreateNote($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCreateNote($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceCreateNote: ', $e->getMessage(), PHP_EOL;
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

## `workspaceCreateNoteBlock()`

```php
workspaceCreateNoteBlock($org, $workspace, $id, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
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
    $result = $apiInstance->workspaceCreateNoteBlock($org, $workspace, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceCreateNoteBlock: ', $e->getMessage(), PHP_EOL;
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

## `workspaceDeleteNote()`

```php
workspaceDeleteNote($org, $workspace, $id)
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $apiInstance->workspaceDeleteNote($org, $workspace, $id);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceDeleteNote: ', $e->getMessage(), PHP_EOL;
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

## `workspaceDeleteNoteBlock()`

```php
workspaceDeleteNoteBlock($org, $workspace, $id)
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $apiInstance->workspaceDeleteNoteBlock($org, $workspace, $id);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceDeleteNoteBlock: ', $e->getMessage(), PHP_EOL;
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

## `workspaceGetNote()`

```php
workspaceGetNote($org, $workspace, $id): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $result = $apiInstance->workspaceGetNote($org, $workspace, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceGetNote: ', $e->getMessage(), PHP_EOL;
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

## `workspaceGetNoteBlock()`

```php
workspaceGetNoteBlock($org, $workspace, $id): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $result = $apiInstance->workspaceGetNoteBlock($org, $workspace, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceGetNoteBlock: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListNoteBlocks()`

```php
workspaceListNoteBlocks($org, $workspace, $id): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$id = 'id_example'; // string

try {
    $result = $apiInstance->workspaceListNoteBlocks($org, $workspace, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceListNoteBlocks: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListNotes()`

```php
workspaceListNotes($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListNotes($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceListNotes: ', $e->getMessage(), PHP_EOL;
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

## `workspaceMoveNoteBlock()`

```php
workspaceMoveNoteBlock($org, $workspace, $id, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
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
    $result = $apiInstance->workspaceMoveNoteBlock($org, $workspace, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceMoveNoteBlock: ', $e->getMessage(), PHP_EOL;
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

## `workspaceUpdateNote()`

```php
workspaceUpdateNote($org, $workspace, $id, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
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
    $result = $apiInstance->workspaceUpdateNote($org, $workspace, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceUpdateNote: ', $e->getMessage(), PHP_EOL;
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

## `workspaceUpdateNoteBlock()`

```php
workspaceUpdateNoteBlock($org, $workspace, $id, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\NotesApi(
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
    $result = $apiInstance->workspaceUpdateNoteBlock($org, $workspace, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NotesApi->workspaceUpdateNoteBlock: ', $e->getMessage(), PHP_EOL;
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
