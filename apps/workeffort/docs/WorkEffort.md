# Work Effort Context

A `WorkEffort` is a fundamental entity representing a task, event, or project. It is used to track work, time, and resources.

## Lifecycle
Work efforts have statuses (e.g., In Progress, Completed, Cancelled). They can be scheduled with start and end dates.

## Relationships
- **Work Effort Type**: Defines the nature of the work (e.g., Task, Event, Production Run).
- **Assigned To**: Often linked to a `Party` or `Person`.
- **Linked To**: Can be associated with `OrderHeader`, `OrderItem`, or `Product`.

## Key Fields
- **Work Effort ID**: Unique identifier for the work effort.
- **Name**: A descriptive title for the work.
- **Current Status**: Tracks the current state of the work effort.
- **Description**: Detailed information about what needs to be done.
