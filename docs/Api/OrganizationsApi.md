# SpatioClient\OrganizationsApi

Organizations, their members, and invitation flow. Organizations contain workspaces; seat counts roll up to billing.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**acceptOrganizationInvitation()**](OrganizationsApi.md#acceptOrganizationInvitation) | **POST** /v1/organizations/{org}/accept-invitation | Accept an invitation to this organization. |
| [**addOrganizationMember()**](OrganizationsApi.md#addOrganizationMember) | **POST** /v1/organizations/{org}/members | Add a member directly (skips invitation flow). |
| [**createOrganization()**](OrganizationsApi.md#createOrganization) | **POST** /v1/organizations | Create an organization. |
| [**createOrganizationConcept()**](OrganizationsApi.md#createOrganizationConcept) | **POST** /v1/organizations/{org}/concepts | Create an org-brain concept (admin+ only). |
| [**createOrganizationCustomRole()**](OrganizationsApi.md#createOrganizationCustomRole) | **POST** /v1/organizations/{org}/roles | Create a custom role (admin+ only). |
| [**createOrganizationInvitation()**](OrganizationsApi.md#createOrganizationInvitation) | **POST** /v1/organizations/{org}/invitations | Invite a user to the organization. |
| [**createOrganizationWorkspace()**](OrganizationsApi.md#createOrganizationWorkspace) | **POST** /v1/organizations/{org}/workspaces | Create a workspace inside an organization. |
| [**deleteOrganization()**](OrganizationsApi.md#deleteOrganization) | **DELETE** /v1/organizations/{org} | Delete an organization. |
| [**deleteOrganizationConcept()**](OrganizationsApi.md#deleteOrganizationConcept) | **DELETE** /v1/organizations/{org}/concepts/{slug} | Delete a concept (admin+ only). |
| [**deleteOrganizationCustomRole()**](OrganizationsApi.md#deleteOrganizationCustomRole) | **DELETE** /v1/organizations/{org}/roles/{roleId} | Delete a custom role (admin+ only). |
| [**deleteOrganizationLogo()**](OrganizationsApi.md#deleteOrganizationLogo) | **DELETE** /v1/organizations/{org}/logo | Delete the organization logo. |
| [**getOrganization()**](OrganizationsApi.md#getOrganization) | **GET** /v1/organizations/{org} | Fetch a single organization. |
| [**getOrganizationConcept()**](OrganizationsApi.md#getOrganizationConcept) | **GET** /v1/organizations/{org}/concepts/{slug} | Fetch a concept. |
| [**listMyOrganizations()**](OrganizationsApi.md#listMyOrganizations) | **GET** /v1/organizations | List the caller&#39;s organizations. |
| [**listOrganizationAuditLog()**](OrganizationsApi.md#listOrganizationAuditLog) | **GET** /v1/organizations/{org}/audit-log | Read the organization audit log (admin / billing-admin only). |
| [**listOrganizationConcepts()**](OrganizationsApi.md#listOrganizationConcepts) | **GET** /v1/organizations/{org}/concepts | List org-brain concepts (curated knowledge surfaced to agents). |
| [**listOrganizationCustomRoles()**](OrganizationsApi.md#listOrganizationCustomRoles) | **GET** /v1/organizations/{org}/roles | List custom roles defined on the organization. |
| [**listOrganizationInvitations()**](OrganizationsApi.md#listOrganizationInvitations) | **GET** /v1/organizations/{org}/invitations | List pending invitations for an organization. |
| [**listOrganizationMembers()**](OrganizationsApi.md#listOrganizationMembers) | **GET** /v1/organizations/{org}/members | List members of an organization. |
| [**listOrganizationWorkspaces()**](OrganizationsApi.md#listOrganizationWorkspaces) | **GET** /v1/organizations/{org}/workspaces | List workspaces in an organization. |
| [**removeOrganizationMember()**](OrganizationsApi.md#removeOrganizationMember) | **DELETE** /v1/organizations/{org}/members/{memberId} | Remove a member from the organization. |
| [**resendOrganizationInvitation()**](OrganizationsApi.md#resendOrganizationInvitation) | **POST** /v1/organizations/{org}/invitations/{invitationId}/resend | Revoke and reissue an invitation with a fresh token. |
| [**revokeOrganizationInvitation()**](OrganizationsApi.md#revokeOrganizationInvitation) | **DELETE** /v1/organizations/{org}/invitations/{invitationId} | Revoke a pending invitation. |
| [**updateOrganization()**](OrganizationsApi.md#updateOrganization) | **PATCH** /v1/organizations/{org} | Update organization metadata. |
| [**updateOrganizationConcept()**](OrganizationsApi.md#updateOrganizationConcept) | **PATCH** /v1/organizations/{org}/concepts/{slug} | Update a concept (admin+ only). |
| [**updateOrganizationCustomRole()**](OrganizationsApi.md#updateOrganizationCustomRole) | **PATCH** /v1/organizations/{org}/roles/{roleId} | Update a custom role (admin+ only). |
| [**updateOrganizationMember()**](OrganizationsApi.md#updateOrganizationMember) | **PATCH** /v1/organizations/{org}/members/{memberId} | Update a member&#39;s role. |
| [**uploadOrganizationLogo()**](OrganizationsApi.md#uploadOrganizationLogo) | **POST** /v1/organizations/{org}/logo | Upload (or replace) the organization logo. Multipart. |


## `acceptOrganizationInvitation()`

```php
acceptOrganizationInvitation($org, $accept_organization_invitation_request): array<string,mixed>
```

Accept an invitation to this organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$accept_organization_invitation_request = new \SpatioClient\Model\AcceptOrganizationInvitationRequest(); // \SpatioClient\Model\AcceptOrganizationInvitationRequest

try {
    $result = $apiInstance->acceptOrganizationInvitation($org, $accept_organization_invitation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->acceptOrganizationInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **accept_organization_invitation_request** | [**\SpatioClient\Model\AcceptOrganizationInvitationRequest**](../Model/AcceptOrganizationInvitationRequest.md)|  | |

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

## `addOrganizationMember()`

```php
addOrganizationMember($org, $add_organization_member_request): array<string,mixed>
```

Add a member directly (skips invitation flow).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$add_organization_member_request = new \SpatioClient\Model\AddOrganizationMemberRequest(); // \SpatioClient\Model\AddOrganizationMemberRequest

try {
    $result = $apiInstance->addOrganizationMember($org, $add_organization_member_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->addOrganizationMember: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **add_organization_member_request** | [**\SpatioClient\Model\AddOrganizationMemberRequest**](../Model/AddOrganizationMemberRequest.md)|  | |

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

## `createOrganization()`

```php
createOrganization($create_organization_request): array<string,mixed>
```

Create an organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_organization_request = new \SpatioClient\Model\CreateOrganizationRequest(); // \SpatioClient\Model\CreateOrganizationRequest

try {
    $result = $apiInstance->createOrganization($create_organization_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->createOrganization: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_organization_request** | [**\SpatioClient\Model\CreateOrganizationRequest**](../Model/CreateOrganizationRequest.md)|  | |

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

## `createOrganizationConcept()`

```php
createOrganizationConcept($org, $request_body): array<string,mixed>
```

Create an org-brain concept (admin+ only).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->createOrganizationConcept($org, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->createOrganizationConcept: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
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

## `createOrganizationCustomRole()`

```php
createOrganizationCustomRole($org, $request_body): array<string,mixed>
```

Create a custom role (admin+ only).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->createOrganizationCustomRole($org, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->createOrganizationCustomRole: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
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

## `createOrganizationInvitation()`

```php
createOrganizationInvitation($org, $create_organization_invitation_request): \SpatioClient\Model\OrganizationInvitation
```

Invite a user to the organization.

Pending invitations count toward seat cap. Free-tier callers at the cap receive a `402` with billing-upgrade payload; paid-tier auto-scales the Stripe quantity.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$create_organization_invitation_request = new \SpatioClient\Model\CreateOrganizationInvitationRequest(); // \SpatioClient\Model\CreateOrganizationInvitationRequest

try {
    $result = $apiInstance->createOrganizationInvitation($org, $create_organization_invitation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->createOrganizationInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **create_organization_invitation_request** | [**\SpatioClient\Model\CreateOrganizationInvitationRequest**](../Model/CreateOrganizationInvitationRequest.md)|  | |

### Return type

[**\SpatioClient\Model\OrganizationInvitation**](../Model/OrganizationInvitation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createOrganizationWorkspace()`

```php
createOrganizationWorkspace($org, $create_workspace_request): \SpatioClient\Model\WorkspaceEnvelope
```

Create a workspace inside an organization.

Requires the `OrgActionCreateWorkspace` action permission. Slug collisions auto-suffix (`-2`, `-3`, ...).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$create_workspace_request = new \SpatioClient\Model\CreateWorkspaceRequest(); // \SpatioClient\Model\CreateWorkspaceRequest

try {
    $result = $apiInstance->createOrganizationWorkspace($org, $create_workspace_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->createOrganizationWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
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

## `deleteOrganization()`

```php
deleteOrganization($org)
```

Delete an organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string | Organization id or slug.

try {
    $apiInstance->deleteOrganization($org);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->deleteOrganization: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**| Organization id or slug. | |

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

## `deleteOrganizationConcept()`

```php
deleteOrganizationConcept($org, $slug)
```

Delete a concept (admin+ only).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$slug = 'slug_example'; // string

try {
    $apiInstance->deleteOrganizationConcept($org, $slug);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->deleteOrganizationConcept: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **slug** | **string**|  | |

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

## `deleteOrganizationCustomRole()`

```php
deleteOrganizationCustomRole($org, $role_id)
```

Delete a custom role (admin+ only).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$role_id = 'role_id_example'; // string

try {
    $apiInstance->deleteOrganizationCustomRole($org, $role_id);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->deleteOrganizationCustomRole: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **role_id** | **string**|  | |

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

## `deleteOrganizationLogo()`

```php
deleteOrganizationLogo($org)
```

Delete the organization logo.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string

try {
    $apiInstance->deleteOrganizationLogo($org);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->deleteOrganizationLogo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |

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

## `getOrganization()`

```php
getOrganization($org): \SpatioClient\Model\OrganizationDetailLegacy
```

Fetch a single organization.

**Wire format note:** response uses PascalCase keys (`ID`, `Name`, `Slug`, ...) — distinct from the rest of the SpatioAPI's camelCase convention. Documented as-is; a future cleanup will harmonize.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string | Organization id or slug.

try {
    $result = $apiInstance->getOrganization($org);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->getOrganization: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**| Organization id or slug. | |

### Return type

[**\SpatioClient\Model\OrganizationDetailLegacy**](../Model/OrganizationDetailLegacy.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getOrganizationConcept()`

```php
getOrganizationConcept($org, $slug): array<string,mixed>
```

Fetch a concept.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$slug = 'slug_example'; // string

try {
    $result = $apiInstance->getOrganizationConcept($org, $slug);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->getOrganizationConcept: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **slug** | **string**|  | |

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

## `listMyOrganizations()`

```php
listMyOrganizations(): \SpatioClient\Model\OrganizationListResponse
```

List the caller's organizations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listMyOrganizations();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->listMyOrganizations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\OrganizationListResponse**](../Model/OrganizationListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listOrganizationAuditLog()`

```php
listOrganizationAuditLog($org, $limit, $cursor): array<string,mixed>
```

Read the organization audit log (admin / billing-admin only).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$limit = 56; // int
$cursor = 'cursor_example'; // string

try {
    $result = $apiInstance->listOrganizationAuditLog($org, $limit, $cursor);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->listOrganizationAuditLog: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **limit** | **int**|  | [optional] |
| **cursor** | **string**|  | [optional] |

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

## `listOrganizationConcepts()`

```php
listOrganizationConcepts($org): array<string,mixed>
```

List org-brain concepts (curated knowledge surfaced to agents).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string

try {
    $result = $apiInstance->listOrganizationConcepts($org);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->listOrganizationConcepts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |

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

## `listOrganizationCustomRoles()`

```php
listOrganizationCustomRoles($org): array<string,mixed>
```

List custom roles defined on the organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string

try {
    $result = $apiInstance->listOrganizationCustomRoles($org);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->listOrganizationCustomRoles: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |

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

## `listOrganizationInvitations()`

```php
listOrganizationInvitations($org): \SpatioClient\Model\OrganizationInvitationListResponse
```

List pending invitations for an organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string

try {
    $result = $apiInstance->listOrganizationInvitations($org);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->listOrganizationInvitations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |

### Return type

[**\SpatioClient\Model\OrganizationInvitationListResponse**](../Model/OrganizationInvitationListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listOrganizationMembers()`

```php
listOrganizationMembers($org): \SpatioClient\Model\OrganizationMemberListResponse
```

List members of an organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string

try {
    $result = $apiInstance->listOrganizationMembers($org);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->listOrganizationMembers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |

### Return type

[**\SpatioClient\Model\OrganizationMemberListResponse**](../Model/OrganizationMemberListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listOrganizationWorkspaces()`

```php
listOrganizationWorkspaces($org): \SpatioClient\Model\WorkspaceListResponse
```

List workspaces in an organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string

try {
    $result = $apiInstance->listOrganizationWorkspaces($org);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->listOrganizationWorkspaces: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |

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

## `removeOrganizationMember()`

```php
removeOrganizationMember($org, $member_id)
```

Remove a member from the organization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$member_id = 'member_id_example'; // string

try {
    $apiInstance->removeOrganizationMember($org, $member_id);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->removeOrganizationMember: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
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

## `resendOrganizationInvitation()`

```php
resendOrganizationInvitation($org, $invitation_id): \SpatioClient\Model\OrganizationInvitation
```

Revoke and reissue an invitation with a fresh token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$invitation_id = 'invitation_id_example'; // string

try {
    $result = $apiInstance->resendOrganizationInvitation($org, $invitation_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->resendOrganizationInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **invitation_id** | **string**|  | |

### Return type

[**\SpatioClient\Model\OrganizationInvitation**](../Model/OrganizationInvitation.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokeOrganizationInvitation()`

```php
revokeOrganizationInvitation($org, $invitation_id)
```

Revoke a pending invitation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$invitation_id = 'invitation_id_example'; // string

try {
    $apiInstance->revokeOrganizationInvitation($org, $invitation_id);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->revokeOrganizationInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
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

## `updateOrganization()`

```php
updateOrganization($org, $update_organization_request): array<string,mixed>
```

Update organization metadata.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string | Organization id or slug.
$update_organization_request = new \SpatioClient\Model\UpdateOrganizationRequest(); // \SpatioClient\Model\UpdateOrganizationRequest

try {
    $result = $apiInstance->updateOrganization($org, $update_organization_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->updateOrganization: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**| Organization id or slug. | |
| **update_organization_request** | [**\SpatioClient\Model\UpdateOrganizationRequest**](../Model/UpdateOrganizationRequest.md)|  | |

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

## `updateOrganizationConcept()`

```php
updateOrganizationConcept($org, $slug, $request_body): array<string,mixed>
```

Update a concept (admin+ only).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$slug = 'slug_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->updateOrganizationConcept($org, $slug, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->updateOrganizationConcept: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **slug** | **string**|  | |
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

## `updateOrganizationCustomRole()`

```php
updateOrganizationCustomRole($org, $role_id, $request_body): array<string,mixed>
```

Update a custom role (admin+ only).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$role_id = 'role_id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->updateOrganizationCustomRole($org, $role_id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->updateOrganizationCustomRole: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **role_id** | **string**|  | |
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

## `updateOrganizationMember()`

```php
updateOrganizationMember($org, $member_id, $update_organization_member_request): array<string,mixed>
```

Update a member's role.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$member_id = 'member_id_example'; // string
$update_organization_member_request = new \SpatioClient\Model\UpdateOrganizationMemberRequest(); // \SpatioClient\Model\UpdateOrganizationMemberRequest

try {
    $result = $apiInstance->updateOrganizationMember($org, $member_id, $update_organization_member_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->updateOrganizationMember: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **member_id** | **string**|  | |
| **update_organization_member_request** | [**\SpatioClient\Model\UpdateOrganizationMemberRequest**](../Model/UpdateOrganizationMemberRequest.md)|  | |

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

## `uploadOrganizationLogo()`

```php
uploadOrganizationLogo($org, $file): array<string,mixed>
```

Upload (or replace) the organization logo. Multipart.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\OrganizationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$file = '/path/to/file.txt'; // \SplFileObject

try {
    $result = $apiInstance->uploadOrganizationLogo($org, $file);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrganizationsApi->uploadOrganizationLogo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **file** | **\SplFileObject****\SplFileObject**|  | [optional] |

### Return type

**array<string,mixed>**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
