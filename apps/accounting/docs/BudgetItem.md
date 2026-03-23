# Budget Item Context

A `BudgetItem` is a specific line item within a `Budget`.

## Lifecycle
Budget items are created as part of a budget to detail specific allocations of funds. Each item belongs to a `BudgetItemType`.

## Relationships
- **Budget**: Every item must be associated with a `Budget`.
- **Item Type**: The `BudgetItemType` specifies the nature of the allocation (e.g., Personnel, Supplies).

## Constraints
- **Amount**: The amount allocated for this item. Should be positive.
- **Purpose**: A description of what the funds are intended for.
- **Justification**: The rationale for the budget allocation.
