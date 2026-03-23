# Order Header Context

`OrderHeader` contains the top-level information for an order, whether it's a Sales Order or a Purchase Order.

## Lifecycle
Orders transition through various statuses defined by `StatusItem`. Key dates include `order_date` (when the order was placed) and `entry_date` (when it was entered into the system).

## Relationships
- **Order Type**: Defines if it's a Sales or Purchase order.
- **Status**: Tracks the current state (e.g., Created, Approved, Completed, Cancelled).
- **Order Items**: An order header can have multiple line items.

## Key Fields
- **Order ID**: Unique identifier for the order.
- **Order Date**: The date the order was created by the customer or requester.
