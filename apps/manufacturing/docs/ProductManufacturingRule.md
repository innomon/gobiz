# Product Manufacturing Rule Context

A `ProductManufacturingRule` (Product To Part Rule) defines how components are handled during the manufacturing process. It can represent substitution rules, part inclusion logic, or other conditional manufacturing operations.

## Use Cases
- **Substitution**: Defining that one part can be used instead of another under certain conditions.
- **Conditional Components**: Rules for including specific parts based on product features.

## Key Fields
- **Rule ID**: Unique identifier for the rule.
- **Product ID**: The main product the rule applies to.
- **Rule Operator**: Logic applied to the rule (e.g., substitution, exclusion).
- **Quantity**: The amount of material affected by the rule.
