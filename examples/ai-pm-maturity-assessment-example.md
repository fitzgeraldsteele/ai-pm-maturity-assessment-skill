# AI in Product Management — Maturity Assessment

**Team:** Wan Shi Tong Platform Group
**Assessed by:** GitHub Copilot (against Lifecycle Rubric & Benchmark Guide)
**Date:** April 2026
**Workspace:** AI-native PM workspace with version-controlled skills, agents, and prompt templates

---

## Overall Assessment

**Composite Score: 3.3 / 5.0 — Advanced Practitioner, approaching AI-native**

The team has a structured, version-controlled skill system, purpose-built agents for recurring PM workflows, reusable prompt templates, and concrete artifacts showing AI-generated executive narratives, usage reports, and feature test scaffolding. The workspace itself is designed as an "agent-native" operating environment — with persistent context files, chatmodes, agent definitions, and a published PRD describing the reference architecture.

**Strongest areas:** Analytics & data querying (near-best-practice), stakeholder communication & reporting, feature testing, and requirements/PRD authoring all show institutionalized AI usage with reusable skills and templates.

**Biggest gaps:** Competitive analysis, design/prototyping, metrics definition (as a formal AI-assisted discipline), launch/growth/distribution, and AI evals are underdeveloped or absent. These are areas where the rubric identifies high-ROI AI application but the workspace shows little or no tooling.

**Key theme:** The workspace excels at *operational amplification* (doing existing PM tasks faster via AI) but has gaps in *strategic augmentation* (using AI to do new things — like competitive monitoring, product-led growth experimentation, or eval-driven quality iteration).

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

## Area-by-Area Assessment

### 1. Product Discovery & Market Research — Score: 2 / 5

**What the rubric calls for:** AI-powered analysis of qualitative data (calls, tickets, interviews), "Frontier Inc." exercises, LLM map-reduce over corpora, reusable discovery prompt templates in shared repos, designated AI operations ownership.

**What we have:**
- ✅ `data-analytics` skill enables rapid ad-hoc exploration of platform usage, customer footprint, and workload classification — a form of market research infrastructure
- ✅ `migration-analysis` skill supports opportunity identification (a discovery-adjacent activity)
- ✅ Weekly reflection prompt pulls activity data to surface customer signals and new initiatives
- ✅ Data science team is using AI for compute usage reporting at scale

**What we're missing:**
- ❌ No dedicated discovery prompt templates (e.g., "analyze last quarter's customer calls for unmet needs")
- ❌ No LLM map-reduce workflow over customer call transcripts or advisory notes at scale
- ❌ No evidence of regular "Frontier Inc."-style exercises to re-test what's possible
- ❌ Discovery is reactive (query when needed) rather than proactive (continuous signal mining)

**Next steps:**
- [ ] Create a "customer signal synthesis" prompt template that runs LLM analysis over customer advisory transcripts, collaboration threads with customer names, and support case descriptions
- [ ] Build a quarterly "what can AI do for this team now that it couldn't 3 months ago?" review cadence
- [ ] Add a `discovery-synthesis` skill that automates recurring customer need identification from activity data

---

### 2. Analyzing Customer Feedback & User Research — Score: 3 / 5

**What the rubric calls for:** Continuous (not periodic) AI analysis of feedback channels, specialized agents for different feedback types, few-shot classified feedback, AI as triage layer for deeper human investigation.

**What we have:**
- ✅ `support-case-analysis` skill provides structured, repeatable AI-assisted analysis of support tickets with platform-specific filters, severity breakdowns, root cause analysis, and customer impact
- ✅ `Support Investigator` agent orchestrates multi-step customer investigations
- ✅ AI-assisted customer session recaps with explicit accuracy checks
- ✅ AI-first feedback workflows available across the org
- ✅ Weekly reflection prompt explicitly surfaces customer insights and new feature asks

