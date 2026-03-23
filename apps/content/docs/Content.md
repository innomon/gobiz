# Content Context

A `Content` record represents a discrete piece of content within the CMS. It can be a document, image, or structured data item.

## Lifecycle
Content typically goes through various statuses (e.g., `CTNT_IN_PROGRESS`, `CTNT_PUBLISHED`, `CTNT_DEACTIVATED`). All status transitions must be validated to ensure content integrity before publication.

## Relationships
- **Content Type**: Linked to a `ContentType` defining its format and behavior.
- **Data Resource**: Linked to a `DataResource` that holds the actual content data (e.g., text, binary file).
- **Associations**: Content can be linked to other content via `ContentAssoc` to create hierarchies or translations.

## Business Logic
1. **Coupled Creation**: Creating content often involves the simultaneous creation of a `DataResource` and a `ContentAssoc` record if it's being added to an existing structure.
2. **Alternative URLs**: The system can generate SEO-friendly alternative URLs for content, which are stored and tracked for navigation.
3. **Data Integrity**: Content records without an associated `DataResource` are treated as structural or "folder" content.

## Key Fields
- **Content ID**: Unique identifier for the content.
- **Content Name**: Descriptive name for the content.
- **Description**: Detailed description of the content.
