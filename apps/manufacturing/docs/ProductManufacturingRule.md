# Product Manufacturing Rule Context

A `ProductManufacturingRule` (often part of a Bill of Materials or BOM) defines how products are manufactured from components.

## Lifecycle
Manufacturing rules define the production process and the relationship between a finished product and its raw materials or sub-assemblies.

## Relationships
- **Product**: The finished product being manufactured.
- **Component**: The raw material or part used in the process.

## Business Logic
1. **Quantity Ratios**: Rules specify the exact quantity of a component required to produce a specific quantity of the finished product.
2. **Sub-Assembly Logic**: Manufacturing rules can be nested, where one rule produces a component that is then used in a higher-level rule.
3. **Date Effective**: Rules are often time-bound, reflecting changes in manufacturing processes or component availability over time.