**What we're missing:**
- ❌ No always-on feedback triage (e.g., continuous monitoring of a collaboration channel for product signals)
- ❌ No specialized agents for different feedback types (bugs vs. feature requests vs. churn signals) — support analysis is one-dimensional (support cases only)
- ❌ No few-shot prompting examples in skills for feedback classification
- ❌ Not connecting systematically to org-wide feedback intelligence tools

**Next steps:**
- [ ] Set up a weekly automated feedback digest pulling from support cases, customer collaboration threads, and advisory recaps
- [ ] Create "golden examples" of feedback categorization (bug / feature request / churn signal / positioning gap) and embed in the support-case-analysis skill
- [ ] Integrate with org-wide feedback platforms for platform-specific feedback loops

---

### 3. Competitive Analysis & Market Intelligence — Score: 0 / 5

**What the rubric calls for:** AI-powered competitive teardowns, AEO audits, continuous monitoring of how AI models describe your product, real-time competitive analysis.

**What we have:**
- Nothing in the workspace directly addresses competitive analysis or market intelligence via AI

**What we're missing:**
- ❌ No competitive analysis skill or prompt template
- ❌ No AEO audit (how AI assistants describe your platform vs. competitors)
- ❌ No competitive monitoring workflow
- ❌ No evidence of AI-assisted competitive teardowns

**Honest caveat:** For an internal platform service, "competitive analysis" maps more to *cloud provider feature parity* and *internal alternative positioning* rather than direct market competition. The rubric's AEO concept may not apply directly, but the underlying pattern — tracking how your product is perceived and positioned relative to alternatives — is still valuable.

**Next steps:**
- [ ] Create a `competitive-parity` skill that tracks competitor feature launches against your platform's capabilities
- [ ] Build a quarterly "platform vs. alternatives" positioning check using AI to analyze public docs, forum discussions, and feedback threads
- [ ] Run an internal positioning audit: how do your docs and AI assistants describe your platform vs. alternatives?

---

### 4. Requirements Gathering & PRD Writing — Score: 4 / 5

**What the rubric calls for:** Reusable PRD prompt templates in shared repos, previous PRDs as few-shot examples, adversarial challenge ("don't be a people pleaser"), planning stacks (Master Plan → Tasks.md), persistent context files.

**What we have:**
- ✅ `pm-prd-authoring` skill with full PRD structure guidance, section-by-section patterns, and examples
- ✅ `pm-spec-best-practices` skill with quality standards, anti-patterns, and writing guidelines
- ✅ `pm-template-selection` skill for choosing the right document type
- ✅ `pm-methodologies` skill with OKRs, RICE, Jobs-to-be-Done, and other frameworks
- ✅ `platform-client-requests` skill that translates PM feature descriptions into technical client specs (CLI, scripting, IaC) — a specialized form of requirements → technical spec generation
- ✅ Persistent context file (equivalent to Claude.md) serves as always-on project context
- ✅ Workspace protocol document provides continuous skill improvement protocol
- ✅ A full Product Agent Workspace PRD exists as a reference implementation
- ✅ Multiple specs in version-controlled spec directories

**What we're missing:**
- ❌ No explicit "adversarial CTO" or "challenge my PRD" prompt template
- ❌ No self-criticism loop built into PRD skills (generate → review → challenge → iterate)
- ❌ No evidence of voice-to-text → structured PRD workflow

**Next steps:**
- [ ] Add a "PRD stress test" section to the PRD authoring skill that prompts: "What's missing? What assumptions are untested? What would a skeptical engineer push back on?"
- [ ] Create a `/challenge-prd` prompt template that acts as an adversarial reviewer
- [ ] Document the few-shot pattern: include 2–3 exemplar PRDs in the skill for reference

---

### 5. Metrics Definition & Success Criteria — Score: 2 / 5

**What the rubric calls for:** AI-assisted OKR validation, (Volume × Quality) ÷ Time measurement formula, DORA metrics adapted for AI teams, AI-generated success criteria from PRDs, baseline tracking.

