# CreateEventRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **string** |  |
**calendar_id** | **string** | Specific calendar within the account; omit for the default. | [optional]
**event** | [**\SpatioClient\Model\SpatioEvent**](SpatioEvent.md) |  |
**send_updates** | **string** | Notification policy passed through to the provider. | [optional]
**conference_type** | **string** | When set, the platform will auto-attach a conference link of the matching type (&#x60;spatio&#x60;, &#x60;meet&#x60;, &#x60;zoom&#x60;, &#x60;teams&#x60;). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
