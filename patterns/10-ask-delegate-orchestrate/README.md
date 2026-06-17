---
title: "Pattern 10: Ask / Delegate / Orchestrate, an AI Fluency Ladder"
slug: ask-delegate-orchestrate
tags:
  - fluency
  - adoption
  - individual
  - andragogy
  - change-management
date_added: 2026-06-17
date_updated: 2026-06-17
status: draft
---

# Pattern 10: Ask / Delegate / Orchestrate, an AI Fluency Ladder

**A three-rung ladder for moving one non-technical worker from using AI as a smarter search box, to handing AI whole tasks and verifying them, to designing multi-step workflows the AI runs. The individual-level companion to the org-level program in Pattern 09.**

## Why this exists

Most enterprise AI rollouts fail the same way. A company buys licenses, runs a webinar, and waits for adoption that never comes. The tool was never the problem. The problem is that nobody gave people a shared way to think about what to hand an AI, how much to hand it, and when to stop trusting it.

The eight-pillar playbook in Pattern 09 is what an organization builds. This pattern is what a single person climbs. The two are different altitudes of the same work: the program exists to move many individuals up this ladder, and the ladder is the thing the program is trying to produce.

Adults adopt a new tool when three things are true at once. The tool solves a problem they already have, they can try it without looking foolish, and they can see the next step from where they are standing. A single training event satisfies none of those. A ladder satisfies all three, because each rung is a small, safe, obviously useful move from the rung below it. That is the gradual release of responsibility ("I do, we do, you do") that teachers have used for decades, applied to AI.

## The ladder

```
   ┌────────┐      ┌──────────┐      ┌──────────────┐
   │  ASK   │ ───▶ │ DELEGATE │ ───▶ │ ORCHESTRATE  │
   └────────┘      └──────────┘      └──────────────┘
   smarter         whole task,        multi-step
   search box      then verify        workflow you design
```

### Rung 1: Ask

**Definition:** Use AI to get an answer, a draft, or an explanation you then use yourself. You stay in control of the work; the AI is a faster reference.

**What it looks like:** "Summarize this policy in plain language." "What's a clearer way to say this paragraph?" "Explain this error message."

**The skill being built:** Writing a clear request and judging whether the answer is good enough. Prompt literacy in its smallest, safest form.

**The failure mode to teach:** Trusting a confident wrong answer. Rung 1's whole job is teaching people that the AI is a draft, not an oracle.

**Ready for the next rung when:** you stop rewriting the request three times and start getting usable answers on the first or second try.

### Rung 2: Delegate

**Definition:** Hand the AI a complete, bounded task and verify the output before it ships. You own the outcome; the AI does the first pass.

**What it looks like:** "Draft the onboarding email for this role, using this template and these three facts." "Turn these meeting notes into action items with owners." "Review this spreadsheet for formula errors and list what you find."

**The skill being built:** Scoping a task tightly enough that an AI can do it, then verifying without redoing. This is where real time savings start.

**The failure mode to teach:** Skipping verification because the output looks polished. Delegation without a review gate is how errors ship at scale.

**Ready for the next rung when:** you find yourself wanting to chain two delegated tasks together.

### Rung 3: Orchestrate

**Definition:** Design a sequence where AI handles multiple steps, possibly across tools, toward an outcome you defined. You're the director; the AI is the crew.

**What it looks like:** A repeatable workflow where AI pulls data, drafts an analysis, formats it to a standard, and flags anything that needs a human decision, with you owning the design and the review points.

**The skill being built:** Decomposing an outcome into steps, deciding which steps are safe to automate and which require human judgment, and building the checkpoints.

**The failure mode to teach:** Automating a broken process. An orchestrated bad workflow just produces bad results faster. Fix the process first.

**You've arrived when:** other people start asking you to help build their workflows. Those are your next champions, surfacing themselves.

## Runnable artifact

A starter `CLAUDE.md` context file that encodes the ladder for a single team's AI workspace is included at `patterns/10-ask-delegate-orchestrate/CLAUDE.md.template`. It tells the assistant who the team is, what rung they're on, and to nudge them one rung up using their own real tasks rather than generic demos.

## Named failure modes

**`ADO_FAILURE_STUCK_AT_ASK`**: A whole team plateaus at Ask because nobody told them Delegate and Orchestrate exist. Action: model one delegated task from their real work; the rung becomes visible.

**`ADO_FAILURE_DELEGATE_NO_VERIFY`**: People delegate but skip the review gate because output looks polished. Action: make verification a named step, not an afterthought.

**`ADO_FAILURE_ORCHESTRATE_BROKEN_PROCESS`**: A broken manual process gets automated and now fails faster. Action: fix the process before orchestrating it.

**`ADO_FAILURE_FORCED_CLIMB`**: Pushing someone to Orchestrate before they can Delegate. Action: competence before autonomy; meet them at their real rung.

## How this relates to other frameworks

This ladder is a synthesis, not an invention, and it stands on named prior work:

- **Gradual release of responsibility** (Pearson and Gallagher, 1983; Fisher and Frey): the "I do, we do, you do" progression this ladder applies to AI.
- **Anthropic's AI Fluency framework** (Delegation, Description, Discernment, Diligence): the verification discipline at the Delegate rung maps directly to Discernment and Diligence.
- **Microsoft's 2026 Work Trend Index** describes a related individual progression (Author, Editor, Director, Orchestrator), and the term Orchestrate is shared.

The distinctive contribution here is the andragogy framing and the explicit verification gate at Rung 2, aimed at non-technical enterprise workers rather than developers.

## Cross-references

- **Pattern 09 (8-Pillar AI Platform Enablement Playbook)**: the organizational program that exists to move individuals up this ladder
- **Pattern 01 (Four-Stage Engagement Pipeline)**: the Enablement stage delivers this climb to a team
- **Pattern 08 (Self-Serve Documentation Hubs)**: the Handoff artifacts that let people self-serve their way up the rungs

## Further reading

- Pearson and Gallagher (1983) on the gradual release of responsibility
- Anthropic AI Fluency: Framework and Foundations (2025)