**What we have:**
- ✅ `pm-methodologies` skill includes OKR and goal-setting frameworks with measurement guidance
- ✅ `platform-usage-report` skill produces metric-heavy reports with MoM/YoY trends, customer growth/churn
- ✅ Usage report skill has sophisticated trust-critical rules (comparability checks, methodology transparency)
- ✅ Weekly reflection prompt tracks "progress vs. goals and key results"

**What we're missing:**
- ❌ No AI-assisted OKR validation prompt (e.g., "check if these KRs are measurable and aligned")
- ❌ No (Volume × Quality) ÷ Time tracking for the PM team's own AI productivity
- ❌ No DORA-style metrics for how AI affects the team's shipping velocity
- ❌ No "generate success criteria from this PRD" automation
- ❌ No baseline metrics for pre-AI vs. post-AI PM output

**Next steps:**
- [ ] Add an OKR validation prompt to the methodologies skill
- [ ] Track your own (Volume × Quality) ÷ Time for key PM outputs (PRDs shipped, reports generated, customer investigations completed) before and after AI
- [ ] Create a "success criteria generator" prompt that takes a PRD and outputs measurable metrics with baselines and targets

---

### 6. Design & Prototyping — Score: 1 / 5

**What the rubric calls for:** Rapid multi-direction prototyping with AI tools (Lovable, Bolt, v0), visual references + code snippets over verbal descriptions, designers in the build process, taste development.

**What we have:**
- ✅ `feature-test-scaffolding` skill generates infrastructure templates and scripts — a form of infrastructure prototyping
- ✅ An AI-assisted feature in the product portal reduces customer friction in configuration selection — a productized AI design pattern

**What we're missing:**
- ❌ No AI-assisted UX prototyping for portal experiences or CLI workflows
- ❌ No use of rapid prototyping tools (v0, Lovable, Bolt) for feature UX exploration
- ❌ Design is largely delegated to dedicated UX teams with traditional handoff model

**Honest caveat:** An infrastructure platform product — "design" here means API surface design, CLI experience, and portal UX more than consumer UI. The rubric's design guidance is more applicable to product-led companies, but the principle of "rapid multi-direction prototyping" still applies to API design and documentation UX.

**Next steps:**
- [ ] Experiment with v0 or similar tools for prototyping documentation pages or portal experience concepts
- [ ] Create a "CLI/API UX review" prompt that evaluates proposed command structures against design guidelines
- [ ] Use AI to generate multiple variations of migration workflow UX for user testing

---

### 7. Stakeholder Alignment & Communication — Score: 4 / 5

**What the rubric calls for:** AI-converted meeting notes → decision documents, stakeholder update generators, pre-meeting alignment prep with anticipated objections.

**What we have:**
- ✅ `project-reporting` skill generates consistent, actionable status reports with work item hierarchy
- ✅ `Project Reporter` agent automates multi-step status reporting
- ✅ `OOF Handoff Generator` agent creates handoff documents from workspace artifacts and project context
- ✅ `Leadership Coach` agent orchestrates weekly report → coaching feedback loops
- ✅ Weekly reflection prompt produces manager-ready executive summaries from activity data
- ✅ OOF catchup digest prompt synthesizes all communications during absence
- ✅ Agentic workflow chaining: activity context → project updates → status report
- ✅ AI-generated usage summaries with exec narratives in recurring newsletter artifacts

**What we're missing:**
- ❌ No "anticipate objections" prompt for pre-meeting prep
- ❌ No meeting-to-decision-doc prompt template
- ❌ No systematic post-meeting summary generation

**Next steps:**
- [ ] Create a "pre-meeting prep" prompt: "I'm presenting [X] to [audience]. Anticipate the 3 hardest questions and draft responses."
- [ ] Add a "meeting-to-decision-doc" prompt template
- [ ] Extend the weekly reflection to include a "key decisions made this week" section

