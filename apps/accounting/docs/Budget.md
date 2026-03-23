# Budget Context

A `Budget` represents a financial plan for a defined period. It is used to track planned revenues and expenses.

## Lifecycle
A budget is typically created for a `CustomTimePeriod`. It can be of various `BudgetType` (e.g., Operating Budget, Capital Budget). 

## Relationships
- **Budget Type**: Linked to a `BudgetType` which defines the category of the budget.
- **Time Period**: Linked to a `CustomTimePeriod` representing the duration the budget covers.
- **Budget Items**: A budget can have multiple `BudgetItem` records associated with it.

## Key Fields
- **Budget ID**: Unique identifier for the budget.
- **Comments**: General notes or descriptions about the budget.
