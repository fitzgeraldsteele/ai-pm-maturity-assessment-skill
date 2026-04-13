---
name: ai-pm-maturity-assessment
description: Assess a PM team's AI maturity across the full product lifecycle. Use when benchmarking AI adoption, scoring PM AI readiness, identifying gaps in AI-assisted workflows, or planning where to invest in AI tooling for a product team.
---

# AI PM Maturity Assessment

Produce an honest, evidence-based assessment of how effectively a product management team uses AI across the full product lifecycle. Scores each of 12 lifecycle phases 0–5, identifies strengths and gaps, and generates concrete next steps.

## When to Invoke

- User asks "assess our AI maturity," "benchmark our AI usage," "how AI-native is our PM team?"
- User asks "where should we invest in AI for PM?" or "what PM workflows should we automate?"
- User wants to compare their team's practices against industry best practices from leading AI-native companies

## Core Rules

- **Evidence-based scoring only.** Score based on artifacts you can observe (skills, agents, prompts, docs, workflows), user-confirmed practices, and data you can query. Never assume capabilities exist without evidence.
- **Ask before guessing.** If you can't determine a team's practices from workspace artifacts alone, ask clarifying questions. An honest "I don't have enough info to score this" is better than a fabricated score.
- **Separate what exists from what's used.** A skill file that exists but is never invoked is weaker evidence than a skill with iteration history, multiple versions, or referenced outputs.
- **Honest caveats for domain mismatch.** Not every rubric area applies equally to every team. Infrastructure platform PMs, consumer PMs, and enterprise SaaS PMs have different centers of gravity. Call out where a low score reflects domain irrelevance vs. a genuine gap.
- **Actionable output.** Every gap identified must have a concrete next step, not a vague recommendation.

## Assessment Workflow

### Phase 1: Gather Evidence

Collect artifacts across these categories. Use workspace exploration tools, file search, and directory listing to inventory what exists.

| Evidence Type | Where to Look | What to Note |
|---------------|---------------|--------------|
| **AI Skills** | `.github/skills/`, skill directories | Count, coverage areas, sophistication (few-shot examples? eval criteria? trust rules?) |
| **Agents** | `.github/agents/`, agent definitions | Count, specialization, multi-step orchestration capability |
| **Chatmodes** | `.github/chatmodes/`, `ai-enablement/chatmodes/` | Purpose-built modes vs. generic |
| **Prompt Templates** | `ai-enablement/prompts/`, prompt files, `.prompt.md` files | Reusable templates in shared repos (key rubric signal) |
| **Instruction Files** | `copilot-instructions.md`, `.instructions.md`, `Claude.md` | Persistent project context (equivalent to Claude.md pattern) |
| **Output Artifacts** | Reports, specs, newsletters, test results | Evidence of AI-generated deliverables in daily use |
| **Workspace Protocol** | Contributing docs, workspace config, Git workflows | Continuous improvement loops, skill update discipline |
| **PRDs / Specs** | Spec folders, design docs | AI-assisted authoring evidence |

If the team's workspace is not available or has no AI artifacts, shift to interview mode — ask the user to describe their AI tooling, workflows, and practices, then score based on their responses.

**Supplementary evidence sources (use when available):**
- **M365 / WorkIQ**: Query for examples of AI usage in emails, Teams chats, and documents (e.g., "How has [team] been using AI to improve product outcomes?")
- **Git history**: Check commit messages and file history for evidence of AI-assisted authoring or iteration
- **Meeting transcripts**: Look for references to AI tools, Copilot usage, or automation discussions

### Phase 2: Clarify Gaps (Ask the User)

After initial evidence gathering, ask targeted questions about areas where workspace artifacts alone don't reveal the full picture. Use `vscode_askQuestions` when possible for structured input. Prioritize these 5 questions (skip any already answered by evidence):

