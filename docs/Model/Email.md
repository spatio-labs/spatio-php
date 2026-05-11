# Email

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**thread_id** | **string** |  | [optional]
**provider** | **string** |  | [optional]
**account_id** | **string** |  | [optional]
**subject** | **string** |  |
**from** | **string** |  |
**to** | **string[]** |  |
**cc** | **string[]** |  | [optional]
**bcc** | **string[]** |  | [optional]
**body** | **string** |  |
**html** | **bool** | &#x60;true&#x60; when &#x60;body&#x60; contains HTML, &#x60;false&#x60; for plain text. |
**date** | **\DateTime** |  |
**labels** | **string[]** |  | [optional]
**is_read** | **bool** |  |
**is_starred** | **bool** |  |
**attachments** | [**\SpatioClient\Model\AttachmentMeta[]**](AttachmentMeta.md) |  | [optional]
**snippet** | **string** |  | [optional]
**message_id** | **string** | RFC 5322 Message-ID header. | [optional]
**in_reply_to** | **string** | RFC 5322 In-Reply-To header — the parent message id this message is a reply to. | [optional]
**references** | **string[]** | RFC 5322 References header (ancestor chain). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
