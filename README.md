# GoBiz: Agentic ERP Integration Platform

GoBiz is a modern, agentic platform built on the `aigen-app` framework. It serves as an intelligent orchestrator that translates and extends the massive capabilities of Apache OFBiz into a flexible, schema-driven, and AI-ready environment.

## 🚀 Overview

The project integrates a high-performance **Go-based orchestrator** with a complete **Apache OFBiz (v24.09.05)** ERP installation. By mapping OFBiz's complex XML data models into the `aigen-app` JSON standard, GoBiz enables:

- **AI-Driven Workflows**: Multi-agent systems (Router, CMS, UI) that autonomously manage ERP data.
- **Dynamic UI Generation**: Schemas automatically drive the creation of administrative dashboards.
- **Unified API**: Access to diverse ERP modules through a simplified GraphQL and JSON interface.

## 📂 Project Structure

```text
gobiz/
├── apps/                    # Translated aigen-app applications
│   ├── accounting/          # Budgets, Invoices, Ledger
│   ├── party/               # CRM: Parties, Persons, Groups
│   ├── order/               # Sales and Purchase Orders
│   ├── product/             # PIM: Products and Categories
│   ├── apps.json            # Central registry of enabled apps
│   └── ...                  # Other ERP modules
├── apache-ofbiz-24.09.05/   # Core Apache OFBiz ERP installation
├── conductor/               # AI-Agent development and mapping guides
├── wwwroot/                 # Static assets and public files
├── config.yaml              # Application configuration (Port, DSN)
├── agentic.yaml             # Agent and Tool definitions
├── GEMINI.md                # Project mandates and standards
├── mapping_ofbiz2gobiz.md   # OFBiz to AiGen mapping documentation
└── main.go                  # Application entry point
```

## 🛠️ Getting Started

### Prerequisites
- **Go**: 1.25.6 or later.
- **SQLite**: Local file `aigen.db` is used for schema and record persistence.

### Running the Application
1. **Initialize Dependencies**:
   ```bash
   go mod tidy
   ```
2. **Build and Run**:
   ```bash
   go build -o gobiz main.go
   ./gobiz
   ```
3. **Access the Interface**:
   - The application defaults to `http://localhost:5000`.

## 🤖 Agentic System

GoBiz uses a multi-agent architecture defined in `agentic.yaml`:
- **Router Agent**: Dispatches user intents to specialized sub-agents.
- **CMS Agent**: Handles data operations (List, Get, Create) across the translated apps.
- **UI Agent**: Manages the dynamic dashboard and updates visual components.

## 📚 Documentation

- **[GEMINI.md](./GEMINI.md)**: Technical standards and workflow mandates for developers.
- **[mapping_ofbiz2gobiz.md](./mapping_ofbiz2gobiz.md)**: Detailed strategy for mapping OFBiz XML entities to GoBiz JSON schemas.
- **[Downstream App Guide](./conductor/downstream-app-development-guide.md)**: Step-by-step instructions for creating new GoBiz apps.
- **[App Definition Instructions](./conductor/app_definition_instruction.md)**: Best practices for self-describing applications.

## ⚖️ License
This project leverages Apache OFBiz which is licensed under the Apache License 2.0. GoBiz specific logic follows the local project licensing.