1. **Feedback channels** — "Do you use AI to monitor or triage customer feedback from any channel (support tickets, Slack, Teams, NPS surveys)? If so, is it continuous or periodic?"
2. **Competitive tracking** — "Do you use AI for any competitive analysis, feature parity tracking, or positioning audits? What does it look like?"
3. **Eval practices** — "Do you have any way to test whether your AI skills/prompts produce correct output? Any regression testing when you update them?"
4. **Team adoption** — "How many people on your team use these AI tools regularly? Is adoption measured or incentivized?"
5. **Metrics** — "Do you track how AI has affected your team's output speed, quality, or decision-making? Any before/after data?"

Only ask about areas where workspace evidence is ambiguous or absent. Do not ask about all 12 areas.

### Phase 3: Score Each Area

Score all 12 lifecycle phases using the rubric below. For each area, document:
- **What the rubric calls for** (1–2 sentence summary of best practice)
- **What we found** (evidence from the workspace + user responses, with ✅ markers)
- **What's missing** (gaps vs. rubric, with ❌ markers)
- **Score** (0–5)
- **Next steps** (1–3 concrete, actionable items)

### Phase 4: Synthesize

Produce the final assessment document with:
1. Overall score and narrative summary
2. Area-by-area breakdown
3. Summary scorecard table
4. Top 5 highest-impact next actions (ordered by effort-to-impact ratio)
5. Methodology section documenting what evidence was reviewed

---

## Scoring Rubric

| Score | Label | Definition |
|:-----:|-------|------------|
| 0 | Not Started | No representation or application of AI in this area |
| 1 | Experimented | Ad-hoc or one-off use; no repeatable process |
| 2 | Emerging | Some tooling exists but not yet systematic or team-wide |
| 3 | Established | Repeatable AI workflows with skills/templates; regular use |
| 4 | Advanced | AI-native workflows with feedback loops, continuous improvement |
| 5 | Best Practice | Full rubric coverage; AI embedded in every aspect; team-wide and evolving |

---

## The 12 Lifecycle Phases

### 1. Product Discovery & Market Research

**Best practice signals (score 4–5):**
- LLM-powered analysis of qualitative data (customer calls, interviews, support tickets) at scale — not one-off, but recurring
- Reusable discovery prompt templates stored in a shared repo
- "Frontier Inc." exercises: quarterly re-testing of what's possible with current AI
- Designated AI operations ownership (even part-time) for improving discovery prompts
- Map-reduce pattern over large corpora (chunk → analyze → aggregate)

**Rubric sources:** Aparna Chennapragada (Microsoft CPO) — "Frontier Inc." technique; Howie Liu (Airtable) — LLM map-reduce across sales transcripts; Mike Krieger (Anthropic) — community signal synthesis; Dan Shipper (Every) — Head of AI Operations role.

**Scoring guide:**
- 0: No AI in discovery
- 1: Occasional ad-hoc LLM queries about market/customer topics
- 2: Some structured queries (e.g., Kusto/SQL analytics via AI) but reactive, not proactive
- 3: Reusable discovery templates; recurring AI-assisted analysis of feedback/usage data
- 4: Continuous signal mining; map-reduce over qualitative corpora; prompt templates iterated regularly
- 5: Full coverage — proactive discovery, Frontier Inc. cadence, shared prompt repo, AI ops ownership

### 2. Analyzing Customer Feedback & User Research

**Best practice signals (score 4–5):**
- Continuous (not periodic) AI analysis of feedback channels
- Specialized agents for different feedback types (bugs vs. feature requests vs. churn signals)
- Few-shot prompting with "golden examples" of how feedback should be categorized
- AI as triage layer directing deeper human investigation

**Rubric sources:** Boris Cherny (Anthropic) — always-on Slack feedback triage; Claire Vo (ChatPRD) — specialized agents per feedback type; Sander Schulhoff — few-shot classification technique; Chip Huyen — AI should bring you closer to user reality.

**Scoring guide:**
- 0: No AI in feedback analysis
- 1: Occasional LLM summarization of feedback
- 2: Structured skill for one feedback channel (e.g., support cases) but not continuous
- 3: Repeatable feedback analysis with skills/agents; covers primary channels
- 4: Continuous monitoring; specialized agents by feedback type; few-shot examples in prompts
- 5: Full multi-channel coverage; always-on triage; connected to product decisions; iterated regularly

