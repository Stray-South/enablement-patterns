# Incidents

Sanitized postmortems from real engagements.

> **Status: Planned.** First incident postmortem coming after engagement contract review confirms permitted scope. See `PLANS.md`.

## Why these matter

The single rarest item in AI Enablement / Forward Deployed Engineer portfolios is a writeup of what actually went wrong, in a specific case, with specific mitigations. Hiring managers at Anthropic, OpenAI, and the major AI infrastructure companies specifically ask for "field feedback that helps Research and Product understand where the models succeed and where they can improve."

This directory is where that lives.

## Sanitization protocol

Every incident postmortem in this directory follows the same sanitization rules:

1. **No client names.** Operating-company names, vendor names, and individual employee names are removed or genericized.
2. **No specific platforms by vendor name.** If the incident involved "the team's CRM," that's the level of specificity used.
3. **No specific data examples.** If a model misbehaved on a particular input, the input is paraphrased or replaced with a structurally similar synthetic example.
4. **Public information remains public.** Aggregate employee counts (if publicly disclosed) and regulatory regimes can be named, because they are already known.

Engagement contract review is run on every incident before it is published.

## Format

Each incident file follows this structure:

1. **What happened** — one-paragraph summary, sanitized
2. **Timeline** — sequence of events, sanitized
3. **Root cause** — the actual underlying cause, not the proximate trigger
4. **What worked in the response** — explicit, because most postmortems only document failures
5. **What did not work** — explicit, with names of failure modes
6. **What I would do differently next time** — concrete changes
7. **Pattern implications** — which patterns in this repo were validated, invalidated, or expanded by this incident

## A note on what this is for

This directory is not a confession. It is professional practice. Engineers and operators who do not write postmortems are not learning from their work. Engineers and operators who write postmortems but do not publish them are not letting the field learn from their work.

If you are a hiring manager or potential customer reading this, the absence of a postmortem in this directory at the moment you visit does not mean nothing has ever gone wrong. It means the sanitization review for the postmortem in queue has not yet been completed.
