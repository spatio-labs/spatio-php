# Workspace

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**name** | **string** |  |
**slug** | **string** |  |
**description** | **string** |  | [optional]
**logo_url** | **string** |  | [optional]
**organization_id** | **string** |  | [optional]
**organization** | [**\SpatioClient\Model\WorkspaceOrganization**](WorkspaceOrganization.md) |  | [optional]
**role** | **string** | The caller&#39;s role in this workspace (&#x60;owner&#x60;, &#x60;admin&#x60;, &#x60;member&#x60;, &#x60;guest&#x60;). | [optional]
**settings** | **mixed** | Per-workspace settings. Currently emitted as either an object (&#x60;{language, timezone, ...}&#x60;) on &#x60;GET /v1/workspaces/{id}&#x60; or a JSON-encoded string on &#x60;GET /v1/organizations/{id}/workspaces&#x60;. Treat as opaque and parse defensively. | [optional]
**is_default** | **bool** |  | [optional]
**member_count** | **int** |  | [optional]
**billing_tier** | **string** |  | [optional]
**created_at** | **\DateTime** |  | [optional]
**updated_at** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