### 3. Competitive Analysis & Market Intelligence

**Best practice signals (score 4–5):**
- AI-assisted competitive teardowns (real-time, not quarterly slide decks)
- AEO audits — checking how AI models describe and recommend products in your category
- Continuous competitive monitoring workflow
- Competitive intelligence fed into product prompts and PRD templates

**Rubric sources:** Amol Avasare (Anthropic) — Cowork mode for competitive teardowns; Ethan Smith (Graphite) — AEO concept; Elena Verna — PMF resets every 3 months; Brian Balfour (Reforge) — AI assistants as growth channel.

**Domain caveat:** For internal platform teams, "competitive analysis" maps to cloud provider feature parity and internal alternative positioning rather than market competition. Score based on the team's domain-appropriate version of this practice.

**Scoring guide:**
- 0: No AI in competitive analysis
- 1: Occasional ad-hoc competitive queries
- 2: Some AI-assisted comparison (e.g., feature parity tracking) but not systematic
- 3: Recurring competitive analysis workflow; AI-assisted teardowns
- 4: Continuous monitoring; AEO audits; competitive intel feeds into product planning
- 5: Full coverage — real-time teardowns, AEO, positioning stress-tests, living competitive brief

### 4. Requirements Gathering & PRD Writing

**Best practice signals (score 4–5):**
- Reusable PRD prompt templates in shared repos, iterated over time
- Previous PRDs included as few-shot examples
- Adversarial review built in ("Don't be a people pleaser" — challenge the PRD)
- Self-criticism loop: generate → review → challenge → iterate
- Persistent project context file (Claude.md / copilot-instructions.md)
- Planning stacks: Master Plan → Implementation Plan → Tasks.md

**Rubric sources:** Dan Shipper (Every) — rambling-to-PRD templates; Lazar Jovanovic — 80/20 planning/execution split; Zevi Arnovitz (Meta) — /create plan commands, Claude.md; Claire Vo (ChatPRD) — adversarial CTO pattern; Sander Schulhoff — self-criticism loop.

**Scoring guide:**
- 0: No AI in PRD writing
- 1: Occasional LLM drafting of PRDs
- 2: Some templates exist but not iterated; no adversarial review
- 3: Reusable templates in shared repo; persistent context files; regular use
- 4: Full planning stack; adversarial review; few-shot examples; continuous template improvement
- 5: All the above plus voice-to-PRD, issue-tracker integration, self-criticism loops

### 5. Metrics Definition & Success Criteria

**Best practice signals (score 4–5):**
- AI-assisted OKR validation (measurability, alignment, ambition checks)
- (Volume × Quality) ÷ Time formula applied to team output
- DORA-style metrics adapted for AI-assisted teams (deployment frequency > lines of code)
- AI-generated success criteria from PRDs
- Baseline metrics tracked before and after AI adoption

**Rubric sources:** Nicole Forsgren (DORA) — adapted DORA + SPACE metrics; Tomer Cohen (LinkedIn) — (Volume × Quality) ÷ Time formula; Logan Kilpatrick (OpenAI) — custom GPTs for OKR validation.

**Scoring guide:**
- 0: No AI in metrics definition
- 1: Occasional LLM help defining metrics
- 2: Some automated metric reporting but no AI-assisted goal validation
- 3: AI-generated metric reports with trust/quality rules; OKR frameworks documented
- 4: AI-assisted OKR validation; productivity measurement; success criteria auto-generation
- 5: Full coverage — DORA metrics, (V×Q)÷T tracking, baselining, continuous measurement

### 6. Design & Prototyping

**Best practice signals (score 4–5):**
- Rapid multi-direction prototyping with AI tools (Lovable, Bolt, v0, or domain equivalents)
- Visual references + code snippets over verbal descriptions
- Designers in the build process, not just the spec process
- Multiple prototype directions tested with real users (low cost per prototype)

**Rubric sources:** Jenny Wen (Anthropic) — "the design process is dead"; Simon Willison — 3-direction rapid prototyping; Guillermo Rauch (v0) — intent-to-prototype; Dylan Field (Figma) — AI makes design the new moat.

