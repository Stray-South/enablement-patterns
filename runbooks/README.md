# Runbooks

Operational checklists. The artifacts that get handed to the operational owner at Handoff (Stage 4 of Pattern 01).

> **Status: Planned.** First runbook templates coming in Week 3. See `PLANS.md`.

## Why these matter

The Four-Stage Engagement Pipeline (Pattern 01) names the Handoff stage's deliverables. The most operationally critical of those deliverables is the runbook set: a normal-operations runbook, a failure-modes runbook, and an escalation runbook. Without these three, Handoff is not actually Handoff. The Enablement function will keep getting paged.

## Planned runbook templates

- **`normal-ops.md`** — Daily / weekly / monthly checklist for an operational owner of an AI system in production. What to monitor, what good looks like, what triggers concern.
- **`failure-modes.md`** — Named failure modes (drawn from the relevant patterns), what they look like in practice, the first three steps to triage each.
- **`escalation.md`** — When to escalate, to whom, with what information, on what timeline. Includes the test for whether escalation actually works (called "the 3 AM test": at 3 AM on a Saturday, does this escalation path actually reach a human who can act?).

## Format

Runbooks are deliberately terse. A runbook that someone has to read carefully under stress has failed at being a runbook. The format is:

1. **One-line operational claim** at the top of the file (what this runbook covers)
2. **Checklist or decision tree** — the actionable content, scannable
3. **Definitions section** — at the bottom, for any term that needs explanation
4. **Last-updated date** — runbooks decay; the date is the test of currency

## A note on customization

Templates in this directory are starting points. Every engagement will need to customize them to the specific system being handed off. The template is the scaffolding, not the final artifact.
