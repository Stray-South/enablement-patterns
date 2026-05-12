---
title: "Pattern 03: A-Team / B-Team Multi-Agent Review Protocol"
slug: ateam-bteam-review
tags:
  - multi-agent
  - quality-gate
  - evals
  - review-protocol
date_added: 2026-05-12
date_updated: 2026-05-12
status: stubbed
---

# Pattern 03: A-Team / B-Team Multi-Agent Review Protocol

> **Status: Stubbed.** Full pattern coming in Week 3. See `PLANS.md`.

## Anchor

Multi-agent orchestration as a category has become saturated and frequently vibe-coded. This pattern is something different: a review-not-runtime protocol that uses multiple AI agents adversarially as a quality gate, not as a runtime framework.

The core idea: one agent (the A-team) builds. A separate agent instance with no context from the build (the Claude B-team) verifies. A third agent of a different model family (the GPT B-team) does adversarial review. Each agent has a defined role, defined output format, and defined stopping points. The protocol is a quality gate that catches errors before they ship, not an orchestrator that hopes multiple models will be smarter than one.

The full pattern will cover the role definitions, the handoff protocol between A-team and B-teams, token quotas, observability hooks, recovery from runaway behavior, and a TP/TN-validated judge calibration that proves the protocol actually catches errors a single-agent approach would miss.

## Coming when

Week 3 per `PLANS.md`. If you need this earlier, contact ljfreeman83@gmail.com.

## Related

- Bryan Bischof's transition failure matrix
- Anthropic's "Building Effective Agents" essay (December 2024)
- Hamel Husain's evals taxonomy
