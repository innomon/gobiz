# Product Context

`Product` is the central entity for all items sold or used in the system.

## Sales Lifecycle
A product's availability for sale is governed by its `introductionDate` and `salesDiscontinuationDate`. Once the discontinuation date has passed, the product can no longer be sold in the system, even if inventory is available.

## Relationships
- **Product Type**: Defines the nature of the product (e.g., `FINISHED_GOOD`, `SERVICE`, `RAW_MATERIAL`).
- **Product Categories**: Products are organized into hierarchies through `ProductCategory` and `ProductCategoryMember`.

## Business Logic
1. **Discontinuation Enforcement**: The system must check the `salesDiscontinuationDate` during the order creation process.
2. **Pricing Integrity**: Product prices are managed through `ProductPrice`, where multiple price types (e.g., `LIST_PRICE`, `DEFAULT_PRICE`, `PROMO_PRICE`) can be defined for different purposes.
3. **Inventory Coupling**: Products can have physical inventory (e.g., serialized or non-serialized) or represent abstract services.

## Key Fields
- **Product ID**: Unique identifier for the product.
- **Product Name**: The display name of the product.
