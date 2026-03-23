# Content Context

A `Content` record represents a discrete piece of content within the CMS. It can be a document, image, or structured data item.

## Lifecycle
Content typically goes through various statuses (e.g., Draft, Approved, Published) and is associated with a specific `ContentType`.

## Relationships
- **Content Type**: Linked to a `ContentType` defining its format and behavior.
- **Data Resource**: Often linked to a `DataResource` that holds the actual content data.
- **Status**: Tracked via `StatusItem`.

## Key Fields
- **Content ID**: Unique identifier for the content.
- **Content Name**: Descriptive name for the content.
- **Description**: Detailed description of the content.
