# TokenResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**access_token** | **string** | Opaque bearer token. Format &#x60;tok_&lt;32 random base64url&gt;&#x60;. |
**token_type** | **string** |  |
**expires_in** | **int** | Seconds until access_token expires. |
**refresh_token** | **string** |  | [optional]
**scope** | **string** |  | [optional]
**id_token** | **string** | Only present when &#x60;openid&#x60; scope was granted. RS256-signed JWT — verify against the JWKS. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
