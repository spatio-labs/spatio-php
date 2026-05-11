# SpatioEvent

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**title** | **string** |  |
**description** | **string** |  | [optional]
**start_time** | **\DateTime** |  |
**end_time** | **\DateTime** |  |
**all_day** | **bool** |  |
**location** | **string** |  | [optional]
**location_details** | **array<string,string>** | Free-form key/value (lat, lng, room, etc.). | [optional]
**organizer** | **string** | Organizer email. | [optional]
**attendees** | [**\SpatioClient\Model\Attendee[]**](Attendee.md) |  | [optional]
**recurrence_rule** | **string** | RFC 5545 RRULE. | [optional]
**recurrence_id** | **string** | Set on instances of a recurring series. | [optional]
**original_start** | **\DateTime** | Original start of a moved recurring instance. | [optional]
**status** | **string** | Provider-mapped event status. Free-form string — common values are &#x60;confirmed&#x60;, &#x60;tentative&#x60;, &#x60;cancelled&#x60;, &#x60;needs_action&#x60;, and the empty string when the provider doesn&#39;t populate it. Not enumerated strictly because providers add custom values and the platform passes them through verbatim. |
**visibility** | **string** | Free-form visibility string. Common values: &#x60;public&#x60;, &#x60;private&#x60;, &#x60;confidential&#x60;, plus empty when unset. |
**busy** | **bool** | Whether this event marks the time as busy or free. |
**reminders** | [**\SpatioClient\Model\Reminder[]**](Reminder.md) |  | [optional]
**travel_time_minutes** | **int** | Apple Calendar&#39;s local-only travel buffer. Stored on the cached row but not synced to providers that don&#39;t model it. | [optional]
**categories** | **string[]** |  | [optional]
**color** | **string** |  | [optional]
**user_id** | **string** |  | [optional]
**account_id** | **string** |  |
**provider** | **string** | Standardized provider id (e.g. &#x60;google-calendar&#x60;, &#x60;native-calendar&#x60;). Mirrors &#x60;provider_id&#x60; — both are populated on writes; clients should prefer &#x60;provider&#x60;. | [optional]
**provider_id** | **string** | Legacy alias of &#x60;provider&#x60;. |
**provider_data** | **array<string,mixed>** | Provider-specific extras. | [optional]
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |
**deleted_at** | **\DateTime** |  | [optional]
**synced_at** | **\DateTime** |  | [optional]
**conference_data** | [**\SpatioClient\Model\ConferenceData**](ConferenceData.md) |  | [optional]
**attachments** | [**\SpatioClient\Model\Attachment[]**](Attachment.md) |  | [optional]
**url** | **string** |  | [optional]
**etag** | **string** |  | [optional]
**sequence** | **int** |  | [optional]
**custom_data** | **array<string,string>** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
