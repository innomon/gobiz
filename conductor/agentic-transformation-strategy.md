# Agentic ERP Transformation Strategy

This document outlines how to transform legacy Apache OFBiz business logic into the GoBiz Agentic Framework.

## 1. Logic Extraction Process
For each OFBiz module (e.g., `accounting`, `order`, `product`):
1.  **Service Analysis**: Scan `servicedef/services_*.xml` to identify core business services.
2.  **Implementation Deep-Dive**: Locate the service implementation in Java (`src/main/java`), Groovy (`src/main/groovy`), or Mini-Lang (`minilang/`).
3.  **Rule Identification**: Extract critical business rules, constraints, and lifecycle transitions from the source code.
4.  **Documentation Embedding**: Append these rules as a "Business Logic" section in the corresponding `apps/{app}/docs/*.md` files.

## 2. Transforming Services into Tools
Instead of hard-coding every OFBiz service, we provide the Agents with **Knowledge (Docs)** and **Capabilities (Tools)**.

-   **Knowledge**: Documentation in `docs/*.md` provides the Agent with the "Why" and "How" (e.g., "A Budget item amount cannot exceed the total Budget").
-   **Capabilities**: The `CMS Agent` provides standard CRUD tools (`create`, `get`, `list`, `update`).
-   **Reasoning**: The Agent uses its reasoning loop to apply the **Knowledge** while executing the **Capabilities**.

## 3. Example Transformation (Accounting Module)
-   **Legacy**: `createBudget` service in `services_budget.xml`.
-   **Agentic**:
    1.  Agent reads `apps/accounting/docs/Budget.md` to understand budget structure.
    2.  Agent reads `apps/accounting/docs/BudgetItem.md` to understand item constraints.
    3.  Agent uses `cms_app_create` to instantiate a new Budget.
    4.  Agent uses `cms_app_create` to add items, ensuring they follow the logic described in the docs.

## 4. Current Progress
- [x] **Accounting**: Budget lifecycle and status transition rules documented.
- [x] **Party**: Identity segregation and ID constraint rules documented.
- [x] **Order**: Sales and Purchase order lifecycle rules (Inventory & Pricing) documented.
- [x] **Product**: PIM hierarchy and sales discontinuation logic documented.
- [x] **Content**: CMS hierarchy and DataResource coupling documented.
- [x] **HumanRes**: Employment relationship and role assignment rules documented.
- [x] **WorkEffort**: Coordination hub and status coupling logic documented.
- [x] **Manufacturing**: BOM quantity ratios and date effectiveness documented.
- [x] **Marketing**: Campaign targeting and attribution logic documented.
