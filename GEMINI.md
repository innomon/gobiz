# Gobiz Project Mandates

This document defines the foundational mandates and technical standards for the `gobiz` project. All changes must strictly adhere to these guidelines.

## Project Overview
`gobiz` is an agentic platform built using the `aigen-app` framework. It integrates an orchestrator (Go) with a large-scale ERP system (Apache OFBiz) to provide AI-driven CMS and UI management.

## Technical Standards

### Backend (Go)
- **Go Version:** 1.25.6 or later.
- **Conventions:** Follow standard Go idioms and `go fmt`.
- **Testing:** New features must include unit tests in `*_test.go` files.
- **Dependencies:** Use `go mod tidy` to manage dependencies. Avoid adding large dependencies unless strictly necessary.

### Agentic System (`agentic.yaml`)
- **Architecture:** The project uses a multi-agent architecture (Router, CMS, UI agents).
- **Tooling:** When adding new capabilities, define them as `tools` in `agentic.yaml`.
- **Instruction Sets:** Ensure agent `instruction` fields are concise and strictly define the agent's role and tool usage.
- **Provider Consistency:** Prefer `gemini` providers for LLM-based agents as configured in `models`.

### Configuration (`config.yaml`)
- **Port Management:** The application defaults to port `5000`. Respect the `port` field in `config.yaml`.
- **Database:** The primary data store is configured via `database_dsn`. Always use the configured DSN rather than hardcoding paths.
- **Static Files:** Use the `wwwroot/` directory for any static assets served by the framework.



## Workflow Mandates
1. **Research First:** Before modifying the agentic configuration, understand the existing tool definitions and agent hierarchies in `agentic.yaml`.
2. **Surgical Edits:** When updating `agentic.yaml` or `config.yaml`, use precise `replace` operations to avoid overwriting unrelated configurations.
3. **Validation:** After any change to Go code, run `go build .` to ensure compilation success. If possible, verify agent behavior by checking the logs or running integration tests.
4. **No Secrets:** Never commit API keys or credentials. Use environment variables if secrets are required by the framework.
