# FederatedSearchRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **string** |  |
**platforms** | **string[]** | Subset to fan out to. Empty means all available platforms. | [optional]
**limit** | **int** |  | [optional] [default to 25]
**page_tokens** | **array<string,string>** | Per-platform cursor for pagination. | [optional]
**workspace_id** | **string** |  | [optional]
**organization_id** | **string** |  | [optional]
**include_shared** | **bool** |  | [optional]
**include_archived** | **bool** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
