# OrganizationInvitation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**organization_id** | **string** |  | [optional]
**email** | **string** |  |
**role** | **string** |  |
**token** | **string** | Opaque invitation token (omitted on list responses). | [optional]
**expires_at** | **\DateTime** |  | [optional]
**created_at** | **\DateTime** |  |
**accepted_at** | **\DateTime** |  | [optional]
**revoked_at** | **\DateTime** |  | [optional]
**invited_by** | [**\SpatioClient\Model\OrganizationMemberInvitedBy**](OrganizationMemberInvitedBy.md) |  | [optional]
**status** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
