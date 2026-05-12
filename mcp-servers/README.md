# MCP Servers

Working MCP (Model Context Protocol) servers wiring enterprise systems into Claude agents.

> **Status: Planned.** First working server (`notion-server/`) ships in Week 2. See `PLANS.md`.

## Why these matter

MCP became the de facto integration standard for AI agents in 2025. By May 2026, Anthropic, OpenAI, Cohere, Modal, and most major AI infrastructure providers ship MCP-shaped examples and cookbooks. A practitioner portfolio in 2026 that does not include at least one working MCP server is missing the clearest signal of "this candidate has actually done the work."

This directory will contain at least one working MCP server, with a complete README explaining what it does, how to set it up, what tools it exposes, and how to use it in an agent workflow.

## Planned servers

- **`notion-server/`** — Connects a Notion workspace to a Claude agent. Exposes tools for reading pages, searching the workspace, updating page properties, and creating new pages from templates. The primary use case demonstrated: turning the AI Use Case Register (Pattern 05) from a static Notion template into an agent-accessible governance system.

- **`asana-server/`** — Possible follow-up depending on which integration produces a more distinctive demo.

## Format

Each MCP server directory contains:

- `README.md` — what the server does, setup instructions, tool documentation
- `server.py` (or equivalent) — the working implementation
- `CLAUDE.md` — example agent instructions that use the server's tools
- `example-session.md` — a captured Claude Code session showing the server in use
- `requirements.txt` or `pyproject.toml` — dependencies

## A note on production readiness

The MCP servers in this directory are working examples, not production-grade software. They demonstrate the integration pattern and can be extended into production systems, but they are not packaged or maintained as products. The production-grade equivalent in Logan's commercial work lives in the WESUMN platform.
