---
title: "Pattern 07: AuDHD-First Defaults as Structural Constraint"
slug: audhd-first-defaults
tags:
  - design-philosophy
  - accessibility
  - meta
  - structural-constraint
date_added: 2026-05-12
date_updated: 2026-05-12
status: stubbed
---

# Pattern 07: AuDHD-First Defaults as Structural Constraint

> **Status: Stubbed.** Full pattern coming in Week 4. See `PLANS.md`.

## Anchor

This pattern is the design-philosophy meta-pattern that disciplines every other pattern in this repo. AuDHD (autistic + ADHD cognitive profile) is treated as a first-class structural constraint, not an accommodation toggle, not an optional theme.

The specific defaults: no streaks, no loss-framing, no auto-advance, no auto-dismiss errors, no animations over 200ms, decision headers on every page, skip-always navigation, no asks for attention the user did not consent to give. The pattern is short. It does not need many words. What it needs is the discipline of being applied to every design decision rather than added at the end.

The full pattern file will show three concrete examples of how AuDHD-First Defaults shaped the design of patterns elsewhere in this repo: the Four-Stage Pipeline (Pattern 01, where stages have explicit stopping points so the operator can pause without losing context), the Use Case Register (Pattern 05, where fields are scoped to one decision per row), and the A-Team / B-Team Review Protocol (Pattern 03, where handoffs between agents externalize all state).

## Coming when

Week 4 per `PLANS.md`.

## Related

- Pattern 06: The operational constraints that follow from this philosophy
- WCAG 2.2 AA: The accessibility baseline this pattern extends
- WESUMN platform: AuDHD-first defaults are enforced at the product level
