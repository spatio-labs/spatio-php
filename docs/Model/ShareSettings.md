# ShareSettings

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**is_public** | **bool** |  |
**has_password** | **bool** |  |
**share_token** | **string** | Opaque token embedded in the public URL. Empty when &#x60;isPublic&#x60; is false. | [optional]
**share_url** | **string** | Fully-qualified public viewer URL. Computed server-side from &#x60;PUBLIC_VIEWER_BASE&#x60; (defaults to &#x60;https://spatio.app&#x60;) and the share token. Empty when the note is private. | [optional]
**password_set_at** | **\DateTime** | When the current password was set, if any. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
