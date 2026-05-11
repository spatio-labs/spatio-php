# SpatioClient\ContactsApi

Cross-provider contacts and org-scoped contact categories.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**assignContactCategory()**](ContactsApi.md#assignContactCategory) | **POST** /v1/contacts/{id}/categories | Assign a category to a contact. |
| [**createContact()**](ContactsApi.md#createContact) | **POST** /v1/contacts | Create a contact. |
| [**createContactCategory()**](ContactsApi.md#createContactCategory) | **POST** /v1/contacts/categories | Create a contact category. |
| [**deleteContact()**](ContactsApi.md#deleteContact) | **DELETE** /v1/contacts/{id} | Delete a contact. |
| [**deleteContactCategory()**](ContactsApi.md#deleteContactCategory) | **DELETE** /v1/contacts/categories/{id} | Delete a category. |
| [**getContact()**](ContactsApi.md#getContact) | **GET** /v1/contacts/{id} | Fetch a contact. |
| [**listContactCategories()**](ContactsApi.md#listContactCategories) | **GET** /v1/contacts/categories | List contact categories. Requires &#x60;organization_id&#x60; query param. |
| [**listContactProviders()**](ContactsApi.md#listContactProviders) | **GET** /v1/contacts/providers | List supported contact providers (native + OAuth-connected). |
| [**listContacts()**](ContactsApi.md#listContacts) | **GET** /v1/contacts | List the caller&#39;s contacts (across providers). |
| [**unassignContactCategory()**](ContactsApi.md#unassignContactCategory) | **DELETE** /v1/contacts/{id}/categories/{categoryId} | Remove a category from a contact. |
| [**updateContact()**](ContactsApi.md#updateContact) | **PATCH** /v1/contacts/{id} | Update a contact. |
| [**updateContactCategory()**](ContactsApi.md#updateContactCategory) | **PATCH** /v1/contacts/categories/{id} | Update a category. |


## `assignContactCategory()`

```php
assignContactCategory($id, $assign_contact_category_request)
```

Assign a category to a contact.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$assign_contact_category_request = new \SpatioClient\Model\AssignContactCategoryRequest(); // \SpatioClient\Model\AssignContactCategoryRequest

try {
    $apiInstance->assignContactCategory($id, $assign_contact_category_request);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->assignContactCategory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **assign_contact_category_request** | [**\SpatioClient\Model\AssignContactCategoryRequest**](../Model/AssignContactCategoryRequest.md)|  | |

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

## `createContact()`

```php
createContact($create_contact_request): \SpatioClient\Model\Contact
```

Create a contact.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_contact_request = new \SpatioClient\Model\CreateContactRequest(); // \SpatioClient\Model\CreateContactRequest

try {
    $result = $apiInstance->createContact($create_contact_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->createContact: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_contact_request** | [**\SpatioClient\Model\CreateContactRequest**](../Model/CreateContactRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Contact**](../Model/Contact.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createContactCategory()`

```php
createContactCategory($create_contact_category_request): \SpatioClient\Model\ContactCategory
```

Create a contact category.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_contact_category_request = new \SpatioClient\Model\CreateContactCategoryRequest(); // \SpatioClient\Model\CreateContactCategoryRequest

try {
    $result = $apiInstance->createContactCategory($create_contact_category_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->createContactCategory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_contact_category_request** | [**\SpatioClient\Model\CreateContactCategoryRequest**](../Model/CreateContactCategoryRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ContactCategory**](../Model/ContactCategory.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteContact()`

```php
deleteContact($id)
```

Delete a contact.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteContact($id);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->deleteContact: ', $e->getMessage(), PHP_EOL;
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

## `deleteContactCategory()`

```php
deleteContactCategory($id)
```

Delete a category.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteContactCategory($id);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->deleteContactCategory: ', $e->getMessage(), PHP_EOL;
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

## `getContact()`

```php
getContact($id): \SpatioClient\Model\Contact
```

Fetch a contact.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getContact($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->getContact: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\SpatioClient\Model\Contact**](../Model/Contact.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listContactCategories()`

```php
listContactCategories($organization_id): \SpatioClient\Model\ContactCategoryListResponse
```

List contact categories. Requires `organization_id` query param.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$organization_id = 'organization_id_example'; // string

try {
    $result = $apiInstance->listContactCategories($organization_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->listContactCategories: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **organization_id** | **string**|  | |

### Return type

[**\SpatioClient\Model\ContactCategoryListResponse**](../Model/ContactCategoryListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listContactProviders()`

```php
listContactProviders(): \SpatioClient\Model\ContactProviderListResponse
```

List supported contact providers (native + OAuth-connected).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listContactProviders();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->listContactProviders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\SpatioClient\Model\ContactProviderListResponse**](../Model/ContactProviderListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listContacts()`

```php
listContacts($limit, $provider, $search): \SpatioClient\Model\ContactListResponse
```

List the caller's contacts (across providers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$limit = 56; // int
$provider = 'provider_example'; // string
$search = 'search_example'; // string

try {
    $result = $apiInstance->listContacts($limit, $provider, $search);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->listContacts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **limit** | **int**|  | [optional] |
| **provider** | **string**|  | [optional] |
| **search** | **string**|  | [optional] |

### Return type

[**\SpatioClient\Model\ContactListResponse**](../Model/ContactListResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `unassignContactCategory()`

```php
unassignContactCategory($id, $category_id)
```

Remove a category from a contact.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$category_id = 'category_id_example'; // string

try {
    $apiInstance->unassignContactCategory($id, $category_id);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->unassignContactCategory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **category_id** | **string**|  | |

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

## `updateContact()`

```php
updateContact($id, $update_contact_request): \SpatioClient\Model\Contact
```

Update a contact.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_contact_request = new \SpatioClient\Model\UpdateContactRequest(); // \SpatioClient\Model\UpdateContactRequest

try {
    $result = $apiInstance->updateContact($id, $update_contact_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->updateContact: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_contact_request** | [**\SpatioClient\Model\UpdateContactRequest**](../Model/UpdateContactRequest.md)|  | |

### Return type

[**\SpatioClient\Model\Contact**](../Model/Contact.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateContactCategory()`

```php
updateContactCategory($id, $update_contact_category_request): \SpatioClient\Model\ContactCategory
```

Update a category.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_contact_category_request = new \SpatioClient\Model\UpdateContactCategoryRequest(); // \SpatioClient\Model\UpdateContactCategoryRequest

try {
    $result = $apiInstance->updateContactCategory($id, $update_contact_category_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->updateContactCategory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_contact_category_request** | [**\SpatioClient\Model\UpdateContactCategoryRequest**](../Model/UpdateContactCategoryRequest.md)|  | |

### Return type

[**\SpatioClient\Model\ContactCategory**](../Model/ContactCategory.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
