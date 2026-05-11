# BulkDeleteTasksRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**task_ids** | **string[]** |  | [optional]
**account_ids** | **string[]** | Parallel slice with taskIds — accountIds[i] targets taskIds[i]. | [optional]
**task_id** | **string** | Singular fallback when only deleting one task. | [optional]
**account_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
