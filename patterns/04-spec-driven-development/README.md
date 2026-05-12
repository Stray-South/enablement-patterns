---
title: "Pattern 04: Spec-Driven Development with AI Partners"
slug: spec-driven-development
tags:
  - claude-code
  - context-engineering
  - workflow
  - spec-first
date_added: 2026-05-12
date_updated: 2026-05-12
status: stubbed
---

# Pattern 04: Spec-Driven Development with AI Partners

> **Status: Stubbed.** Full pattern coming in Week 3. See `PLANS.md`.

## Anchor

The shift from "prompt engineering" to "context engineering" (named by Gartner as the breakout AI capability of 2026) requires a different workflow than typing prompts into a chat box. The workflow that actually works at production scale is spec-driven: write the specification first, then have AI partners execute against it, with verification checkpoints in between.

This pattern documents the specific spec-driven workflow used to build this repo, the WESUMN platform, and the six-repository protocol stack at github.com/Stray-South. It includes the CLAUDE.md and PLANS.md conventions (mirroring Anthropic and OpenAI's published patterns), the verification pattern, and the specific places where AI partners are reliably useful versus the places where they will produce confident-but-wrong output that a human must catch.

This is also where the "I work with AI coding partners daily" claim from the LinkedIn profile gets made concrete. The repo itself is the demo.

## Coming when

Week 3 per `PLANS.md`.

## Related

- OpenAI Cookbook: "Using PLANS.md for multi-hour problem solving" (October 2025)
- Anthropic's "Context Engineering for Agents" guide (September 2025)
- Beauchemin's AI Enablement Pyramid Level 3
