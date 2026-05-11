# FederatedSearch200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**items** | [**\SpatioClient\Model\FederatedSearch200ResponseItemsInner[]**](FederatedSearch200ResponseItemsInner.md) |  |
**next_page_tokens** | **array<string,string>** |  | [optional]
**per_platform** | [**array<string,\SpatioClient\Model\FederatedSearch200ResponsePerPlatformValue>**](FederatedSearch200ResponsePerPlatformValue.md) |  |
**errors** | **array<string,string>** | Per-platform errors. Other platforms still return results. | [optional]
**total_returned** | **int** |  |
**took** | **string** | Aggregate wall-clock time for the fan-out, e.g. \&quot;120ms\&quot;. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