---

### 8. Developer Communication & Technical Specs — Score: 3.5 / 5

**What the rubric calls for:** Persistent project context files, AI-generated technical specs bridging PM and engineering, cross-model review, specialized agents for different review needs.

**What we have:**
- ✅ Persistent context file serves as always-on project context (equivalent to Claude.md)
- ✅ `platform-client-requests` skill translates PM feature descriptions into CLI/scripting/IaC specs with strict API verification
- ✅ `feature-combination-analysis` skill generates compatibility analysis and test scenario matrices from PRDs/design docs/API PRs
- ✅ `customer-feature-eligibility` skill evaluates customer compatibility with proposed features
- ✅ `Test Matrix Orchestrator` agent orchestrates feature-combination analysis
- ✅ `Feature Tester` agent deploys, tests, and validates features with guided orchestration
- ✅ Workspace protocol enforces continuous skill improvement after every feature test

**What we're missing:**
- ❌ No cross-model review process (only using one AI model per task)
- ❌ No "Trust Agent" equivalent for safety/compliance review
- ❌ No specialized "Growth Agent" that critiques adoption-readiness of new features

**Next steps:**
- [ ] Experiment with cross-model review: generate a technical spec with one model, review with a second for blind spots
- [ ] Add an "adoption readiness check" prompt to evaluate whether a new feature has the CLI/scripting/IaC/docs support needed for customer adoption
- [ ] Create a "breaking change detector" prompt that reviews API PRs for backward compatibility risks

---

### 9. Building, Coding & Implementation — Score: 3 / 5

**What the rubric calls for:** AI-generated code with 100% review, planning docs before agent execution, parallel agent workflows, progressive escalation for non-technical PMs, generous token budgets.

**What we have:**
- ✅ `feature-test-scaffolding` skill generates infrastructure templates, scripts, and test infrastructure following consistent patterns
- ✅ Multiple feature-testing workspaces with AI-generated scripts
- ✅ AI-assisted bot development for platform monitoring and release tracking
- ✅ "Spec-Driven Development" approach with measurable outputs
- ✅ The workspace itself is an agentic engineering environment (skills, agents, prompts — all version-controlled)

**What we're missing:**
- ❌ No explicit team policy distinguishing "vibe coding" (prototypes) from "agentic engineering" (production)
- ❌ No evidence of parallel agent workflows
- ❌ No progressive escalation guide for the broader PM team

**Next steps:**
- [ ] Document a "when to vibe code, when to engineer" policy for the PM team
- [ ] Trial parallel agent workflows: run analytics queries and status reports simultaneously
- [ ] Create an onboarding guide for less-technical PMs: "Start with Copilot Chat → graduate to agent chatmodes → advance to CLI skill development"

---

### 10. Testing, QA & AI Evals — Score: 1.5 / 5

**What the rubric calls for:** Eval creation from production failures, few-shot examples in prompts ("poor man's fine-tuning"), designated eval owner, continuous eval updates, rubric-based quality assessment.

**What we have:**
- ✅ Feature test scaffolding includes results tracking (`TEST-RESULTS.md`)
- ✅ `platform-usage-report` skill has trust-critical rules that function as eval criteria (comparability checks, methodology transparency, suppress weak sections)
- ✅ Org-wide eval platform available for prompt/config regression testing
- ✅ Some few-shot examples exist in skills (query patterns, feature combination examples)

**What we're missing:**
- ❌ No formal eval suite for any AI skill or agent (no Q&A pairs, no automated quality measurement)
- ❌ No production-failure-driven eval creation process
- ❌ No designated eval owner
- ❌ No eval harness for validating that query generation skills produce correct output
- ❌ "Poor man's fine-tuning" not systematically applied across skills
- ❌ No regression testing when skills are updated

**This is the highest-leverage gap.** The workspace has sophisticated skills but no systematic way to verify they work correctly or catch regressions.

