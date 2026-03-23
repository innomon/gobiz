# Budget Context

A `Budget` represents a financial plan for a defined period. It is used to track planned revenues and expenses.

## Lifecycle
A budget is typically created for a `CustomTimePeriod`. It can be of various `BudgetType` (e.g., Operating Budget, Capital Budget). 

### Status Transitions
Budget statuses (e.g., `BG_CREATED`, `BG_APPROVED`, `BG_REJECTED`) are managed via the `BudgetStatus` entity. All status transitions must be validated against the `StatusValidChange` entity to ensure only permitted lifecycle moves occur.

## Relationships
- **Budget Type**: Linked to a `BudgetType` which defines the category of the budget.
- **Time Period**: Linked to a `CustomTimePeriod` representing the duration the budget covers.
- **Budget Items**: A budget can have multiple `BudgetItem` records associated with it.
- **Budget Roles**: Parties (Persons or Groups) are assigned to budgets via `BudgetRole` to define accountability (e.g., Budget Manager, Reviewer).

## Business Logic
1. **Status Validation**: Whenever a budget status is updated, the system must verify that the current status can transition to the new status.
2. **Accountability**: Every budget should have at least one assigned role to ensure a clear owner for the financial plan.
3. **Audit History**: All status changes and reviews must be recorded to provide a complete audit trail of the budget's evolution.

## Key Fields
- **Budget ID**: Unique identifier for the budget.
- **Comments**: General notes or descriptions about the budget.
