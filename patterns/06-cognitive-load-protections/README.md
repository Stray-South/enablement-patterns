---
title: "Pattern 06: Cognitive Load Protections in Agent UX"
slug: cognitive-load-protections
tags:
  - agent-ux
  - accessibility
  - production
  - interruption-recovery
date_added: 2026-05-12
date_updated: 2026-05-12
status: stubbed
---

# Pattern 06: Cognitive Load Protections in Agent UX

> **Status: Stubbed.** Full pattern coming in Week 4. See `PLANS.md`.

## Anchor

Most production agent UIs are built on three assumptions that fail in the real world: that the user has continuous attention, working memory between sessions, and the cognitive capacity to recover gracefully when interrupted. Strip those assumptions away and design for users who lack any of them, and the resulting interface is better for everyone (the classic curb-cut effect).

This pattern documents the specific structural constraints that produce agent UX which holds up under real-world cognitive conditions. Externalized state. Single-source-of-truth defaults. Interruption-recovery built into every long-running operation. No auto-dismiss errors. No animations that consume attention budget the user did not consent to spend. Decision headers on every page that name what the page is for and what action it expects.

The pattern is connected to but distinct from Pattern 07 (AuDHD-First Defaults). Pattern 07 is the design philosophy. Pattern 06 is the specific operational constraints that follow from it.

## Coming when

Week 4 per `PLANS.md`.

## Related

- Pattern 07: The design philosophy this pattern operationalizes
- Pattern 01: Cognitive Load Protections shape what Enablement-stage delivery can ask of users
- WCAG 2.2 AA: The accessibility baseline this pattern extends
