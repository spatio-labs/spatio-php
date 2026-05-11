# SpatioClient\RepoApi

Code repository platform — native Spatio repos plus connected providers (GitHub, GitLab, …). Repos, pull requests, issues, branches, commits, workflows.

All URIs are relative to https://api.spatio.app, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createRepoBranch()**](RepoApi.md#createRepoBranch) | **POST** /v1/repos/repositories/{owner}/{repo}/branches | Create a branch (from a base sha). |
| [**createRepoPullRequest()**](RepoApi.md#createRepoPullRequest) | **POST** /v1/repos/repositories/{owner}/{repo}/pulls | Open a pull request. |
| [**createRepoRepository()**](RepoApi.md#createRepoRepository) | **POST** /v1/repos/repositories | Create a repository. |
| [**getRepoCommit()**](RepoApi.md#getRepoCommit) | **GET** /v1/repos/repositories/{owner}/{repo}/commits/{sha} | Fetch a single commit. |
| [**getRepoRepository()**](RepoApi.md#getRepoRepository) | **GET** /v1/repos/repositories/{owner}/{repo} | Fetch a single repository. |
| [**linkRepoTask()**](RepoApi.md#linkRepoTask) | **POST** /v1/repos/repositories/{owner}/{repo}/tasks/link | Link an existing Spatio task to this repo, allocating a per-repo number. |
| [**listRepoBranches()**](RepoApi.md#listRepoBranches) | **GET** /v1/repos/repositories/{owner}/{repo}/branches | List branches on a repository. |
| [**listRepoCommits()**](RepoApi.md#listRepoCommits) | **GET** /v1/repos/repositories/{owner}/{repo}/commits | List commits on a repository. |
| [**listRepoPullRequests()**](RepoApi.md#listRepoPullRequests) | **GET** /v1/repos/repositories/{owner}/{repo}/pulls | List pull requests on a repository. |
| [**listRepoRepositories()**](RepoApi.md#listRepoRepositories) | **GET** /v1/repos/repositories | List the caller&#39;s accessible repositories. |
| [**listRepoTasks()**](RepoApi.md#listRepoTasks) | **GET** /v1/repos/repositories/{owner}/{repo}/tasks | List tasks linked to this repo (the \&quot;issues\&quot; surface). |
| [**listRepoWorkflows()**](RepoApi.md#listRepoWorkflows) | **GET** /v1/repos/repositories/{owner}/{repo}/workflows | List CI workflows. |
| [**mergeRepoPullRequest()**](RepoApi.md#mergeRepoPullRequest) | **POST** /v1/repos/repositories/{owner}/{repo}/pulls/{number}/merge | Merge a pull request. |
| [**triggerRepoWorkflow()**](RepoApi.md#triggerRepoWorkflow) | **POST** /v1/repos/repositories/{owner}/{repo}/workflows/{id}/trigger | Trigger a workflow_dispatch run. |
| [**workspaceCreateRepoBranch()**](RepoApi.md#workspaceCreateRepoBranch) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/branches |  |
| [**workspaceCreateRepoPullRequest()**](RepoApi.md#workspaceCreateRepoPullRequest) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls |  |
| [**workspaceCreateRepoRepository()**](RepoApi.md#workspaceCreateRepoRepository) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories |  |
| [**workspaceGetRepoCommit()**](RepoApi.md#workspaceGetRepoCommit) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/commits/{sha} |  |
| [**workspaceGetRepoRepository()**](RepoApi.md#workspaceGetRepoRepository) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo} |  |
| [**workspaceLinkRepoTask()**](RepoApi.md#workspaceLinkRepoTask) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/tasks/link |  |
| [**workspaceListRepoBranches()**](RepoApi.md#workspaceListRepoBranches) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/branches |  |
| [**workspaceListRepoCommits()**](RepoApi.md#workspaceListRepoCommits) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/commits |  |
| [**workspaceListRepoPullRequests()**](RepoApi.md#workspaceListRepoPullRequests) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls |  |
| [**workspaceListRepoRepositories()**](RepoApi.md#workspaceListRepoRepositories) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories |  |
| [**workspaceListRepoTasks()**](RepoApi.md#workspaceListRepoTasks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/tasks |  |
| [**workspaceListRepoWorkflows()**](RepoApi.md#workspaceListRepoWorkflows) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/workflows |  |
| [**workspaceMergeRepoPullRequest()**](RepoApi.md#workspaceMergeRepoPullRequest) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls/{number}/merge |  |
| [**workspaceTriggerRepoWorkflow()**](RepoApi.md#workspaceTriggerRepoWorkflow) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/workflows/{id}/trigger |  |


## `createRepoBranch()`

```php
createRepoBranch($owner, $repo, $request_body): array<string,mixed>
```

Create a branch (from a base sha).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->createRepoBranch($owner, $repo, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->createRepoBranch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
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

## `createRepoPullRequest()`

```php
createRepoPullRequest($owner, $repo, $request_body): array<string,mixed>
```

Open a pull request.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->createRepoPullRequest($owner, $repo, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->createRepoPullRequest: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
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

## `createRepoRepository()`

```php
createRepoRepository($request_body): array<string,mixed>
```

Create a repository.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->createRepoRepository($request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->createRepoRepository: ', $e->getMessage(), PHP_EOL;
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

## `getRepoCommit()`

```php
getRepoCommit($owner, $repo, $sha): array<string,mixed>
```

Fetch a single commit.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$sha = 'sha_example'; // string

try {
    $result = $apiInstance->getRepoCommit($owner, $repo, $sha);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->getRepoCommit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **sha** | **string**|  | |

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

## `getRepoRepository()`

```php
getRepoRepository($owner, $repo): array<string,mixed>
```

Fetch a single repository.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->getRepoRepository($owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->getRepoRepository: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `linkRepoTask()`

```php
linkRepoTask($owner, $repo, $link_repo_task_request): array<string,mixed>
```

Link an existing Spatio task to this repo, allocating a per-repo number.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$link_repo_task_request = new \SpatioClient\Model\LinkRepoTaskRequest(); // \SpatioClient\Model\LinkRepoTaskRequest

try {
    $result = $apiInstance->linkRepoTask($owner, $repo, $link_repo_task_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->linkRepoTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **link_repo_task_request** | [**\SpatioClient\Model\LinkRepoTaskRequest**](../Model/LinkRepoTaskRequest.md)|  | |

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

## `listRepoBranches()`

```php
listRepoBranches($owner, $repo): array<string,mixed>
```

List branches on a repository.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->listRepoBranches($owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->listRepoBranches: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `listRepoCommits()`

```php
listRepoCommits($owner, $repo, $branch, $limit): array<string,mixed>
```

List commits on a repository.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$branch = 'branch_example'; // string
$limit = 56; // int

try {
    $result = $apiInstance->listRepoCommits($owner, $repo, $branch, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->listRepoCommits: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **branch** | **string**|  | [optional] |
| **limit** | **int**|  | [optional] |

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

## `listRepoPullRequests()`

```php
listRepoPullRequests($owner, $repo): array<string,mixed>
```

List pull requests on a repository.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->listRepoPullRequests($owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->listRepoPullRequests: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `listRepoRepositories()`

```php
listRepoRepositories($visibility, $limit): array<string,mixed>
```

List the caller's accessible repositories.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$visibility = 'visibility_example'; // string
$limit = 56; // int

try {
    $result = $apiInstance->listRepoRepositories($visibility, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->listRepoRepositories: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **visibility** | **string**|  | [optional] |
| **limit** | **int**|  | [optional] |

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

## `listRepoTasks()`

```php
listRepoTasks($owner, $repo, $state, $per_page, $page): array<string,mixed>
```

List tasks linked to this repo (the \"issues\" surface).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$state = 'state_example'; // string
$per_page = 56; // int
$page = 56; // int

try {
    $result = $apiInstance->listRepoTasks($owner, $repo, $state, $per_page, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->listRepoTasks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **state** | **string**|  | [optional] |
| **per_page** | **int**|  | [optional] |
| **page** | **int**|  | [optional] |

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

## `listRepoWorkflows()`

```php
listRepoWorkflows($owner, $repo): array<string,mixed>
```

List CI workflows.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->listRepoWorkflows($owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->listRepoWorkflows: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `mergeRepoPullRequest()`

```php
mergeRepoPullRequest($owner, $repo, $number, $request_body): array<string,mixed>
```

Merge a pull request.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$number = 56; // int
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->mergeRepoPullRequest($owner, $repo, $number, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->mergeRepoPullRequest: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **number** | **int**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | [optional] |

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

## `triggerRepoWorkflow()`

```php
triggerRepoWorkflow($owner, $repo, $id, $request_body): array<string,mixed>
```

Trigger a workflow_dispatch run.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$id = 'id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->triggerRepoWorkflow($owner, $repo, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->triggerRepoWorkflow: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | [optional] |

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

## `workspaceCreateRepoBranch()`

```php
workspaceCreateRepoBranch($org, $workspace, $owner, $repo, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCreateRepoBranch($org, $workspace, $owner, $repo, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceCreateRepoBranch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
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

## `workspaceCreateRepoPullRequest()`

```php
workspaceCreateRepoPullRequest($org, $workspace, $owner, $repo, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCreateRepoPullRequest($org, $workspace, $owner, $repo, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceCreateRepoPullRequest: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
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

## `workspaceCreateRepoRepository()`

```php
workspaceCreateRepoRepository($org, $workspace, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceCreateRepoRepository($org, $workspace, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceCreateRepoRepository: ', $e->getMessage(), PHP_EOL;
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

## `workspaceGetRepoCommit()`

```php
workspaceGetRepoCommit($org, $workspace, $owner, $repo, $sha): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$sha = 'sha_example'; // string

try {
    $result = $apiInstance->workspaceGetRepoCommit($org, $workspace, $owner, $repo, $sha);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceGetRepoCommit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **sha** | **string**|  | |

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

## `workspaceGetRepoRepository()`

```php
workspaceGetRepoRepository($org, $workspace, $owner, $repo): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->workspaceGetRepoRepository($org, $workspace, $owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceGetRepoRepository: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `workspaceLinkRepoTask()`

```php
workspaceLinkRepoTask($org, $workspace, $owner, $repo, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceLinkRepoTask($org, $workspace, $owner, $repo, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceLinkRepoTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
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

## `workspaceListRepoBranches()`

```php
workspaceListRepoBranches($org, $workspace, $owner, $repo): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->workspaceListRepoBranches($org, $workspace, $owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceListRepoBranches: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `workspaceListRepoCommits()`

```php
workspaceListRepoCommits($org, $workspace, $owner, $repo): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->workspaceListRepoCommits($org, $workspace, $owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceListRepoCommits: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `workspaceListRepoPullRequests()`

```php
workspaceListRepoPullRequests($org, $workspace, $owner, $repo): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->workspaceListRepoPullRequests($org, $workspace, $owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceListRepoPullRequests: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `workspaceListRepoRepositories()`

```php
workspaceListRepoRepositories($org, $workspace): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string

try {
    $result = $apiInstance->workspaceListRepoRepositories($org, $workspace);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceListRepoRepositories: ', $e->getMessage(), PHP_EOL;
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

## `workspaceListRepoTasks()`

```php
workspaceListRepoTasks($org, $workspace, $owner, $repo): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->workspaceListRepoTasks($org, $workspace, $owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceListRepoTasks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `workspaceListRepoWorkflows()`

```php
workspaceListRepoWorkflows($org, $workspace, $owner, $repo): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string

try {
    $result = $apiInstance->workspaceListRepoWorkflows($org, $workspace, $owner, $repo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceListRepoWorkflows: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |

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

## `workspaceMergeRepoPullRequest()`

```php
workspaceMergeRepoPullRequest($org, $workspace, $owner, $repo, $number, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$number = 56; // int
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceMergeRepoPullRequest($org, $workspace, $owner, $repo, $number, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceMergeRepoPullRequest: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **number** | **int**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | [optional] |

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

## `workspaceTriggerRepoWorkflow()`

```php
workspaceTriggerRepoWorkflow($org, $workspace, $owner, $repo, $id, $request_body): array<string,mixed>
```



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Personal Access Token (pat_...)) authorization: bearerAuth
$config = SpatioClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new SpatioClient\Api\RepoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$org = 'org_example'; // string
$workspace = 'workspace_example'; // string
$owner = 'owner_example'; // string
$repo = 'repo_example'; // string
$id = 'id_example'; // string
$request_body = NULL; // array<string,mixed>

try {
    $result = $apiInstance->workspaceTriggerRepoWorkflow($org, $workspace, $owner, $repo, $id, $request_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RepoApi->workspaceTriggerRepoWorkflow: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **org** | **string**|  | |
| **workspace** | **string**|  | |
| **owner** | **string**|  | |
| **repo** | **string**|  | |
| **id** | **string**|  | |
| **request_body** | [**array<string,mixed>**](../Model/mixed.md)|  | [optional] |

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
