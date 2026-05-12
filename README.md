# enablement-patterns

Repeatable deployment patterns for AI enablement engineers working in regulated enterprise contexts. Field-tested. Eval-validated. Sanitized for public consumption.

I'm Logan Freeman. I run AI enablement engagements at enterprise scale (currently designing AI learning architecture for a large regulated utility company, ~120,000 employees across three operating companies) and I build governance infrastructure for agentic AI systems (WESUMN, at [wesummonit.com](https://wesummonit.com)). This repo is where I publish the patterns I actually use, the failure modes I've actually hit, and the artifacts I'd hand a customer on day one of a new engagement.

## Start here

If you're new to this work, read **[Pattern 01: The Four-Stage Engagement Pipeline](./patterns/01-four-stage-pipeline/)** first. It's the operating system underneath every other pattern in this repo.

If you're navigating an EU AI Act or Colorado SB-205 conversation right now, jump to **[Pattern 02: Translating Regulatory Requirements into Product Features](./patterns/02-regulatory-translation/)**.

## The patterns

| # | Pattern | Tags |
|---|---------|------|
| 01 | [Four-Stage Engagement Pipeline](./patterns/01-four-stage-pipeline/) | `engagement`, `process`, `enterprise` |
| 02 | [Translating Regulatory Requirements into Product Features](./patterns/02-regulatory-translation/) | `regulated-domain`, `eu-ai-act`, `compliance` |
| 03 | [A-Team / B-Team Multi-Agent Review Protocol](./patterns/03-ateam-bteam-review/) | `multi-agent`, `quality-gate`, `evals` |
| 04 | [Spec-Driven Development with AI Partners](./patterns/04-spec-driven-development/) | `claude-code`, `context-engineering`, `workflow` |
| 05 | [The AI Use Case Register](./patterns/05-use-case-register/) | `governance`, `intake`, `assessment` |
| 06 | [Cognitive Load Protections in Agent UX](./patterns/06-cognitive-load-protections/) | `agent-ux`, `accessibility`, `production` |
| 07 | [AuDHD-First Defaults as Structural Constraint](./patterns/07-audhd-first-defaults/) | `design-philosophy`, `accessibility`, `meta` |
| 08 | [Self-Serve Documentation Hubs](./patterns/08-self-serve-doc-hubs/) | `handoff`, `adoption`, `measurement` |
| 09 | [The Eight-Pillar AI Enablement Playbook](./patterns/09-eight-pillar-playbook/) | `strategy`, `governance`, `measurement`, `meta` |

## Why this repo exists

Most AI enablement writing in 2026 is either marketing prose or vendor cookbooks. Neither helps you when you're three weeks into a regulated enterprise deployment and the legal team has just asked what Article 14 actually requires of your agent.

This repo is what I wish existed when I started doing this work. The patterns are named, the failure modes are explicit, and every pattern that can carry a runnable artifact has one. Field reports are sanitized but real.

If you're hiring for AI Enablement, Forward Deployed Engineering, or Developer Advocacy roles and you want to see how I think, the patterns are the answer. The contact info is at the bottom.

## What's in each pattern

Each pattern follows the same shape: a problem statement, a "why this exists" anchor (about 200 words), an architecture or workflow diagram, a runnable artifact (template or code), an eval section showing the pattern wins on some measurable axis, named failure modes, and a field report sidebar drawn from real engagements.

If you want the supporting infrastructure, see:
- [`anti-patterns/`](./anti-patterns/) — short essays on what fails and why
- [`evals/`](./evals/) — calibrated judges for the patterns that admit one
- [`incidents/`](./incidents/) — sanitized postmortems from real engagements
- [`runbooks/`](./runbooks/) — operational checklists, the Handoff artifacts
- [`mcp-servers/`](./mcp-servers/) — real MCP servers wiring Notion and Asana into agents
- [`field-reports/`](./field-reports/) — long-form writeups of engagements

## Contact

ljfreeman83@gmail.com · [linkedin.com/in/loganfreemanai](https://linkedin.com/in/loganfreemanai) · [straysouth.com](https://straysouth.com)

If your team is hiring for AI Enablement, Forward Deployed Engineering, Developer Advocacy, or AI Product Management roles in 2026, my inbox is open.

## License

Patterns, templates, and prose are CC BY 4.0. Code samples are Apache 2.0 unless otherwise noted.
