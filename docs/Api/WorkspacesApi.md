# SpatioClient\WorkspacesApi

Workspaces and their members. Workspaces live inside organizations and are the unit of resource scoping for Personal Access Tokens.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**acceptWorkspaceInvitation()**](WorkspacesApi.md#acceptWorkspaceInvitation) | **POST** /v1/invitations/{token}/accept | Accept a workspace invitation by token. The signed-in user&#39;s email must match the invitation. Organization-token accept lives at &#x60;POST /v1/organizations/{org}/accept-invitation&#x60;. |
| [**addWorkspaceMember()**](WorkspacesApi.md#addWorkspaceMember) | **POST** /v1/workspaces/{workspaceId}/members | Add a member directly (skips invitation flow). |
| [**createWorkspace()**](WorkspacesApi.md#createWorkspace) | **POST** /v1/workspaces | Create a workspace. Requires &#x60;organizationId&#x60; in the body — bare \&quot;personal\&quot; workspaces aren&#39;t supported on the public API. |
| [**createWorkspaceInvitation()**](WorkspacesApi.md#createWorkspaceInvitation) | **POST** /v1/workspaces/{workspaceId}/invitations | Invite a user to a workspace. |
| [**getPublicInvitation()**](WorkspacesApi.md#getPublicInvitation) | **GET** /invitations/{token} | Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in. |
| [**getWorkspace()**](WorkspacesApi.md#getWorkspace) | **GET** /v1/workspaces/{workspaceId} | Fetch a single workspace by id. |
| [**listMyWorkspaces()**](WorkspacesApi.md#listMyWorkspaces) | **GET** /v1/workspaces | List the caller&#39;s workspaces (across organizations). |
| [**listWorkspaceInvitations()**](WorkspacesApi.md#listWorkspaceInvitations) | **GET** /v1/workspaces/{workspaceId}/invitations | List pending workspace invitations. |
| [**listWorkspaceMembers()**](WorkspacesApi.md#listWorkspaceMembers) | **GET** /v1/workspaces/{workspaceId}/members | List members of a workspace. |
| [**removeWorkspaceMember()**](WorkspacesApi.md#removeWorkspaceMember) | **DELETE** /v1/workspaces/{workspaceId}/members/{memberId} | Remove a member from the workspace. |
| [**revokeWorkspaceInvitation()**](WorkspacesApi.md#revokeWorkspaceInvitation) | **DELETE** /v1/workspaces/{workspaceId}/invitations/{invitationId} | Revoke a pending workspace invitation. |
| [**updateWorkspace()**](WorkspacesApi.md#updateWorkspace) | **PATCH** /v1/workspaces/{workspaceId} | Update workspace metadata. |
| [**updateWorkspaceMember()**](WorkspacesApi.md#updateWorkspaceMember) | **PATCH** /v1/workspaces/{workspaceId}/members/{memberId} | Update a member&#39;s role. |


## `acceptWorkspaceInvitation()`

```php
acceptWorkspaceInvitation($token): array<string,mixed>
```

Accept a workspace invitation by token. The signed-in user's email must match the invitation. Organization-token accept lives at `POST /v1/organizations/{org}/accept-invitation`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$token = 'token_example'; // string

try {
    $result = $apiInstance->acceptWorkspaceInvitation($token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->acceptWorkspaceInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token** | **string**|  | |

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

## `addWorkspaceMember()`

```php
addWorkspaceMember($workspace_id, $add_workspace_member_request): array<string,mixed>
```

Add a member directly (skips invitation flow).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string
$add_workspace_member_request = new \SpatioClient\Model\AddWorkspaceMemberRequest(); // \SpatioClient\Model\AddWorkspaceMemberRequest

try {
    $result = $apiInstance->addWorkspaceMember($workspace_id, $add_workspace_member_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->addWorkspaceMember: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |
| **add_workspace_member_request** | [**\SpatioClient\Model\AddWorkspaceMemberRequest**](../Model/AddWorkspaceMemberRequest.md)|  | |

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

## `createWorkspace()`

```php
createWorkspace($create_workspace_request): \SpatioClient\Model\WorkspaceEnvelope
```

Create a workspace. Requires `organizationId` in the body — bare \"personal\" workspaces aren't supported on the public API.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_workspace_request = new \SpatioClient\Model\CreateWorkspaceRequest(); // \SpatioClient\Model\CreateWorkspaceRequest

try {
    $result = $apiInstance->createWorkspace($create_workspace_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->createWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_workspace_request** | [**\SpatioClient\Model\CreateWorkspaceRequest**](../Model/CreateWorkspaceRequest.md)|  | |

### Return type

[**\SpatioClient\Model\WorkspaceEnvelope**](../Model/WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createWorkspaceInvitation()`

```php
createWorkspaceInvitation($workspace_id, $create_workspace_invitation_request): \SpatioClient\Model\WorkspaceInvitation
```

Invite a user to a workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string
$create_workspace_invitation_request = new \SpatioClient\Model\CreateWorkspaceInvitationRequest(); // \SpatioClient\Model\CreateWorkspaceInvitationRequest

try {
    $result = $apiInstance->createWorkspaceInvitation($workspace_id, $create_workspace_invitation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->createWorkspaceInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |
| **create_workspace_invitation_request** | [**\SpatioClient\Model\CreateWorkspaceInvitationRequest**](../Model/CreateWorkspaceInvitationRequest.md)|  | |

### Return type

[**\SpatioClient\Model\WorkspaceInvitation**](../Model/WorkspaceInvitation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPublicInvitation()`

```php
getPublicInvitation($token): \SpatioClient\Model\PublicInvitationPayload
```

Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$token = 'token_example'; // string

try {
    $result = $apiInstance->getPublicInvitation($token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->getPublicInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token** | **string**|  | |

### Return type

[**\SpatioClient\Model\PublicInvitationPayload**](../Model/PublicInvitationPayload.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWorkspace()`

```php
getWorkspace($workspace_id): \SpatioClient\Model\WorkspaceEnvelope
```

Fetch a single workspace by id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string

try {
    $result = $apiInstance->getWorkspace($workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->getWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |

### Return type

[**\SpatioClient\Model\WorkspaceEnvelope**](../Model/WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listMyWorkspaces()`

```php
listMyWorkspaces(): \SpatioClient\Model\WorkspaceListResponse
```

List the caller's workspaces (across organizations).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listMyWorkspaces();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listMyWorkspaces: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\WorkspaceListResponse**](../Model/WorkspaceListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listWorkspaceInvitations()`

```php
listWorkspaceInvitations($workspace_id): \SpatioClient\Model\WorkspaceInvitationListResponse
```

List pending workspace invitations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string

try {
    $result = $apiInstance->listWorkspaceInvitations($workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listWorkspaceInvitations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |

### Return type

[**\SpatioClient\Model\WorkspaceInvitationListResponse**](../Model/WorkspaceInvitationListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listWorkspaceMembers()`

```php
listWorkspaceMembers($workspace_id): \SpatioClient\Model\WorkspaceMemberListResponse
```

List members of a workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string

try {
    $result = $apiInstance->listWorkspaceMembers($workspace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listWorkspaceMembers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |

### Return type

[**\SpatioClient\Model\WorkspaceMemberListResponse**](../Model/WorkspaceMemberListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `removeWorkspaceMember()`

```php
removeWorkspaceMember($workspace_id, $member_id)
```

Remove a member from the workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string
$member_id = 'member_id_example'; // string

try {
    $apiInstance->removeWorkspaceMember($workspace_id, $member_id);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->removeWorkspaceMember: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |
| **member_id** | **string**|  | |

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

## `revokeWorkspaceInvitation()`

```php
revokeWorkspaceInvitation($workspace_id, $invitation_id)
```

Revoke a pending workspace invitation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string
$invitation_id = 'invitation_id_example'; // string

try {
    $apiInstance->revokeWorkspaceInvitation($workspace_id, $invitation_id);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->revokeWorkspaceInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |
| **invitation_id** | **string**|  | |

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

## `updateWorkspace()`

```php
updateWorkspace($workspace_id, $update_workspace_request): \SpatioClient\Model\WorkspaceEnvelope
```

Update workspace metadata.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string
$update_workspace_request = new \SpatioClient\Model\UpdateWorkspaceRequest(); // \SpatioClient\Model\UpdateWorkspaceRequest

try {
    $result = $apiInstance->updateWorkspace($workspace_id, $update_workspace_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->updateWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |
| **update_workspace_request** | [**\SpatioClient\Model\UpdateWorkspaceRequest**](../Model/UpdateWorkspaceRequest.md)|  | |

### Return type

[**\SpatioClient\Model\WorkspaceEnvelope**](../Model/WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateWorkspaceMember()`

```php
updateWorkspaceMember($workspace_id, $member_id, $update_workspace_member_request): array<string,mixed>
```

Update a member's role.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_id = 'workspace_id_example'; // string
$member_id = 'member_id_example'; // string
$update_workspace_member_request = new \SpatioClient\Model\UpdateWorkspaceMemberRequest(); // \SpatioClient\Model\UpdateWorkspaceMemberRequest

try {
    $result = $apiInstance->updateWorkspaceMember($workspace_id, $member_id, $update_workspace_member_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->updateWorkspaceMember: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_id** | **string**|  | |
| **member_id** | **string**|  | |
| **update_workspace_member_request** | [**\SpatioClient\Model\UpdateWorkspaceMemberRequest**](../Model/UpdateWorkspaceMemberRequest.md)|  | |

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
