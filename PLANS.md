# PLANS.md

Current multi-hour work plan for `enablement-patterns`. This file mirrors the [OpenAI Cookbook PLANS.md convention](https://cookbook.openai.com/examples/codex/plans_md) for structuring multi-session work that an AI partner can pick up where the human left off.

## Current goal

Ship the spine of the repo plus the two lead patterns (Pattern 01: Four-Stage Engagement Pipeline; Pattern 02: Translating Regulatory Requirements into Product Features) within one week. The remaining six patterns ship over the following three weeks.

## Status as of repo creation

| File | Status | Owner | Notes |
|------|--------|-------|-------|
| `README.md` | ✅ Done | Logan | Repo front page, 60–90 lines |
| `CLAUDE.md` | ✅ Done | Logan | Agent instructions |
| `PLANS.md` | ✅ Done | Logan | This file |
| `registry.yaml` | ✅ Done | Logan | Pattern manifest |
| `LICENSE` | ✅ Done | Logan | Apache 2.0 + CC BY 4.0 |
| `patterns/01-four-stage-pipeline/` | ✅ Draft | Logan | Lead pattern, full content |
| `patterns/02-regulatory-translation/` | ✅ Draft | Logan | Second lead pattern, full content |
| `patterns/03-ateam-bteam-review/` | 🚧 Stubbed | Logan | Anchor paragraph only |
| `patterns/04-spec-driven-development/` | 🚧 Stubbed | Logan | Anchor paragraph only |
| `patterns/05-use-case-register/` | 🚧 Stubbed | Logan | Anchor paragraph only |
| `patterns/06-cognitive-load-protections/` | 🚧 Stubbed | Logan | Anchor paragraph only |
| `patterns/07-audhd-first-defaults/` | 🚧 Stubbed | Logan | Anchor paragraph only |
| `patterns/08-self-serve-doc-hubs/` | 🚧 Stubbed | Logan | Anchor paragraph only |
| `patterns/09-eight-pillar-playbook/` | ✅ Complete | Logan | Full content, eight pillars, diagnostic artifact |
| `mcp-servers/notion-server/` | 📋 Planned | Logan | Week 2 |
| `evals/` | 📋 Planned | Logan | One calibrated judge per pattern that admits one |
| Long-form essay on regulatory translation | 📋 Planned | Logan | Week 2, published on straysouth.com |
| Recorded demo of Four-Stage Pipeline | 📋 Planned | Logan | Week 3 |

## Week 1 (current week)

**Goal:** Ship the spine + Patterns 01 and 02 in full. Make the repo publicly visible.

- [x] Build directory structure
- [x] Write `README.md`, `CLAUDE.md`, `PLANS.md`, `registry.yaml`
- [x] Draft Pattern 01: Four-Stage Engagement Pipeline (full content)
- [x] Draft Pattern 02: Translating Regulatory Requirements into Product Features (full content)
- [x] Stub Patterns 03–08 with anchor paragraphs
- [ ] Loganize the prose in Patterns 01 and 02 (voice pass)
- [ ] Add one diagram to Pattern 01 (the four-stage workflow)
- [ ] Push to github.com/Stray-South/enablement-patterns
- [ ] Set GitHub topics: `ai-enablement`, `forward-deployed-engineer`, `developer-relations`, `llm-evals`, `agent-engineering`, `context-engineering`, `mcp-server`, `eu-ai-act`, `playbooks`, `runbooks`

## Week 2

**Goal:** Build the MCP server. Ship the long-form essay.

- [ ] Build `mcp-servers/notion-server/` as a working MCP server connecting Notion to Claude
- [ ] Document the server's setup, tools, and use cases in its README
- [ ] Write the long-form essay: "Translating EU AI Act Article 14 into a Claude Agent: a Field Guide" (~5,000 words)
- [ ] Publish essay on straysouth.com or as Substack with custom domain
- [ ] Link the essay from Pattern 02

## Week 3

**Goal:** Complete Patterns 03, 04, 05. Record the demo.

- [ ] Draft Pattern 03: A-Team / B-Team Multi-Agent Review Protocol (full content)
- [ ] Draft Pattern 04: Spec-Driven Development with AI Partners (full content)
- [ ] Draft Pattern 05: The AI Use Case Register (full content)
- [ ] Record 8–12 minute screen capture demo of the Four-Stage Pipeline in action
- [ ] Add captured Claude Code session to Pattern 04 as supporting artifact

## Week 4

**Goal:** Complete Patterns 06, 07, 08. Submit one conference talk.

- [ ] Draft Pattern 06: Cognitive Load Protections in Agent UX (full content)
- [ ] Draft Pattern 07: AuDHD-First Defaults as Structural Constraint (full content)
- [ ] Draft Pattern 08: Self-Serve Documentation Hubs (full content)
- [ ] Submit talk proposal to AI Engineer Summit, MLOps Community Conference, or DevRelCon

## Open questions

1. **Sanitization protocol for field reports.** What level of detail can be shared about the regulated utility engagement without breaching contract? Likely: company names removed, employee counts kept (public information), specific platforms mentioned only at category level (not vendor names). Verify with engagement contract before publishing first field report.

2. **MCP server choice.** Notion or Asana? Notion has wider audience appeal; Asana shows project-management depth. Default: Notion. Revisit if Asana would surface a more distinctive demo.

3. **License clarity.** Confirm Apache 2.0 for code + CC BY 4.0 for prose is the right split. Some practitioners use Apache 2.0 for everything to reduce friction.

## What we are NOT doing

To preserve focus, these items are explicitly out of scope:

- A custom static site or marketing landing for the repo (use GitHub Pages defaults only)
- Twitter/X content calendar (per research findings, low signal-per-hour)
- A YouTube channel (single recorded demo is enough)
- Translation into other languages
- A separate book or course (the patterns repo is the artifact)

## How to use this file

When picking up this work after time away, read this file first. Update the status column. Cross items off as they ship. Add open questions as they arise.

This file is a living plan. If it's wrong, fix it. If a pattern's scope changes, update the relevant week's checklist.
