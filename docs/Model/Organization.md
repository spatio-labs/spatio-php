# Organization

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**name** | **string** |  |
**slug** | **string** |  |
**description** | **string** |  | [optional]
**logo_url** | **string** |  | [optional]
**role** | **string** | The caller&#39;s role in this org (&#x60;owner&#x60;, &#x60;admin&#x60;, &#x60;billing_admin&#x60;, &#x60;member&#x60;). |
**member_count** | **int** |  | [optional]
**workspace_count** | **int** |  | [optional]
**workspaces** | [**\SpatioClient\Model\OrganizationWorkspacesInner[]**](OrganizationWorkspacesInner.md) | Compact workspace summaries embedded in the org-list response. | [optional]
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
