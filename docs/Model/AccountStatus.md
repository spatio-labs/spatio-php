# AccountStatus

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | **string** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;, &#x60;google-keep&#x60;). |
**account_id** | **string** | Connected-account row id. |
**account_name** | **string** | Human-readable label for the account, when available. | [optional]
**status** | **string** | - &#x60;ok&#x60; — provider call returned without error. - &#x60;error&#x60; — provider call failed; details in &#x60;error&#x60;. - &#x60;skipped&#x60; — connection was filtered out before the provider   call ran. Reserved; not currently emitted by the runtime. |
**error** | [**\SpatioClient\Model\AccountError**](AccountError.md) |  | [optional]
**next_page_token** | **string** | Provider-specific cursor for the next page, if any. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
