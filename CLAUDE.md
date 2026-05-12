# CLAUDE.md

Agent instructions for working in the `enablement-patterns` repo.

## Project context

This is a public portfolio repo of AI enablement patterns, owned by Logan Freeman (github.com/Stray-South). The audience is hiring managers and practitioners at AI infrastructure companies (Anthropic, Modal, Vercel, GitLab, MongoDB, Caylent, Databricks, etc.), regulated-enterprise customers, and other AI Enablement Engineers / Forward Deployed Engineers / Developer Advocates.

The repo is not WESUMN marketing. It is not academic. It is practitioner writing in the lineage of Hamel Husain's hamel.dev, Eugene Yan's eugeneyan.com, and the Anthropic / OpenAI cookbooks.

## File structure

```
enablement-patterns/
├── README.md                    # Repo front page, 60–90 lines
├── CLAUDE.md                    # This file
├── PLANS.md                     # Current multi-hour work plan
├── registry.yaml                # Manifest of all patterns
├── LICENSE                      # Apache 2.0 for code, CC BY 4.0 for prose
├── patterns/                    # The eight numbered patterns
├── anti-patterns/               # Short essays on what fails
├── evals/                       # Calibrated judges for patterns
├── incidents/                   # Sanitized postmortems
├── runbooks/                    # Operational checklists
├── mcp-servers/                 # Real MCP servers
└── field-reports/               # Long-form sanitized engagement writeups
```

## Voice and writing rules

When generating or editing prose in this repo, follow these rules strictly.

**Do:**
- Open every pattern file with stakes, conflict, and decision (the screenwriter's three-beat opening)
- Use Logan's voice: contractions, short sentences punching long ones, occasional self-aware honesty, specific images over abstract claims
- Name failure modes explicitly with constants or constants-like phrasing
- Cite specific regulations by article number when relevant (EU AI Act Article 14, Article 15; Colorado SB-205)
- Use real metrics with units when they exist
- Cross-link to other patterns by relative path

**Don't:**
- Use em-dashes. Use commas, periods, or semicolons. Em-dash density is a recognized LLM-content signal in 2026.
- Use "leveraged," "orchestrated," "spearheaded," "navigated," "bridge the gap," "intersection of," "passionate about," or "proven track record"
- Use parallel-structure constructions like "X isn't Y, it's Z"
- Repeat the same callback phrase across multiple sections
- Reference Logan's MFA / film background more than once in the entire repo (it appears in the "About" page only)
- Write marketing prose about WESUMN. WESUMN gets one sentence in the README; that's it.
- Use emoji-heavy headings or "✨ Welcome to..." style openers
- Pad with filler phrases like "in today's fast-paced world" or "as we navigate the AI landscape"

## Pattern file format

Each pattern lives at `patterns/0N-slug/README.md` and follows this structure:

1. **Title** — Pattern N: [Name]
2. **One-sentence problem statement**
3. **Why this exists** — ~200 word anchor paragraph
4. **The pattern itself** — the structural framework, with diagrams
5. **Runnable artifact** — code or template
6. **Eval section** — how to know this pattern actually wins (if applicable)
7. **Named failure modes** — 3–5 specific things that go wrong
8. **Field report sidebar** — sanitized story from real engagement
9. **Cross-references** — links to related patterns

Length: 1,500–4,000 words. Front matter: title, tags, date, status.

## Tone calibration check

Before committing any prose to this repo, run the following check on your output:

1. Count em-dashes. Target: zero.
2. Count instances of "leveraged," "orchestrated," "spearheaded." Target: zero.
3. Count parallel "X isn't Y, it's Z" constructions. Target: zero.
4. Does every claim about a regulation cite a specific article number? If not, rewrite.
5. Does every metric have a unit? If not, rewrite.
6. Does the opening paragraph use the stakes-conflict-decision structure? If not, rewrite.

## What this repo is not

- It is not a WESUMN marketing surface
- It is not an academic publication venue
- It is not a place for hot takes on AGI timelines or AI policy debates
- It is not a tutorial for beginners (it assumes practitioner readers)
- It is not a comprehensive textbook (it is a practitioner reference)

## Linked work

- WESUMN platform: github.com/Stray-South/wesumn-public
- Protocol stack: github.com/Stray-South/cognitive-meter-public, github.com/Stray-South/x402-gateway-py, github.com/Stray-South/agent-commerce-protocol, github.com/Stray-South/agent-sandbox-templates
- Personal site: straysouth.com