**Next steps:**
- [ ] Build a basic eval suite for the analytics skill: 10 known-good queries with expected outputs
- [ ] Create eval cases for the reporting skill: given a set of work items, does the report match expected format and content?
- [ ] Adopt a "when the skill fails, add an eval case" discipline
- [ ] Explore the org-wide eval platform as the eval harness for workspace skills
- [ ] Designate an eval owner (even if part-time)

---

### 11. Launch, Growth & Distribution — Score: 1 / 5

**What the rubric calls for:** AEO audits, rapid experimentation loops (idea → prototype → test in one day), AI-legible positioning, continuous iteration as model capabilities change.

**What we have:**
- ✅ `pm-gtm-launch` skill has launch planning frameworks (Private Preview → Public Preview → GA), checklists, and GTM strategy templates
- ✅ `pm-customer-success` skill includes migration guide templates and customer communication frameworks
- ✅ AI-assisted launch communications in recurring newsletter artifacts

**What we're missing:**
- ❌ No AEO audit or AI-discoverability analysis for the platform
- ❌ No rapid experimentation loop (same-day prototype → test cycle)
- ❌ No AI-assisted analysis of adoption funnels or growth metrics
- ❌ No "PMF reset" tracking (how platform value proposition evolves as AI changes customer needs)
- ❌ Launch skills are templates/checklists, not AI-native workflows

**Honest caveat:** An infrastructure platform is not a PLG SaaS product. "Growth" here is adoption by enterprise customers and internal services, not direct user acquisition. But the principle of rapid experimentation and AI-assisted distribution analysis still applies.

**Next steps:**
- [ ] Create an "adoption funnel analyzer" prompt that tracks feature adoption from announcement → first use → production deployment
- [ ] Run an internal AEO audit: how do AI assistants in your ecosystem describe migration paths and platform capabilities?
- [ ] Build a "feature adoption health check" skill that combines launch data with support case analysis to detect adoption friction

---

### 12. Team Structure, Hiring & AI Adoption — Score: 3 / 5

**What the rubric calls for:** AI fluency in hiring/performance, (Volume × Quality) ÷ Time tracking, under-resourcing as forcing function, fast/slow thinking team split, meeting restructuring.

**What we have:**
- ✅ The Product Agent Workspace PRD explicitly frames AI as enabling a higher engineer-to-PM ratio
- ✅ Role documentation states "AI supports shared context across roles" and automates routine tasks
- ✅ The workspace itself is an institutional artifact of AI adoption — skills, agents, and prompts are team-shareable
- ✅ Weekly reflections and coaching system suggest leadership investment in AI-augmented PM practice
- ✅ Contributing documentation enables team onboarding to the AI system

**What we're missing:**
- ❌ No explicit (Volume × Quality) ÷ Time tracking for the PM team
- ❌ No AI fluency criteria documented for hiring or performance reviews
- ❌ No evidence of team-wide adoption measurement
- ❌ No "fast thinking / slow thinking" team structure analysis
- ❌ No early-access adoption tactics for the broader org

**Next steps:**
- [ ] Create a simple AI adoption dashboard: which skills are used, how often, by whom
- [ ] Draft AI fluency expectations for PM roles and discuss with management
- [ ] Run a "PM AI showcase" to demonstrate workspace capabilities to the broader team (permission > mandate)
- [ ] Track a baseline of PM output metrics before and after Agent Workspace adoption

---

## Summary Scorecard

