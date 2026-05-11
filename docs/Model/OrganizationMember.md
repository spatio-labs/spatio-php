# OrganizationMember

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | &#x60;OrganizationMember&#x60; row id. |
**user_id** | **string** |  |
**role** | **string** |  |
**joined_at** | **\DateTime** |  |
**invited_by** | [**\SpatioClient\Model\OrganizationMemberInvitedBy**](OrganizationMemberInvitedBy.md) |  | [optional]
**user** | **array<string,mixed>** | Embedded user-profile fields (id, email, name, profilePhoto, ...). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