**Domain caveat:** For API/infrastructure product teams, "design" means API surface design, CLI UX, and documentation experience. For consumer teams, it means UI/UX. Score based on the team's domain.

**Scoring guide:**
- 0: No AI in design or prototyping
- 1: Occasional AI-generated mockups or scaffolding
- 2: Some infrastructure prototyping (e.g., ARM templates, boilerplate generation)
- 3: Repeatable prototyping workflows; AI scaffolding for test environments
- 4: Multi-direction prototyping with AI; design alternatives evaluated with users
- 5: Full AI-native design workflow; rapid iteration; real user testing of AI-generated prototypes

### 7. Stakeholder Alignment & Communication

**Best practice signals (score 4–5):**
- AI-converted meeting notes → structured decision documents
- Stakeholder update generators tuned to audience priorities
- Pre-meeting prep: AI anticipates objections and drafts responses
- Recurring automated status reports from project management tools

**Rubric sources:** Dan Shipper (Every) — meeting-to-decision-doc prompts; Zevi Arnovitz — stakeholder-ready /create plan outputs; Julie Zhuo — "from managing people to managing AI"; Jessica Fain — influence as the skill AI can't replace.

**Scoring guide:**
- 0: No AI in stakeholder communication
- 1: Occasional AI-drafted emails or updates
- 2: Some automated reporting (e.g., ADO status) but not systematic
- 3: Repeatable reporting agents/skills; AI-generated exec summaries; newsletter automation
- 4: Agentic workflow chaining (data → report → comms); OOF/handoff automation; coaching loops
- 5: Full coverage — meeting-to-decision-doc, pre-meeting prep, automated updates, coaching

### 8. Developer Communication & Technical Specs

**Best practice signals (score 4–5):**
- Persistent project context file (Claude.md or equivalent) loaded in every AI conversation
- AI-generated technical specs bridging PM intent and engineering detail
- Cross-model review (generate with one model, review with another)
- Specialized agents for different review needs (trust, growth, data access)

**Rubric sources:** Tomer Cohen (LinkedIn) — full-stack builder PMs, specialized agents; Zevi Arnovitz — Claude.md, cross-model review; Boris Cherny (Anthropic) — everyone codes.

**Scoring guide:**
- 0: No AI in developer communication
- 1: Occasional AI-drafted specs
- 2: Some AI-assisted spec generation but no persistent context or review
- 3: Persistent context files; repeatable spec generation skills; feature compatibility analysis
- 4: Cross-model review; specialized review agents; client interface design automation
- 5: Full coverage — context files, spec gen, cross-model review, specialized agents, continuous improvement

### 9. Building, Coding & Implementation

**Best practice signals (score 4–5):**
- AI-generated code with 100% human review
- Planning documents before agent execution (Master Plan → Tasks.md)
- Clear policy: "vibe coding" (prototypes) vs. "agentic engineering" (production)
- Parallel agent workflows for independent tasks
- Progressive escalation for less-technical team members

**Rubric sources:** Boris Cherny (Anthropic) — 100% Claude-written code, 200% productivity; Simon Willison — vibe coding vs. agentic engineering; Lazar Jovanovic — planning-first agent execution; Sherwin Wu (OpenAI) — 95% Codex adoption.

**Scoring guide:**
- 0: No AI in coding/implementation
- 1: Occasional AI code generation
- 2: Some AI-generated scripts/templates but no review policy
- 3: Repeatable scaffolding skills; AI-native workspace; planning-before-execution pattern
- 4: Formal review policies; parallel workflows; progressive escalation documented
- 5: Full AI-native engineering — all code AI-generated with review, parallel agents, team-wide adoption

### 10. Testing, QA & AI Evals

**Best practice signals (score 4–5):**
- Formal eval suite: Q&A pairs defining "good" output for AI skills/agents
- Production-failure-driven eval creation (when it fails, add an eval case)
- "Poor man's fine-tuning" — few-shot examples in key prompts
- Designated eval owner
- Regression testing when skills are updated

