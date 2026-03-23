# Mapping Apache OFBiz to GoBiz (AiGen APP)

This document outlines the methodology and specific mappings used to translate Apache OFBiz applications into the GoBiz (`aigen-app`) framework.

## Source of Truth
The primary source for all entity definitions is the comprehensive data model directory:
`apache-ofbiz-24.09.05/applications/datamodel/entitydef/`

While individual components have their own `entitydef` folders, they often contain only specialized reports or overrides. The `datamodel` directory provides the base system schemas.

## Technical Mapping Strategy

### 1. Naming Conventions
| Element | OFBiz (XML) | GoBiz (JSON) | Note |
| :--- | :--- | :--- | :--- |
| **App Name** | Component Name (e.g., `accounting`) | App Folder Name (e.g., `apps/accounting`) | Matches the folder structure. |
| **Entity Name** | `entity-name` (PascalCase) | `Name` (PascalCase) | Used for GraphQL and UI labels. |
| **Table Name** | `table-name` (or derived) | `TableName` (snake_case) | Prefixed with `app_name_` for GoBiz isolation. |
| **Field Name** | `name` (camelCase) | `Field` (snake_case) | Standardized for modern database consistency. |

### 2. Data Type Mapping
OFBiz types are mapped to `aigen-app` primitives to ensure compatibility with the JSON-based storage and dynamic UI generation.

| OFBiz Type | GoBiz `DataType` | GoBiz `DisplayType` |
| :--- | :--- | :--- |
| `id`, `id-long`, `id-vlong` | `String` | `Text` |
| `description`, `comment`, `value` | `String` | `Text` |
| `long-varchar` | `String` | `TextArea` |
| `very-long` | `String` | `RichText` |
| `currency-amount`, `fixed-point` | `Float` | `Number` |
| `floating-point`, `numeric` | `Float` | `Number` |
| `date-time`, `date` | `DateTime` | `Date` |
| `indicator` | `Boolean` | `Checkbox` |

### 3. Relationship Mapping
| OFBiz Relation | GoBiz `DataType` | GoBiz `DisplayType` | Note |
| :--- | :--- | :--- | :--- |
| `<relation type="one">` | `Lookup` | `Select` | Maps to the `Name` of the target entity. |
| `<relation type="many">` | `Collection` | `DataTable` | (Planned) Expressed via foreign key lookups. |

## Translated Applications Index

| App Name | Source XML File | Primary Entities Translated |
| :--- | :--- | :--- |
| **Accounting** | `accounting-entitymodel.xml` | `Budget`, `BudgetItem` |
| **Party** | `party-entitymodel.xml` | `Party`, `Person`, `PartyGroup` |
| **Order** | `order-entitymodel.xml` | `OrderHeader`, `OrderItem` |
| **Product** | `product-entitymodel.xml` | `Product`, `ProductCategory` |
| **Content** | `content-entitymodel.xml` | `Content`, `DataResource` |
| **HumanRes** | `humanres-entitymodel.xml` | `PartyQual`, `Employment` |
| **Manufacturing** | `manufacturing-entitymodel.xml` | `ProductManufacturingRule`, `TechDataCalendar` |
| **Marketing** | `marketing-entitymodel.xml` | `MarketingCampaign`, `ContactList` |
| **WorkEffort** | `workeffort-entitymodel.xml` | `WorkEffort` |

## Workflow for Further Expansion
To add more entities from OFBiz:
1. Locate the entity in the corresponding `*-entitymodel.xml` file in `datamodel/entitydef/`.
2. Convert the XML `<entity>` block to a JSON schema in the app's `schemas/` directory.
3. Update the `app_def.json` to include the new entity and a link to its documentation.
4. Create a Markdown file in `docs/` describing the business context and lifecycle.
