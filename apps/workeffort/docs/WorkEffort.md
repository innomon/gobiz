# Work Effort Context

A `WorkEffort` is a fundamental entity representing a task, event, or project. It is used to track work, time, and resources.

## Coordination Hub
Work efforts act as a coordination hub, linking `Shipments`, `Facilities`, and `Parties`. For example, shipment events (Pickup/Arrival) are represented as work efforts to track estimated vs actual dates.

## Lifecycle
Work efforts transition through statuses (e.g., `CAL_TENTATIVE`, `CAL_CONFIRMED`, `CAL_COMPLETED`, `CAL_CANCELLED`).

## Relationships
- **Work Effort Type**: Defines the nature of the work (e.g., `TASK`, `EVENT`, `SHIPMENT_OUTBOUND`).
- **Assigned To**: Linked to a `Party` via `WorkEffortPartyAssignment` to define responsibility and attendance.
- **Linked To**: Associated with orders, products, or shipments to provide context for the work.

## Business Logic
1. **Status Coupling**: A work effort's status often mirrors the status of its associated master record (e.g., a shipment work effort becomes `CAL_CANCELLED` if the shipment is cancelled).
2. **Date Propagation**: Changes to a shipment's estimated dates must propagate to the associated work efforts to ensure scheduling accuracy.
3. **Role-Based Assignment**: Assignments to work efforts must include a role (e.g., `CAL_ATTENDEE`) and an initial status (e.g., `CAL_SENT`).

## Key Fields
- **Work Effort ID**: Unique identifier for the work effort.
- **Name**: A descriptive title for the work.
- **Current Status**: Tracks the current state of the work effort.
- **Description**: Detailed information about what needs to be done.
