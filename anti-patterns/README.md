# Anti-patterns

Short essays on AI enablement approaches that fail, and why.

> **Status: Planned.** First three anti-patterns coming in Week 2 per `PLANS.md`.

## What goes here

Each anti-pattern file is a 400–800 word essay covering:

1. **What the anti-pattern looks like in practice** — specific enough that readers can recognize it in their own work
2. **Why it seems reasonable** — anti-patterns persist because they look like the obvious move
3. **What actually happens when you do it** — the failure mode, with field-report evidence where possible
4. **What to do instead** — pointer to the pattern (in this repo or elsewhere) that solves the underlying problem correctly

## Planned anti-patterns

- **The Pilot That Never Ends.** A pilot has succeeded by every metric but the engagement does not Handoff because "we want to be sure." Eventually the pilot becomes the system, with no operational owner and no remediation budget.

- **The Compliance Checklist.** Regulatory requirements are treated as quarterly checklist items rather than product features. The system is "compliant" according to the checklist and would fail any auditor who reads the regulation.

- **The AI Champion Handoff.** The enthusiastic AI advocate at the customer becomes the Handoff owner. Six months later they have moved teams, and the system has no operational owner.

- **The Vendor-Summary Trap.** Team builds against a vendor summary of a regulation rather than the regulation text. Discovers the gap in production.

- **The Multi-Agent Orchestrator Vibe.** Team builds a multi-agent orchestrator because multi-agent feels more impressive than single-agent. The orchestrator hides where errors come from and makes evals harder.

## Format

Anti-pattern files live at `anti-patterns/NN-slug.md` and use the same front matter convention as pattern files. They are deliberately shorter than patterns; an anti-pattern is a warning, not a playbook.
