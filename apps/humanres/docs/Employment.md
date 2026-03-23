# Employment Context

An `Employment` record represents an employment relationship between two parties.

## Lifecycle
Employment begins on a `fromDate` and may terminate on a `thruDate`. It defines the roles each party plays in the relationship.

## Relationships
- **Party From**: Typically the employer (e.g., an internal organization).
- **Party To**: Typically the employee.
- **Role Type**: Defines the roles (e.g., Employer, Employee) within the employment.

## Key Fields
- **Party ID From**: The party acting as the employer.
- **Party ID To**: The party acting as the employee.
- **From Date**: Start date of employment.
- **Thru Date**: End date of employment (if applicable).
