# Order Item Context

`OrderItem` represents a specific line item within an order, specifying the product and quantity.

## Lifecycle
Items are associated with an `OrderHeader` and inherit its status or can have their own status.

## Relationships
- **Order Header**: The parent order this item belongs to.
- **Product**: The product being ordered.

## Key Fields
- **Order Item Seq ID**: A sequence number to identify the item within the order.
- **Quantity**: The number of units ordered.
- **Unit Price**: The price per unit at the time of the order.
