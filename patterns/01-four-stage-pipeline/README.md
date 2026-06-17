---
title: "Pattern 01: The Four-Stage Engagement Pipeline"
slug: four-stage-pipeline
tags:
  - engagement
  - process
  - enterprise
  - intake
  - assessment
  - handoff
date_added: 2026-05-12
date_updated: 2026-05-12
status: draft
---

# Pattern 01: The Four-Stage Engagement Pipeline

**A repeatable Intake → Assessment → Enablement → Handoff process for engaging any development team or business unit with AI adoption, with named entry criteria, ordered steps, definition of done, and a stopping point at each stage.**

## Why this exists

When you are responsible for AI enablement across multiple teams at the same time, the failure mode is not lack of effort. It is unbounded scope. Every team you talk to has a different starting point, a different appetite, and a different definition of what success looks like. Without structure, you end up running every engagement as a bespoke conversation, which means you can only ever serve a few teams at once, and the quality varies based on how tired you are that week.

The Four-Stage Pipeline solves this by making engagement itself a product. Every team that asks for help enters the same pipeline. Each stage has an entry criterion (what has to be true before you start the stage), an ordered set of steps (what you do during the stage), a definition of done (what has to be true before you exit), and a stopping point (where you'd kill the engagement if the criterion fails).

The stages are: **Intake, Assessment, Enablement, Handoff.** They are sequential. You cannot skip stages. A team in Assessment cannot jump to Enablement until Assessment is complete, even if they're enthusiastic. A team that fails the Assessment exit criterion goes back to Intake or is paused, not pushed forward into Enablement they cannot absorb.

This pattern is the operating system underneath every other pattern in this repo. The Use Case Register (Pattern 05) is the Intake artifact. The Cognitive Load Protections (Pattern 06) shape the Enablement stage. The Self-Serve Documentation Hubs (Pattern 08) are the Handoff deliverable.

## The pipeline

```
   ┌─────────┐     ┌────────────┐     ┌────────────┐     ┌─────────┐
   │ INTAKE  │ ──▶ │ ASSESSMENT │ ──▶ │ ENABLEMENT │ ──▶ │ HANDOFF │
   └─────────┘     └────────────┘     └────────────┘     └─────────┘
        │                │                  │                 │
        │ stop if:       │ stop if:         │ stop if:        │ stop if:
        │ no real        │ wrong tier       │ team can't      │ no owner
        │ business       │ or unsafe        │ absorb or       │ identified
        │ problem        │ use case         │ wrong approach  │
```

Each stage produces specific artifacts that feed the next stage. Each stage has a stopping point that triggers an explicit conversation, not silent drift.

### Stage 1: Intake

**Entry criterion:** A team has reached out with what they think is an AI use case.

**What happens during this stage:**
1. A single 30-minute intake conversation, structured around four questions:
   - What is the business problem you are trying to solve?
   - What does success look like in concrete, measurable terms?
   - Who are the humans on the other end of this system?
   - What happens if the AI gets it wrong?
2. The team fills out the AI Use Case Register entry (see Pattern 05). This includes a preliminary risk tier (low / medium / high / prohibited).
3. The Enablement Lead reviews the entry and either accepts the engagement into Assessment, rejects it, or asks for revision.

**Definition of done:** A signed Use Case Register entry exists with a preliminary risk tier, named stakeholders, and a clearly stated business problem.

**Stopping point:** If after the intake conversation there is no real business problem ("we just want to use AI"), or if the proposed use case maps to a prohibited category under any applicable regulation, the engagement does not proceed. You write a one-paragraph note explaining why and offer the team an alternative entry point (e.g., AI literacy training, or returning when the problem is clearer).

**Failure mode at this stage:** The most common failure is accepting engagements that should have been rejected because the requesting team is influential. Hold the line. The cost of running a bad Assessment is higher than the cost of a difficult Intake conversation.

### Stage 2: Assessment

**Entry criterion:** A signed Intake artifact exists.

**What happens during this stage:**
1. A landscape analysis: what tools does this team already use? What is their current workflow? What data is involved? What constraints (regulatory, security, contractual) apply?
2. A risk assessment: confirm or revise the preliminary risk tier. For high-risk use cases under EU AI Act categorization, this stage gets significantly more rigorous. See Pattern 02.
3. A capability fit check: is the AI capability actually appropriate for this use case, or is the team reaching for a model when a deterministic system would work better?
4. A learning needs assessment: where does this team sit on the AI fluency spectrum, and what do they need to learn before Enablement can succeed?
5. An adoption readiness check: does the team have a real owner, real time allocated, and real authority to make decisions?

**Definition of done:** An Assessment report exists with a confirmed risk tier, a recommended approach (build, buy, partner, or do nothing), named success metrics, and a learning plan.

**Stopping point:** If the risk tier is too high relative to the team's readiness, or if the capability fit check fails (a deterministic system would work better), or if there is no real owner, the engagement is paused. This is not a rejection. It is an acknowledgment that the team needs something before they can succeed, and Enablement is not it.

**Failure mode at this stage:** The most common failure is letting enthusiasm drive past the readiness check. A team that wants AI but does not have an owner or time allocated will burn the engagement out within six weeks. Better to pause than to fail visibly.

### Stage 3: Enablement

**Entry criterion:** A completed Assessment report with stated approach, metrics, and learning plan.

**What happens during this stage:**
1. The learning plan is delivered. This is not training. It is targeted, measured, performance-based capability building. The team learns the specific things they need to learn to operate the system being delivered.
2. The technical work happens in parallel: integration, prompt engineering, evaluation harnesses, governance hooks. Where possible, the technical work is paired with the learning, so the team sees the system being built and develops intuition for it.
3. Regular checkpoints (weekly or bi-weekly) against the named success metrics. These are not status updates. They are go/no-go decisions on the engagement.
4. A pilot phase where the system runs in a limited scope with active monitoring before any general rollout.

**Definition of done:** The system meets the success criteria defined in Assessment, the team can operate it without daily support from the Enablement function, and a Handoff readiness review confirms that the artifacts needed for sustained operation exist.

**Stopping point:** If the system does not meet success criteria after a reasonable iteration window, or if the team cannot absorb the system as designed, the engagement returns to Assessment for a redesign rather than being pushed into Handoff. Forcing Handoff on a system the team cannot operate creates lasting damage to the AI enablement function's credibility.

**Failure mode at this stage:** The most common failure is treating Enablement as a delivery phase rather than a learning phase. The team has to come out of this stage able to operate the system. If they cannot, you have not finished Enablement, regardless of whether the code works.

### Stage 4: Handoff

**Entry criterion:** The system meets success criteria and the team can operate it without daily support.

**What happens during this stage:**
1. The Handoff artifacts are produced. These typically include: a runbook for normal operation, a runbook for failure modes, a measurement dashboard, a documented escalation path, and a named owner. See `runbooks/` directory in this repo for templates.
2. A self-serve documentation hub is stood up. This hub addresses the questions the team is most likely to ask in the first 90 days of operation. See Pattern 08.
3. A formal handoff meeting confirms transfer of operational responsibility. The Enablement function moves to advisory-only.
4. A 90-day check-in is scheduled. The Enablement function does not vanish, but the team owns the system.

**Definition of done:** The team has signed off on operational ownership. The documentation hub is live. The escalation path is tested. The 90-day check-in is on the calendar.

**Stopping point:** If at any point during Handoff it becomes clear that the team cannot actually own the system without ongoing support, the engagement returns to Enablement, not Handoff. There is no Handoff to a team that cannot own.

**Failure mode at this stage:** The most common failure is doing Handoff to the wrong person. The team's enthusiastic AI champion is often not the right Handoff owner. The right owner is the person who will still be doing this job in six months and has the authority to make changes.

## Runnable artifact

The `pipeline-tracker.json` schema in this directory defines a minimal data structure for tracking an engagement through the four stages. A team's status at any point is one record in this format. The companion `tracker.py` CLI generates fresh Intake artifacts and lints existing ones for missing fields.

```bash
# Create a new Intake entry
python tracker.py intake --team "Platform Engineering" --problem "..."

# Validate an existing engagement against the pipeline schema
python tracker.py validate engagements/2026-platform-eng.json

# Generate a status report for all active engagements
python tracker.py status
```

See `pipeline-tracker.json` in this directory for the schema, and `engagements/example.json` for a complete sample record.

## Named failure modes

The pipeline does not prevent failure. It surfaces failure earlier, with named labels, so you can have the right conversation at the right time.

**`PIPELINE_FAILURE_INTAKE_NO_PROBLEM`**: Team enters Intake without a real business problem. Action: do not advance. Offer AI literacy training instead and document the conversation.

**`PIPELINE_FAILURE_ASSESSMENT_NO_OWNER`**: No real owner identified during Assessment. Action: pause engagement until the requesting team identifies a named owner with allocated time and decision authority.

**`PIPELINE_FAILURE_ASSESSMENT_RISK_TIER_MISMATCH`**: Use case is higher risk than the team's readiness. Action: do not advance. Either escalate to a more rigorous governance process or scope the use case down to a tier the team can absorb.

**`PIPELINE_FAILURE_ENABLEMENT_NO_ABSORPTION`**: System works but the team cannot operate it. Action: return to Assessment for capability fit redesign. Do not push to Handoff.

**`PIPELINE_FAILURE_HANDOFF_WRONG_OWNER`**: Handoff is happening to the wrong person (the AI champion rather than the operational owner). Action: identify the operational owner before completing Handoff. Re-run the Handoff meeting if necessary.

## Field report sidebar

**Engagement:** Large regulated enterprise, three operating subsidiaries, mixed AI fluency across business units. Names withheld per engagement contract.

**Pattern observation:** The most useful thing the Pipeline did in this engagement was create a shared vocabulary across operating subsidiaries. Before the pipeline, "AI enablement" meant something different to each subsidiary, which made cross-subsidiary coordination impossible. After the pipeline, every conversation referenced specific stages, specific artifacts, and specific stopping points. The cross-subsidiary coordination problem became tractable.

**Specific observation:** The Intake conversation was where most of the value got created, not the Enablement stage. Teams that did a rigorous Intake almost always succeeded in Enablement. Teams that skipped or rushed Intake failed predictably in Enablement, regardless of how good the technical work was. If you can only do one stage well, do Intake.

**What I would do differently:** Build the Assessment templates earlier and lighter. I made the first Assessment too heavy and several teams stalled at that stage. The Assessment should fit on two pages, not ten. Anything longer is a research project pretending to be an assessment.

## Cross-references

- **Pattern 02 (Regulatory Translation)**: How the Assessment stage handles EU AI Act and Colorado SB-205 high-risk categorization
- **Pattern 05 (Use Case Register)**: The Intake artifact this pipeline produces
- **Pattern 06 (Cognitive Load Protections)**: Constraints on what Enablement can ask of a team
- **Pattern 08 (Self-Serve Documentation Hubs)**: The Handoff deliverable

## Further reading

- Maxime Beauchemin's "AI Enablement Pyramid" framework (2025)
- Hamel Husain's writing on the Three Levels of Evaluation (hamel.dev/blog/posts/evals/), relevant to Assessment-stage rigor
- The ADDIE instructional design framework (Analyze, Design, Develop, Implement, Evaluate), the pipeline is influenced by but does not replicate ADDIE
