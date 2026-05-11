# CreateDraftRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **string** |  | [optional]
**to** | **string[]** |  | [optional]
**cc** | **string[]** |  | [optional]
**bcc** | **string[]** |  | [optional]
**subject** | **string** |  | [optional]
**body** | **string** |  | [optional]
**html** | **bool** |  | [optional]
**attachments** | [**\SpatioClient\Model\AttachmentInput[]**](AttachmentInput.md) |  | [optional]
**thread_id** | **string** | Provider thread id — set when this draft is a reply, so the sent message lands inside the parent thread. | [optional]
**in_reply_to** | **string** |  | [optional]
**references** | **string[]** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
