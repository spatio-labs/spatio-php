# Sheet

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**provider** | **string** | Registered provider id (e.g. &#x60;native-sheets&#x60;). | [optional]
**account_id** | **string** | Connected-account row this sheet belongs to. | [optional]
**owner_user_id** | **string** | User id of the sheet owner; non-native providers leave empty. | [optional]
**name** | **string** |  |
**description** | **string** |  | [optional]
**data** | **array<string,mixed>** | Free-form provider blob. Treat as opaque. | [optional]
**row_count** | **int** |  |
**column_count** | **int** |  |
**sheet_count** | **int** | Tab count when the file contains multiple sheets. |
**is_public** | **bool** |  |
**is_read_only** | **bool** |  |
**file_size** | **int** |  | [optional]
**last_accessed_at** | **\DateTime** |  | [optional]
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
