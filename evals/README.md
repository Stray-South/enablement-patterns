# Evals

Calibrated LLM-as-judge implementations for the patterns in this repo that admit a measurable eval.

> **Status: Planned.** First working eval ships in Week 2 alongside the MCP server. See `PLANS.md`.

## Why these matter

A pattern that claims to win on some metric and does not have a working eval is just a claim. The evals in this directory are what turn the patterns from prose into testable artifacts.

The methodology follows Hamel Husain's three-level eval taxonomy (unit tests → human + model eval → A/B testing), with the calibration step that Hamel and Shreya Shankar have pushed hard since 2025: hand-label ~100 traces, open-code categories, axial-code the judges, validate the judge against held-out human labels with measured agreement rate (TP/TN, ideally above 90%).

## Planned evals

| Eval | Pattern | Status |
|------|---------|--------|
| `regulatory-translation/article-14-hitl/` | Pattern 02 | Planned, Week 2 |
| `ateam-bteam/review-protocol-effectiveness/` | Pattern 03 | Planned, Week 3 |
| `use-case-register/risk-tier-classification/` | Pattern 05 | Planned, Week 3 |

## Format

Each eval directory contains:

- `README.md` — what this eval measures and how to run it
- `test_set.json` — labeled examples used for both calibration and ongoing evaluation
- `judge.py` — the LLM-as-judge implementation
- `calibration.md` — agreement rate against held-out human labels, with date and methodology
- `report-latest.json` — most recent eval run output

## Anti-pattern

The most common eval anti-pattern in 2026 is shipping an LLM-as-judge implementation without calibration. A judge that has not been validated against human labels is a confident guess. The patterns in this repo will not include an eval until the eval is calibrated.
