---
title: "Pattern 02: Translating Regulatory Requirements into Product Features"
slug: regulatory-translation
tags:
  - regulated-domain
  - eu-ai-act
  - colorado-sb-205
  - compliance
  - hitl
date_added: 2026-05-12
date_updated: 2026-05-12
status: draft
---

# Pattern 02: Translating Regulatory Requirements into Product Features

**Convert regulatory obligations (EU AI Act, Colorado SB-205, sector-specific rules) into named product features built into the system, not separate compliance modules bolted on at the end.**

## Why this exists

There is a way the regulatory conversation usually goes in an enterprise AI deployment. Legal flags a regulation. Engineering says "we'll add a compliance layer." Six months later, the compliance layer is a quarterly checklist that nobody trusts and the auditors hate. The system shipped without the regulatory requirement actually being satisfied, because the requirement was treated as something separate from the product instead of something the product is.

This pattern is about preventing that.

The move is to read the regulation carefully, identify the specific operational requirements it imposes, and then build those requirements as product features the system cannot function without. Signed audit receipts. Kill switches. Human-in-the-loop approval gates. Confidence thresholds. Logging that produces evidence rather than telemetry. The regulation does not get a separate layer. The regulation shapes the system.

When you do this well, the system becomes easier to ship into regulated contexts than systems that treat compliance as an afterthought, because the customer's auditor can see the requirement being satisfied at the product level. You stop having the "is this compliant?" conversation and start having the "show me where the receipt is signed" conversation. The second conversation is much shorter.

This pattern is most concretely applicable to **EU AI Act Article 14 (human oversight) and Article 15 (accuracy, robustness, and cybersecurity)**, with the Article 12 logging obligation as the bridge between them. It also maps cleanly to Colorado SB-205 (effective February 2026), which is the most comprehensive US-state-level analog.

## The pattern

The work breaks into four moves: read, decompose, build, prove.

### Move 1: Read

Read the actual regulation text, not the summaries. For the EU AI Act, this means the official consolidated text. For Colorado SB-205, this means the bill as enacted. Summaries written by vendors are wrong in ways that matter. Specifically, vendor summaries tend to overstate flexibility and understate the specific operational requirements imposed by named articles.

For each regulation in scope, build a working table of obligations:

| Regulation | Article | Obligation | Triggers When | Failure Cost |
|------------|---------|-----------|---------------|--------------|
| EU AI Act | Art. 14 | Human oversight measures | High-risk AI system in production | Up to 7% global revenue |
| EU AI Act | Art. 15 | Accuracy, robustness, cybersecurity | High-risk AI system in production | Up to 7% global revenue |
| EU AI Act | Art. 12 | Automatic recording of events | High-risk AI system throughout lifecycle | Part of conformity assessment |
| Colorado SB-205 | C.R.S. § 6-1-1701 | Reasonable care duty | Algorithmic discrimination risk in consequential decision | Civil penalty + private right of action |

This is not a comprehensive list. It is the seed list. Each regulation has many articles; you read all the ones that plausibly apply to your system.

### Move 2: Decompose

Take each obligation and decompose it into the specific operational requirements it imposes. For EU AI Act Article 14, the actual text requires that "high-risk AI systems shall be designed and developed in such a way... that they can be effectively overseen by natural persons." Decomposed into operational requirements:

- A human in a defined role must be able to inspect what the system is doing
- That human must be able to interpret the output (which requires the output be in a form they can read)
- That human must be able to intervene (which requires a "stop" mechanism that actually works)
- That human must be able to override the output (which requires the system to accept override input)
- The system must "remain operable" even when the human has interrupted it (which means stateful pause, not crash)

Each of those decomposed requirements is now a product feature. Not a compliance checklist item. A feature.

For Article 15, the text requires "appropriate level of accuracy, robustness, and cybersecurity." Decomposed:

- Accuracy metrics must be defined, measured, and reported
- Robustness against adversarial inputs must be tested and documented
- Cybersecurity measures must be appropriate to the risk
- All three must be "consistent throughout the lifecycle"

That last word is the key one. "Throughout the lifecycle" means the metrics are not measured once. They are measured continuously, with logs that can be inspected.

### Move 3: Build

Build the decomposed requirements as features. The features are not optional. The features cannot be disabled by configuration. The features are the system.

Here is what this looks like in practice for EU AI Act Articles 12, 14, and 15:

**For Article 14 (human oversight):**
- A `human_review_required` state in the agent state machine, triggered by named conditions (confidence below threshold, action category in restricted list, customer-flagged decision categories)
- A reviewer UI that surfaces the system's current state, its proposed action, and its reasoning, with a one-click intervention path
- A kill switch that puts the agent in `paused` state without losing context, allowing the human to resume after override
- A logged record of every human review, including who reviewed, what the system proposed, what the human decided, and the reason if they overrode

**For Article 15 (accuracy, robustness, cybersecurity):**
- A continuous evaluation harness that runs the agent against a held-out test set on every model update
- Adversarial test suites that include prompt injection, jailbreak attempts, and out-of-distribution inputs, run on a defined cadence
- Cybersecurity hardening at the agent execution boundary (ephemeral sandboxes, capability tokens, no persistent secrets in agent context)
- Metrics dashboards visible to the customer, not just the vendor

**For Article 12 (logging):**
- Signed, hash-chained event logs covering every agent action, decision, and human intervention
- Logs preserved per the retention requirements of the regulation
- Logs queryable by the customer's compliance team, not just by the vendor

Each of these is a feature that the customer can see, test, and verify. None of them is a "compliance module."

### Move 4: Prove

The final move is producing the evidence that the requirement is satisfied. This is not the same as having the feature. The feature must produce inspectable evidence.

