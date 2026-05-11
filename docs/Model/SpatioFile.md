# SpatioFile

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**provider** | **string** |  | [optional]
**account_id** | **string** |  | [optional]
**name** | **string** |  |
**size** | **int** | Bytes. |
**mime_type** | **string** |  |
**folder_id** | **string** |  | [optional]
**storage_type** | **string** | Backing storage class — &#x60;r2&#x60;, &#x60;gdrive&#x60;, &#x60;dropbox&#x60;, etc. Provider-specific; treat as opaque. |
**download_url** | **string** | Pre-signed download URL when one is cached on the row. Use &#x60;GET /v1/files/{id}/download&#x60; for a guaranteed-fresh URL — this field can lag past expiry. | [optional]
**metadata** | **array<string,mixed>** |  | [optional]
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
