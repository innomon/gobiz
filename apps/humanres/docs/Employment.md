# Employment Context

An `Employment` record represents an employment relationship between two parties.

## Lifecycle
Employment begins on a `fromDate` and may terminate on a `thruDate`. All employment relationships must have a clear start date and follow a defined termination process.

## Relationships
- **Employer**: Typically an `INTERNAL_ORGANIZATIO` party.
- **Employee**: Typically a `PERSON` party with the role of `EMPLOYEE`.
- **Fulfillment**: Employment is often linked to an `EmplPosition` via `EmplPositionFulfillment`.

## Business Logic
1. **Relationship-Based**: Employment is a specialized form of `PartyRelationship` where the `relationshipName` is `EMPLOYMENT`.
2. **Mandatory Roles**: Creating an employment record requires the parties involved to have the appropriate roles (`INTERNAL_ORGANIZATIO` and `EMPLOYEE`).
3. **Overlapping Rules**: A person can have multiple employment records over time, but generally only one active `EMPLOYMENT` relationship with the same organization at a given time.

## Key Fields
- **Party ID From**: The party acting as the employer.
- **Party ID To**: The party acting as the employee.
- **From Date**: Start date of employment.
- **Thru Date**: End date of employment (if applicable).
