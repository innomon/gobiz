# Order Header Context

`OrderHeader` contains the top-level information for an order, whether it's a Sales Order or a Purchase Order.

## Lifecycle
Orders transition through various statuses (e.g., `ORDER_CREATED`, `ORDER_APPROVED`, `ORDER_COMPLETED`, `ORDER_CANCELLED`). All status transitions are validated against the `StatusValidChange` rules to ensure logical progression.

### Inventory Management
For **Sales Orders**, the system must verify inventory availability before allowing the order to proceed to the `APPROVED` state. Orders for discontinued products (based on `salesDiscontinuationDate`) are automatically rejected.

## Relationships
- **Order Type**: Defines if it's a Sales or Purchase order.
- **Status**: Tracks the current state of the order.
- **Order Items**: An order header can have multiple line items.
- **Parties**: Linked to parties via roles (e.g., Bill-to Customer, Bill-from Vendor).

## Business Logic
1. **Purchase Order Pricing**: When creating or updating a Purchase Order, the unit price defaults to the `lastPrice` from the `SupplierProduct` record unless overridden by an active agreement.
2. **Sales Validation**: Sales orders cannot be created for products that have passed their `salesDiscontinuationDate`.
3. **Traceability**: Every order maintains a record of who entered the order and the timestamp of every status change.

## Key Fields
- **Order ID**: Unique identifier for the order.
- **Order Date**: The date the order was created by the customer or requester.