**Rubric sources:** Hamel Husain & Shreya Shankar — evals as "the hottest new PM skill"; Nick Turley (OpenAI) — production failures > benchmarks; Kevin Weil (OpenAI) — poor man's fine-tuning; Brendan Foody (Mercor) — "if the model is the product, the eval is the PRD."

**This is typically the highest-leverage gap.** Teams invest in AI skills but rarely build the eval infrastructure to verify those skills work correctly or catch regressions.

**Scoring guide:**
- 0: No evals or quality measurement for AI outputs
- 1: Ad-hoc spot-checking of AI outputs
- 2: Some trust/quality rules in skills but no formal eval suite
- 3: Basic eval cases exist; few-shot examples in key skills; results tracking
- 4: Systematic eval suite; production-failure-driven additions; regression testing
- 5: Full eval coverage — eval owner, automated regression, continuous improvement, DeepEval-style harness

### 11. Launch, Growth & Distribution

**Best practice signals (score 4–5):**
- Launch ≠ landed — adoption threshold and success criteria defined before ship
- Structured adoption tracking tiers (shipped → awareness → activation → sustained use → outcome achieved)
- AI-powered adoption dashboards, activation drop-off detection, early-adopter feedback synthesis
- Distribution plan as a parallel workstream covering: docs/tutorials, content/community, ecosystem/integrations, in-product discovery, field/enablement, and AI-native channels (AEO)
- AEO audits (how AI models describe and recommend your product)
- Rapid experimentation loops (idea → AI prototype → user test in one day)
- AI-legible positioning (AI models can accurately describe your product)
- Continuous iteration as model capabilities change (PMF resets every ~3 months)
- Post-launch impact reviews at 90 days — did-it-land assessment against pre-defined thresholds

**Rubric sources:** Elena Verna — PMF resets every 3 months; Ethan Smith (Graphite) — AEO; Brian Balfour (Reforge) — AI assistants as growth channel; Grant Lee (Gamma) — same-day experimentation loops. Internal best practice: landing reports with adoption tiers and named-customer unblock tracking.

**Domain caveat:** For internal platform teams, "growth" means adoption by internal customers and partner services, not PLG user acquisition. "Distribution" means enablement (docs, workshops, migration guides, field engagement), not marketing campaigns. Score based on the team's domain-appropriate version.

**Scoring guide:**
- 0: No AI in launch or growth; no adoption tracking beyond "feature is live"
- 1: AI-assisted launch communications (one-off); success measured by ship date
- 2: Launch templates/checklists exist; some adoption telemetry but no pre-defined thresholds or landing criteria
- 3: Adoption thresholds defined before launch; AI-assisted adoption tracking; distribution plan covers 2–3 channels; newsletter/changelog automation
- 4: Structured adoption tiers tracked (shipped → activated → sustained → outcome); AI-powered adoption dashboards and drop-off detection; AEO audits; experimentation loops; distribution across 4+ channels; 90-day impact reviews
- 5: Full AI-native growth — pre-defined landing criteria for every launch, automated adoption funnels, AI-synthesized early-adopter feedback, AEO, rapid experimentation, multi-channel distribution plans, PMF-reset tracking, post-launch impact reviews as standard operating rhythm

### 12. Team Structure, Hiring & AI Adoption

**Best practice signals (score 4–5):**
- AI fluency in hiring criteria and performance reviews
- (Volume × Quality) ÷ Time tracking at team level
- Under-resourcing as forcing function for AI adoption
- "Permission > mandate" adoption strategy (let early adopters demonstrate value)
- Meeting restructuring (AI replaces many status meetings)

**Rubric sources:** Tomer Cohen (LinkedIn) — Platform + Tools + Culture framework, (V×Q)÷T; Howie Liu (Airtable) — fast/slow thinking teams; Boris Cherny (Anthropic) — under-resourcing, unlimited tokens; Eoghan McCabe (Intercom) — radical restructuring.

**Scoring guide:**
- 0: No organizational consideration of AI adoption
- 1: Individual experimentation, no team-level approach
- 2: Some team members use AI; no adoption measurement
- 3: AI-native workspace shared with team; onboarding documentation; leadership investment
- 4: Adoption metrics tracked; AI fluency expectations; showcase/sharing practices
- 5: Full coverage — hiring criteria, performance reviews, adoption dashboards, team restructuring

