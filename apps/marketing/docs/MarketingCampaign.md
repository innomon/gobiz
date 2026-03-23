# Marketing Campaign Context

A `MarketingCampaign` represents a focused marketing effort to reach a set of target parties or customers.

## Lifecycle
Campaigns progress through phases of planning, execution, and review.

## Relationships
- **Parties**: Associated with parties (customers, leads) via `ContactList`.
- **Roles**: Parties are assigned roles like `CAMPAIGN_MANAGER`.
- **Promotion**: Campaigns are often linked to specific product promotions (`ProductPromo`).

## Business Logic
1. **Targeting**: Campaigns are executed against one or more `ContactList` records which represent the target audience.
2. **Attribution**: The effectiveness of a campaign is measured by tracking orders or responses that reference the campaign's ID.
3. **Budgetary Coupling**: Campaigns can be linked back to the `Accounting` module's `Budget` to track marketing spend.
