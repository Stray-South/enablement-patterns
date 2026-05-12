---
title: "Pattern 05: The AI Use Case Register"
slug: use-case-register
tags:
  - governance
  - intake
  - assessment
  - risk-tiering
date_added: 2026-05-12
date_updated: 2026-05-12
status: stubbed
---

# Pattern 05: The AI Use Case Register

> **Status: Stubbed.** Full pattern coming in Week 3. See `PLANS.md`.

## Anchor

The Use Case Register is the structured intake artifact produced by Stage 1 of the Four-Stage Engagement Pipeline (Pattern 01). Every AI use case under consideration in an enterprise becomes one row in the register, with fields covering purpose, data, model, risk tier, controls, sign-offs, status, and next review date.

The register is the asset that turns an Assessment-stage workshop into an enabled team. Compliance teams want it. Audit teams want it. The team running the use case wants it because it gives them a single place to reference what they committed to.

This pattern ships as two artifacts: a Notion-template export (for teams using Notion as their compliance system of record), and a JSON-schema-validated CLI that generates a fresh register entry, validates an existing one against the schema, and produces a status summary report. Two artifacts, one pattern. Readable to non-technical buyers, demonstrably engineered for technical ones.

## Coming when

Week 3 per `PLANS.md`.

## Related

- Pattern 01 (Four-Stage Pipeline): Intake stage uses this artifact
- Pattern 02 (Regulatory Translation): Risk tier field aligns with EU AI Act risk categorization
- NIST AI RMF: Govern function maps to register fields