For each feature, define the evidence artifact:
- For human oversight, the evidence is the human review log
- For accuracy, the evidence is the eval results dashboard
- For robustness, the evidence is the adversarial test report
- For logging, the evidence is the signed log chain itself

Hand the evidence artifacts to the customer's compliance team on day one of the engagement. Do not wait for them to ask. Customers that have been through audits before know that being handed the evidence proactively is the strongest possible signal of vendor maturity.

## Runnable artifact

This directory contains three templates:

- `risk-assessment-template.md`: A two-page risk assessment template aligned to EU AI Act Article 9 risk management requirements and Colorado SB-205 algorithmic impact assessment requirements
- `technical-documentation-template.md`: The Annex IV technical documentation structure required for EU AI Act conformity assessment, in a fillable format
- `hitl-eval-spec.yaml`: A specification for evaluating whether a human-in-the-loop gate is actually functioning as Article 14 requires, with measurable criteria

See each file for usage instructions.

## Eval section

The hardest part of this pattern is knowing whether the regulatory translation actually works. A feature that claims to satisfy Article 14 but does not stop a determined model from acting unilaterally has not actually satisfied Article 14.

The eval pattern for regulatory features is:

1. **Specify the requirement as a falsifiable test.** For Article 14: "When the agent encounters a decision in the restricted category list and a human is not available to review, the agent must not act." This is testable.

2. **Build the test cases.** A set of inputs that should trigger the restricted-category response, paired with a state in which no human is available.

3. **Run the test.** Confirm that the agent does not act, with a measurable error code or state transition.

4. **Run adversarial variants.** Test cases where the input is designed to make the model want to act anyway. If the agent acts in any adversarial case, the feature has failed.

5. **Document the pass rate, document the failures, fix the failures, re-test.**

The `evals/regulatory-translation/` directory contains a working example for the Article 14 test case, including the test set, the judge, and a sample report. This is what proves the pattern actually wins.

## Named failure modes

**`REG_TRANS_FAILURE_VENDOR_SUMMARY`**: Team built the feature against a vendor summary of the regulation rather than the regulation text. Action: re-read the actual regulation, identify the gap, rebuild the feature.

**`REG_TRANS_FAILURE_OPTIONAL_FEATURE`**: The regulatory feature can be disabled via configuration. Action: remove the configuration path. The feature is not optional.

**`REG_TRANS_FAILURE_NO_EVIDENCE`**: The feature exists but produces no inspectable evidence that the regulatory requirement is satisfied. Action: add the evidence artifact. A feature without evidence is not compliance, it is a hope.

**`REG_TRANS_FAILURE_AUDIT_LAYER`**: Team built compliance as a separate audit layer that runs after the agent acts. Action: move the requirement into the agent's action path so non-compliance is not possible, rather than detected.

**`REG_TRANS_FAILURE_OVERRIDE_BYPASS`**: Article 14 human override exists in the UI but does not actually stop the agent from completing the action. Action: confirm that override is a hard stop, not a request. Test with adversarial inputs.

## Field report sidebar

**Engagement:** Large regulated enterprise preparing for EU AI Act Article 14/15 enforcement in August 2026. Multiple operating subsidiaries with different AI maturity. Names withheld per engagement contract.

**Pattern observation:** Most teams entered this engagement believing they had compliance covered because their vendor told them so. The first move that changed the conversation was a clause-by-clause walkthrough of Article 14 against the actual deployed system. In every case, the team had features that "supported human oversight" but did not satisfy the specific operational requirements when read carefully. Once the gap was visible, teams moved quickly. The pattern that worked was: read the article, decompose it, walk through the deployed system one decomposed requirement at a time, flag the gaps with specific test cases that would fail. Two weeks of this conversation, per operating subsidiary, produced a working remediation plan in each case.

**Specific observation:** The customer's compliance team consistently appreciated being given the evidence artifacts up front. The signal of vendor maturity that mattered most was not the slide deck or the security review. It was being handed a signed audit log on day one and being told "here is where you can verify any claim we make."

**What I would do differently:** Build the eval harness for the regulatory features earlier. The first version of this pattern relied on manual confirmation that features worked. A test suite that runs on every change would have caught two regressions that I had to fix in production. The lesson: regulatory features need evals at the same maturity level as the underlying AI system, not lower.

## Cross-references

- **Pattern 01 (Four-Stage Engagement Pipeline)**: Assessment stage uses this pattern when the use case is high-risk under EU AI Act categorization
- **Pattern 03 (A-Team / B-Team Multi-Agent Review Protocol)**: The review protocol is itself a feature satisfying Article 14
- **Pattern 05 (Use Case Register)**: The Intake artifact captures risk tier preliminary classification

## Further reading

- EU AI Act consolidated text: official EUR-Lex publication
- Colorado SB-205: full text at the Colorado General Assembly website
- NIST AI Risk Management Framework (AI RMF 1.0), useful structural reference for the decomposition move
- Stanford HAI's AI Index Report (relevant year), context on regulatory landscape

## A note on scope

This pattern focuses on EU AI Act Articles 12, 14, and 15 because those are the articles most likely to apply to enterprise-deployed AI systems and the articles whose obligations translate most directly into product features. The full Act has many more obligations (data governance under Article 10, technical documentation under Article 11, conformity assessment under Article 43, post-market monitoring under Article 72, and others). Each of those obligations admits the same four-move pattern: read, decompose, build, prove.

If your system is in a regulated context not covered by the EU AI Act or Colorado SB-205 (HIPAA-covered, FFIEC-supervised, FDA-regulated, etc.), the same pattern applies. The regulation changes; the four moves do not.
