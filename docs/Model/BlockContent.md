# BlockContent

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**rich_text** | [**\SpatioClient\Model\RichTextObject[]**](RichTextObject.md) |  | [optional]
**language** | **string** | Programming language for &#x60;code&#x60; blocks. | [optional]
**checked** | **bool** | Toggle state for &#x60;to_do&#x60; blocks. | [optional]
**icon** | **string** | Emoji or short string for &#x60;callout&#x60; blocks. | [optional]
**color** | **string** | Theme color for &#x60;callout&#x60; blocks. | [optional]
**url** | **string** | Source URL for &#x60;image&#x60;, &#x60;video&#x60;, &#x60;file&#x60; blocks. | [optional]
**caption** | **string** | Visible caption for media blocks. | [optional]
**alt_text** | **string** | Screen-reader description for media blocks. Distinct from &#x60;caption&#x60; (visible to readers) — required for accessible notes when the image conveys meaning. | [optional]
**embed_url** | **string** | Source URL for &#x60;embed&#x60; blocks. | [optional]
**cells** | **\SpatioClient\Model\RichTextObject[][]** | 2D rich-text grid for &#x60;table&#x60; and &#x60;table_row&#x60; blocks. | [optional]
**expression** | **string** | TeX/MathJax expression for &#x60;equation&#x60; blocks. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
