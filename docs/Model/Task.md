# Task

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**provider** | **string** | Registered provider id (e.g. &#x60;native-tasks&#x60;, &#x60;linear&#x60;). | [optional]
**account_id** | **string** |  | [optional]
**owner_user_id** | **string** |  | [optional]
**title** | **string** |  |
**description** | **string** |  | [optional]
**status** | **string** | Free-form status string. Canonical values across most providers: &#x60;todo&#x60;, &#x60;in_progress&#x60;, &#x60;in_review&#x60;, &#x60;backlog&#x60;, &#x60;done&#x60;. The platform falls back to &#x60;done&#x60; when &#x60;completed&#x60; is true and &#x60;status&#x60; is empty, else &#x60;todo&#x60;. | [optional]
**completed** | **bool** |  |
**due_date** | **\DateTime** |  | [optional]
**priority** | **string** | Priority bucket. Canonical values (mapped from a 0–4 integer): &#x60;none&#x60;, &#x60;low&#x60;, &#x60;medium&#x60;, &#x60;high&#x60;, &#x60;urgent&#x60;. |
**labels** | **string[]** |  | [optional]
**tags** | **string[]** |  | [optional]
**assignee_id** | **string** |  | [optional]
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |
**completed_at** | **\DateTime** |  | [optional]
**parent_task_id** | **string** | Parent task id when this is a subtask. | [optional]
**metadata** | **array<string,mixed>** | Provider-specific extras. | [optional]
**type** | **string** | Discriminator. Canonical values: &#x60;todo&#x60;, &#x60;reminder&#x60;, &#x60;issue&#x60;. Empty defaults to &#x60;todo&#x60;. | [optional]
**source_platform** | **string** | When this task was auto-generated from another artifact (e.g. a calendar event reminder), the platform id of that artifact. | [optional]
**source_id** | **string** | Source artifact id paired with &#x60;sourcePlatform&#x60;. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
