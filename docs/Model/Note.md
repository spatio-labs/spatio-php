# Note

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Stable provider id for the note. |
**provider** | **string** | Registered provider id (e.g. &#x60;native-notes&#x60;). | [optional]
**account_id** | **string** | Connected-account row this note belongs to. | [optional]
**owner_user_id** | **string** | User id of the note&#39;s owner. Surfaced so the renderer can show \&quot;Shared with you\&quot; when &#x60;ownerUserId&#x60; differs from the viewer&#39;s id. Empty for non-native providers. | [optional]
**title** | **string** |  |
**content** | **string** | Markdown body. The block tree at &#x60;/v1/notes/{id}/blocks&#x60; is the canonical structured representation; &#x60;content&#x60; is a flattened markdown view kept for clients that don&#39;t render blocks. |
**icon** | **string** | Emoji or short string used as the note&#39;s icon. | [optional]
**cover_image** | **string** | URL of the note&#39;s cover image. | [optional]
**parent_id** | **string** | Parent note id when notes are nested. | [optional]
**properties** | **array<string,mixed>** | Free-form provider-specific properties (tags, etc.). | [optional]
**archived** | **bool** |  |
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |
**last_edited_by** | **string** | User id of the most recent editor. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