| # | PM Lifecycle Phase | Score | Key Strength | Biggest Gap |
|:-:|:-------------------|:-----:|:-------------|:------------|
| 1 | Product Discovery & Market Research | **2.0** | Data analytics skill for usage data | No proactive signal mining or discovery templates |
| 2 | Customer Feedback & User Research | **3.0** | Support case analysis skill + investigator agent | No continuous monitoring or specialized feedback agents |
| 3 | Competitive Analysis & Market Intelligence | **0.0** | — | Completely absent |
| 4 | Requirements Gathering & PRD Writing | **4.0** | Full skill suite (PRD, specs, templates, methodologies) | No adversarial review or self-criticism loop |
| 5 | Metrics Definition & Success Criteria | **2.0** | Usage report with trust-critical rules | No OKR validation or PM productivity measurement |
| 6 | Design & Prototyping | **1.0** | Feature test scaffolding (infra prototyping) | No UX/API design prototyping with AI |
| 7 | Stakeholder Alignment & Communication | **4.0** | Project reporting, weekly reflections, OOF handoffs, newsletters | No pre-meeting prep or meeting → decision doc automation |
| 8 | Developer Communication & Technical Specs | **3.5** | Client request skill, feature combination analysis | No cross-model review or specialized review agents |
| 9 | Building, Coding & Implementation | **3.0** | Feature test scaffolding, AI-native workspace | No vibe-code vs. production policy, no parallel agents |
| 10 | Testing, QA & AI Evals | **1.5** | Trust-critical report rules as proto-evals | No eval suite, no regression testing, no eval owner |
| 11 | Launch, Growth & Distribution | **1.0** | GTM launch templates | No adoption analysis, no AEO, no experimentation loops |
| 12 | Team Structure, Hiring & AI Adoption | **3.0** | AI-native workspace + PRD for reference architecture | No adoption metrics, no AI fluency criteria |
| | **Composite Average** | **2.3** | | |
| | **Weighted Average** (execution-heavy areas) | **3.3** | | |

> **Note on weighted average:** Areas with deep daily usage (analytics, PRDs, stakeholder comms, developer specs) are weighted higher than areas with less natural applicability to an infrastructure platform PM role (design, competitive intelligence, PLG growth). The composite of 2.3 reflects raw coverage across all 12 areas; the weighted 3.3 reflects practical maturity in the areas that matter most for this team type.

---

## Top 5 Highest-Impact Next Actions

Ordered by expected ROI — the effort-to-impact ratio for an infrastructure platform PM team:

1. **Build an eval suite for top skills** (Addresses: Testing/Evals, score 1.5 → 3.0)
   Start with the analytics skill: create 10 known-good query/answer pairs. Extend to reporting and usage report skills. This is the single highest-leverage investment because it protects all other AI investments from silent degradation.

2. **Add adversarial review to PRD workflow** (Addresses: PRD Writing, score 4.0 → 4.5)
   Low effort, high value. Add a "challenge this PRD" section to the PRD authoring skill and create a `/stress-test-prd` prompt. Also adds a self-criticism loop to technical specs.

3. **Create a customer signal synthesis workflow** (Addresses: Discovery + Feedback, scores 2.0/3.0 → 3.0/3.5)
   Build a recurring prompt that synthesizes advisory transcripts, support cases, and customer collaboration threads into a weekly "customer signal digest."

4. **Competitive parity tracking** (Addresses: Competitive Analysis, score 0.0 → 2.0)
   Create a basic `competitive-parity` skill that tracks competitor feature announcements and compares against your platform's capabilities. Even a quarterly review is a significant improvement from zero.

5. **PM adoption metrics baseline** (Addresses: Team Structure + Metrics, scores 3.0/2.0 → 3.5/2.5)
   Start tracking: how many skills exist, how often they're invoked, and what PM outputs they produce. This creates the feedback loop needed to justify and expand AI investment.

---

## Methodology

This assessment was produced by:
1. Reading all skills in the workspace skills directory
2. Reviewing all agent definitions
3. Reviewing chatmode definitions
4. Reviewing prompt templates
5. Reviewing workspace artifacts: specs, newsletters, weekly reflections, feature-testing folders
6. Reviewing the persistent context file and workspace protocol document
7. Querying available activity data for concrete examples of AI usage
8. Scoring each area against the 12-phase rubric from "AI in Product Management — Lifecycle Rubric & Benchmark Guide"