---

## Output Format

### Assessment Document Structure

```markdown
# AI in Product Management — Maturity Assessment

**Team:** [Team name]
**Date:** [Assessment date]
**Assessed by:** [Assessor]

---

## Overall Assessment

**Composite Score: X.X / 5.0 — [Label]**

[2–3 sentence narrative: strongest areas, biggest gaps, key theme]

---

## Area-by-Area Assessment

### 1. [Phase Name] — Score: X / 5

**What the rubric calls for:** [1–2 sentences]

**What we found:**
- ✅ [Evidence of capability]
- ✅ [Evidence of capability]

**What's missing:**
- ❌ [Gap vs. rubric]
- ❌ [Gap vs. rubric]

**Next steps:**
- [ ] [Concrete action]
- [ ] [Concrete action]

[Repeat for all 12 phases]

---

## Summary Scorecard

| # | PM Lifecycle Phase | Score | Key Strength | Biggest Gap |
|:-:|:-------------------|:-----:|:-------------|:------------|
| 1 | Product Discovery & Market Research | **X.X** | ... | ... |
[...]
| | **Composite Average** | **X.X** | | |

---

## Top 5 Highest-Impact Next Actions

[Ordered by effort-to-impact ratio for this specific team]

---

## Methodology

[What evidence was reviewed, what questions were asked, what tools were used]
```

### Score Labels

| Range | Label |
|:-----:|-------|
| 0.0–0.9 | Not Started |
| 1.0–1.9 | Experimenting |
| 2.0–2.9 | Emerging |
| 3.0–3.9 | Established |
| 4.0–4.5 | Advanced |
| 4.6–5.0 | AI-Native |

### Composite Score Calculation

Calculate two scores:
- **Composite Average:** Simple average of all 12 area scores
- **Weighted Average:** Weight areas based on the team's domain (e.g., infrastructure platform teams weight analytics/specs/testing higher; consumer teams weight design/growth/feedback higher)

Always show both scores and explain the weighting rationale.

---

## Common Patterns by Team Type

### Infrastructure / Platform PM Teams
Tend to score high on: Analytics, developer specs, building/implementation, stakeholder comms
Tend to score low on: Design, competitive analysis, launch/growth, AI evals
Key leverage point: AI evals (protect existing skills from degradation)

### Consumer Product PM Teams
Tend to score high on: Design, feedback analysis, launch/growth
Tend to score low on: Developer specs, metrics definition, team adoption measurement
Key leverage point: Customer signal synthesis (connect feedback to discovery)

### Enterprise SaaS PM Teams
Tend to score high on: PRD writing, stakeholder comms, competitive analysis
Tend to score low on: Building/implementation, AI evals, design prototyping
Key leverage point: Rapid prototyping (compress experimentation cycles)

---

## Sources

This rubric is synthesized from 40+ episodes of Lenny's Podcast (January 2025 – April 2026), including direct practices from:
- Anthropic (Boris Cherny, Mike Krieger, Jenny Wen, Amol Avasare)
- OpenAI (Kevin Weil, Sherwin Wu, Nick Turley, Logan Kilpatrick, Alexander Embiricos)
- Microsoft (Aparna Chennapragada)
- LinkedIn (Tomer Cohen)
- Airtable (Howie Liu)
- Vercel (Guillermo Rauch)
- Lovable (Anton Osika)
- Bolt (Eric Simons)
- Reforge (Brian Balfour)
- Graphite (Ethan Smith)
- ChatPRD (Claire Vo)
- Every (Dan Shipper)
- DORA/GitHub (Nicole Forsgren)
- Figma (Dylan Field)
- Intercom (Eoghan McCabe)
- Mercor (Brendan Foody)
- Eval experts (Hamel Husain, Shreya Shankar)
- Prompt engineering (Sander Schulhoff)
- AI engineering (Chip Huyen)
- Independent practitioners (Simon Willison, Lazar Jovanovic, Zevi Arnovitz)
