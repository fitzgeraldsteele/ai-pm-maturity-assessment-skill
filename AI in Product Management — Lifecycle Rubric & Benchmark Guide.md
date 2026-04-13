# AI in Product Management: Lifecycle Rubric & Benchmark Guide

**Synthesized from 40+ episodes of Lenny's Podcast (January 2025 – April 2026)**

This report covers every major phase of the product management lifecycle and documents how leading companies and practitioners are using AI in each phase. Each section follows the same structure: a summary of the strategy, concrete examples with sources, and actionable dos/don'ts/next steps. Use this as a rubric to benchmark your team's AI maturity and identify where to invest next.

---

## Table of Contents

1. [Product Discovery & Market Research](#1-product-discovery--market-research)
2. [Analyzing Customer Feedback & User Research](#2-analyzing-customer-feedback--user-research)
3. [Competitive Analysis & Market Intelligence](#3-competitive-analysis--market-intelligence)
4. [Requirements Gathering & PRD Writing](#4-requirements-gathering--prd-writing)
5. [Metrics Definition & Success Criteria](#5-metrics-definition--success-criteria)
6. [Design & Prototyping](#6-design--prototyping)
7. [Stakeholder Alignment & Communication](#7-stakeholder-alignment--communication)
8. [Developer Communication & Technical Specs](#8-developer-communication--technical-specs)
9. [Building, Coding & Implementation](#9-building-coding--implementation)
10. [Testing, QA & AI Evals](#10-testing-qa--ai-evals)
11. [Launch, Growth & Distribution](#11-launch-growth--distribution)
12. [Team Structure, Hiring & AI Adoption](#12-team-structure-hiring--ai-adoption)
13. [Appendix: Tools Referenced](#appendix-tools-referenced)
14. [Appendix: Episode Index](#appendix-episode-index)

---

## 1. Product Discovery & Market Research

### How AI Is Being Used

The most sophisticated product teams are using AI to dramatically compress the discovery cycle. Aparna Chennapragada (Microsoft CPO) described a technique she calls **"Frontier Inc."** — imagine a startup founded today with access to all current AI tools, then prototype what their workflows would look like. This forces your team to prototype with AI rather than theorize about it, and surfaces assumptions about what's technically possible that may already be outdated. Kevin Weil (OpenAI CPO) reinforced this: "The AI models that you're using today is the worst AI model you will ever use for the rest of your life... every two months, computers can do something they've never been able to do before and you need to completely think differently about what you're doing."

At Anthropic, Mike Krieger's team monitors community channels (Discord, forums, X/Twitter) and uses Claude to synthesize patterns across thousands of user conversations — effectively automating the "what are people asking for?" question that traditionally requires a researcher or community manager to manually track. Howie Liu (Airtable CEO) takes a similar but more intensive approach: he runs LLM map-reduce analysis across hundreds of sales call transcripts, breaking long transcripts into chunks and running analysis on each, then aggregating. He describes the output as "like a really smart chief of staff read every sales call transcript." He tracks his personal inference costs and takes pride in being Airtable's highest-spending internal user — often spending hundreds of dollars on a single strategic analysis, which he views as trivial compared to the strategic value of better insights.

Dan Shipper (Every) has operationalized discovery even further by creating a **Head of AI Operations** role — a person whose full-time job is building prompts and workflows that automate repetitive discovery tasks. In weekly 1:1s with Dan, they identify repetitive work and convert it into reusable prompt templates stored in a shared GitHub repo, so every successive discovery task gets faster.

### Concrete Examples, Techniques & Prompts

**Frontier Inc. exercise (Aparna Chennapragada, Microsoft):** (transcript @11:14) Gather your team and ask: "If we were founding a company today with the same mission, using a fully AI-native approach, what would our discovery process look like?" Prototype the answer. If the answer is "not meaningfully different from what we do today," that's a red flag.

**LLM map-reduce for call analysis (Howie Liu, Airtable):** ([▶ YouTube @14:49](https://youtu.be/GT0jtVjRy2E?t=889)) Take a corpus of sales calls, customer interviews, or support tickets. Break into chunks. Run each through an LLM with a prompt like: "Extract the top product requests, objections, and competitive mentions from this transcript. Flag any quotes that reveal unmet needs." Aggregate results across all chunks to find patterns.

**Community signal synthesis (Mike Krieger, Anthropic):** ([▶ YouTube @19:24](https://youtu.be/DKrBGOFs0GY?t=1164)) Point Claude at community channels and ask it to identify recurring themes, feature requests, and pain points across hundreds of messages. Use this as an input to roadmap prioritization.

**Brainstorming with AI (Simon Willison):** ([▶ YouTube @25:00](https://youtu.be/wc8FBhQtdsA?t=1500)) Ask for 20+ ideas iteratively. "The first ideas are obvious, later ones point in interesting directions." Combine unexpected domains for creative inspiration — e.g., "Marketing my SaaS inspired by marine biology."

### Dos, Don'ts & Next Steps

**Do:**
- Run the "Frontier Inc." exercise quarterly to recalibrate what's possible with current AI
- Invest in LLM-powered analysis of your existing qualitative data (calls, tickets, interviews) — the ROI is enormous and immediate
- Create reusable prompt templates for recurring discovery tasks and store them in a shared repo
- Budget for AI inference costs as a strategic investment, not an expense to minimize

**Don't:**
- Don't rely on AI to replace customer conversations — use it to analyze and synthesize, not to substitute for direct user contact
- Don't assume yesterday's "impossible" is still impossible — re-test AI capabilities on discovery tasks every quarter
- Don't keep discovery insights locked in individual heads — operationalize them into shared prompts and workflows

**Next Steps:**
- [ ] Identify your team's top 3 recurring discovery tasks and create prompt templates for each
- [ ] Run an LLM analysis on your last quarter of customer calls or support tickets
- [ ] Designate someone (even part-time) as an "AI operations" owner who captures and improves team prompts weekly

---

## 2. Analyzing Customer Feedback & User Research

### How AI Is Being Used

Feedback analysis is one of the highest-ROI applications of AI for product teams. Boris Cherny (Head of Claude Code, Anthropic) described pointing Claude at Anthropic's internal Slack feedback channel, where it automatically surfaces bug fixes, feature ideas, and improvement suggestions from the firehose of customer feedback. This isn't a once-a-month synthesis — it's a continuous, always-on analysis that treats Claude like a coworker monitoring the feedback stream. Howie Liu described a similar pattern using Airtable's own AI to run what he calls "map-reduce" across sales transcripts — chunking long documents, analyzing each piece, then aggregating patterns about product requests, objections, positioning gaps, and competitive intelligence.

Chip Huyen (AI Engineering 101 episode) offered a counterintuitive insight: "A question that gets asked a lot is 'How do we keep up with the latest AI news?' Why do you need to keep up with the latest AI news? If you talk to the users who understand what they want or they don't want, look into the feedback, then you can actually improve the application way, way, way more." The implication for feedback analysis is that AI should bring you closer to user reality, not further from it. The best teams use AI to process more feedback faster, then use those insights to guide deeper human investigation.

Claire Vo (ChatPRD founder, "How I AI" podcast host) takes this further with specialized agents. She runs multiple domain-specific AI agents — separate personas for different types of analysis — because "I would hire different people for these jobs, so I set up different agents." One agent might specialize in analyzing NPS feedback, another in parsing feature requests, another in synthesizing competitive intelligence from user comments.

### Concrete Examples, Techniques & Prompts

**Always-on feedback triage (Boris Cherny, Anthropic):** ([▶ YouTube @46:32](https://youtu.be/We7BZVKbCVw?t=2792)) Connect Claude (or your LLM of choice) to your feedback channels (Slack, Zendesk, Intercom, email). Prompt: "Review the last week of feedback. Categorize into: bugs, feature requests, UX confusion, and praise. For each category, rank by frequency and severity. Flag any new themes that weren't present last month."

**Map-reduce transcript analysis (Howie Liu, Airtable):** ([▶ YouTube @14:49](https://youtu.be/GT0jtVjRy2E?t=889)) For long transcripts or large feedback corpora: chunk the input, run analysis on each chunk, then aggregate. This avoids context window limits and produces more thorough results than single-pass analysis.

**Specialized feedback agents (Claire Vo):** ([▶ YouTube @42:06](https://youtu.be/DIa0MYJzM5I?t=2526)) Create separate AI agents (custom GPTs, Claude Projects, etc.) with different system prompts for different feedback types. A "Feature Request Analyst" agent with instructions to categorize requests by user segment, frequency, and strategic alignment. A "Churn Risk Detector" agent focused on identifying frustration signals.

**Few-shot prompting for feedback classification (Sander Schulhoff):** ([▶ YouTube @12:18](https://youtu.be/eKuFqQKYRrA?t=738)) Provide 3-5 examples of how you'd categorize feedback, then let the model classify the rest. "This is the highest-ROI prompting technique — bad prompts get you 0% accuracy; good prompts with examples get you 90%."

### Dos, Don'ts & Next Steps

**Do:**
- Set up continuous (not periodic) AI analysis of your feedback channels
- Use few-shot prompting — give the model examples of how you'd categorize and prioritize feedback
- Create specialized agents for different feedback types rather than one general-purpose prompt
- Use AI analysis to identify where to do deeper human investigation, not to replace it

**Don't:**
- Don't trust AI summaries without spot-checking — especially for sentiment analysis and severity assessment
- Don't analyze feedback in isolation from business context — include user segment, revenue impact, and strategic priorities in your prompts
- Don't skip the "what's new this month?" question — AI is excellent at detecting emerging themes humans would miss in volume

**Next Steps:**
- [ ] Set up a weekly automated feedback digest using an LLM against your primary feedback channels
- [ ] Create 3-5 "golden examples" of how you categorize and prioritize feedback, and include them in your analysis prompts
- [ ] Experiment with specialized agents for different feedback types (bugs vs. feature requests vs. churn signals)

---

## 3. Competitive Analysis & Market Intelligence

### How AI Is Being Used

Competitive analysis has been transformed by AI's ability to rapidly process and synthesize large volumes of information. Amol Avasare (Head of Growth, Anthropic) specifically mentioned using **Anthropic's Cowork mode with the Chrome extension** for competitive teardowns — walking through competitor onboarding flows, pricing pages, and feature sets while Claude captures and analyzes everything in real time. This turns what used to be a week-long project into a same-day deliverable.

Elena Verna (Head of Growth, describing AI growth playbooks) emphasized that product-market fit now resets approximately every three months in AI products because capabilities change so rapidly. This means competitive analysis can't be a quarterly exercise — it needs to be continuous and AI-augmented. Ethan Smith (Graphite) introduced the concept of **AEO — Answer Engine Optimization** — which flips competitive analysis on its head: instead of just studying competitors, you need to understand how AI models (ChatGPT, Perplexity, Google AI Overviews) describe and recommend products in your category, because that's increasingly how buyers discover solutions. His research showed that AI citations disproportionately favor companies with strong, authentic content — particularly content on Reddit and independent review sites.

Brian Balfour (Reforge) framed ChatGPT and similar AI assistants as "the next big growth channel," arguing that understanding how AI models perceive your product relative to competitors is now as important as understanding SEO rankings.

### Concrete Examples, Techniques & Prompts

**Real-time competitive teardowns (Amol Avasare, Anthropic):** ([▶ YouTube @24:44](https://youtu.be/k-H4nsOTuxU?t=1484)) Use Claude's Cowork mode + Chrome extension to walk through a competitor's signup flow, pricing page, and key features. Ask Claude to document the flow, identify friction points, compare to your own flow, and suggest improvements.

**Answer Engine Optimization audit (Ethan Smith, Graphite):** ([▶ YouTube @6:33](https://youtu.be/iT7kq-R3Gjc?t=393)) Ask ChatGPT, Claude, Perplexity, and Google's AI Overviews: "What's the best [your product category] for [your target use case]?" Document where your product appears (or doesn't) in AI recommendations. Then ask: "Why would someone choose [competitor] over [your product]?" The responses reveal how AI models perceive your positioning.

**Continuous competitive monitoring:** Set up a recurring prompt that synthesizes recent competitor announcements, pricing changes, and feature launches from public sources. Run weekly or bi-weekly.

**Competitive positioning stress-test (adapted from Kevin Weil, OpenAI):** ([▶ YouTube @18:58](https://youtu.be/scsW6_2SPC4?t=1138)) Ask an AI model to argue the case for each major competitor in your space, then argue the case against your product. Use the output to identify positioning gaps.

### Dos, Don'ts & Next Steps

**Do:**
- Run AEO audits monthly — check how AI models describe and recommend products in your category
- Use real-time AI-assisted teardowns for competitor analysis instead of static slide decks
- Monitor how quickly competitor capabilities change (Elena Verna's "PMF resets every 3 months" principle)
- Feed competitive intelligence into your product prompts and PRD templates

**Don't:**
- Don't treat competitive analysis as a quarterly deliverable — AI makes it continuous
- Don't ignore how AI assistants perceive your product — this is a new competitive surface
- Don't rely solely on AI for competitive intelligence — combine with human judgment about strategic intent

**Next Steps:**
- [ ] Run an AEO audit: ask 3+ AI models to recommend products in your category and document where you stand
- [ ] Set up a monthly competitive teardown using AI-assisted browsing
- [ ] Create a living competitive brief that gets AI-updated monthly rather than human-updated quarterly

---

## 4. Requirements Gathering & PRD Writing

### How AI Is Being Used

PRD writing is arguably the single most discussed AI use case across all Lenny's Podcast episodes in this period. Dan Shipper (Every) described his approach as creating a reusable prompt template: "There's a sort of platonic ideal of a PRD. Write a prompt that can take my rambling thoughts and then turn that into a PRD. You spend a little bit of work to make all of the next PRDs easier to write." His Head of AI Operations captures his thought process in weekly 1:1s, converts it into prompts, and stores them in GitHub — so each successive PRD gets faster and more consistent. Critically, Dan uses Claude Code (not just chat) for this, because it can access local files — previous PRDs, design docs, user research — and incorporate that context automatically.

Lazar Jovanovic (Professional Vibe Coder) provided the most detailed planning workflow. He spends roughly 80% of his time on planning and 20% on execution, creating a stack of documents before any code is written: a **Master Plan** (10,000-foot overview of why, who, and how they feel), an **Implementation Plan** (high-level execution order), **Design Guidelines** (look/feel including CSS), a **User Journey** (step-by-step flow), and a **Tasks.md** file (actual subtasks for agent execution). He then points the AI agent at all documents with a single instruction: "Read all files first. Don't do anything before reading PRDs. Read tasks.md for next task. Execute. Tell me what you did and how to test."

Zevi Arnovitz (Meta PM) built a more sophisticated system using Cursor's `/commands` feature — reusable prompts saved directly in the codebase. His `/create plan` command takes a Linear ticket reference, fetches context from Linear automatically, and generates a full plan with scope definition, data model, UX/UI approach, validation method, grading criteria, and AI system prompt changes needed. He also maintains a **Claude.md** file in his codebase root that serves as persistent context for every Claude conversation — workflow definitions, challenge-my-thinking instructions, and project context.

### Concrete Examples, Techniques & Prompts

**Rambling-to-PRD template (Dan Shipper, Every):** ([▶ YouTube @42:45](https://youtu.be/crMrVozp_h8?t=2565)) Create a voice memo or brain dump about a feature idea. Feed it to Claude with a prompt like: "Here's my rough thinking about a feature. Turn this into a structured PRD with: problem statement, user stories, success metrics, scope (in/out), technical considerations, and open questions. Flag any gaps in my thinking." Store the prompt as a reusable template.

**Lazar's planning stack:** ([▶ YouTube @13:12](https://youtu.be/0XNkUdzxiZI?t=792))
1. Master Plan — "Why are we building this? Who is it for? How should they feel using it?"
2. Implementation Plan — "What's the high-level order? Backend first, then auth, then UI?"
3. Design Guidelines — "How should this look and feel? Include specific CSS/styling direction."
4. User Journey — "Step 1: User lands on page. Step 2: They see X. Step 3: They click Y."
5. Tasks.md — "Break into specific subtasks the agent can execute one at a time."

**Zevi's /create plan command (Cursor):** ([▶ YouTube @29:08](https://youtu.be/1em64iUFt3U?t=1748)) When a Linear ticket exists, type `/create plan STU88` and Claude fetches the ticket context, then generates: scope definition, data model, UX/UI approach, validation method, grading criteria, and system prompt changes needed.

**Claire Vo's ChatPRD approach:** ([▶ YouTube @42:06](https://youtu.be/DIa0MYJzM5I?t=2526)) Claire built ChatPRD specifically as an AI tool for PRD writing. Her approach: specialized agents that act as a "CTO who challenges you, doesn't people-please." The system prompt: "I own the problem/user experience. You own the build. Challenge me. Don't be a people pleaser."

**Self-criticism loop (Sander Schulhoff):** ([▶ YouTube @28:42](https://youtu.be/eKuFqQKYRrA?t=1722)) After generating a PRD, prompt: "Review this PRD. What's missing? What assumptions are untested? What would a skeptical engineer push back on?" Then iterate.

### Dos, Don'ts & Next Steps

**Do:**
- Create reusable PRD prompt templates and store them in a shared repo — each iteration should improve the template
- Use voice-to-text for initial brain dumps, then let AI structure them (Lazar's approach)
- Include previous PRDs as few-shot examples so the AI learns your team's format and level of detail
- Set up your AI to challenge your PRD, not just write it — "Don't be a people pleaser" (Claire Vo / Zevi Arnovitz)
- Spend 80% of time on planning documents, 20% on execution (Lazar Jovanovic)

**Don't:**
- Don't use AI to write PRDs without feeding it context (previous PRDs, user research, technical constraints)
- Don't skip the self-criticism step — always have AI review and challenge its own output
- Don't let AI-generated PRDs bypass your normal review process — they're a draft, not a final product
- Don't write PRDs in isolation — use tools that can pull context from your issue tracker, docs, and codebase

**Next Steps:**
- [ ] Create a "PRD prompt template" that includes your team's format, with 2-3 examples of past PRDs as few-shot context
- [ ] Set up a `/create plan` style command in your IDE or AI tool that pulls from your issue tracker
- [ ] Experiment with the "adversarial CTO" pattern — have AI challenge your PRD before sharing with stakeholders

---

## 5. Metrics Definition & Success Criteria

### How AI Is Being Used

Metrics definition is an area where AI excels at both generation and validation. Nicole Forsgren (DORA, GitHub) brought rigorous measurement frameworks to the AI productivity conversation, advocating for **DORA + SPACE metrics** adapted for AI-assisted teams. Her key insight: measure deployment frequency, not lines of code. Traditional productivity metrics (lines of code, story points) become meaningless when AI generates code — what matters is how often you ship to users and the quality of what ships. She emphasized tracking "developer experience" alongside throughput, because AI tools that increase output but destroy flow state aren't actually productive.

Tomer Cohen (LinkedIn CPO) shared a specific measurement formula his teams use: **(Volume × Quality) ÷ Time**. Volume is output quantity, quality is measured by user outcomes, and time is calendar time to ship. This formula works because it captures the three dimensions AI most impacts — you can produce more, at the same or better quality, faster. He tracks this at the team level and uses it to identify which teams have successfully integrated AI and which haven't.

Logan Kilpatrick (OpenAI) described building **custom GPTs specifically for OKR planning** — with forced consistency checks that flag when objectives and key results don't align, when metrics aren't measurable, or when targets seem disconnected from historical baselines.

### Concrete Examples, Techniques & Prompts

**OKR validation prompt (adapted from Logan Kilpatrick, OpenAI):** ([▶ transcript @16:50]) "Here are our team's OKRs for next quarter: [paste OKRs]. Review for: (1) Are key results measurable and time-bound? (2) Do key results actually ladder to objectives? (3) Are targets ambitious but achievable given [context about team size, historical performance]? (4) Are there any blind spots — important areas not covered? Flag issues and suggest improvements."

**Tomer's measurement formula:** (transcript @31:54) (Volume × Quality) ÷ Time. Apply this to any product activity. For PRDs: how many PRDs shipped × quality rating from stakeholders ÷ calendar days. For features: features shipped × user satisfaction delta ÷ weeks. Track before and after AI adoption.

**Nicole Forsgren's adapted DORA metrics for AI teams:** ([▶ YouTube @12:23](https://youtu.be/SWcDfPVTizQ?t=743)) Track deployment frequency (how often you ship), lead time for changes (idea to production), change failure rate (% of deployments causing issues), and time to restore service. Add: developer experience survey scores and flow state indicators.

**AI-generated success criteria (general pattern):** After writing a PRD, prompt: "Based on this PRD, suggest 3-5 success metrics we should track. For each metric, define: what we're measuring, how we'll measure it, what baseline we expect, and what target would indicate success. Flag any metrics that would be hard to instrument."

### Dos, Don'ts & Next Steps

**Do:**
- Shift from output metrics (lines of code, story points) to outcome metrics (deployment frequency, user impact)
- Use the (Volume × Quality) ÷ Time formula to benchmark AI's impact on your team
- Build AI-assisted OKR validation into your planning process
- Track developer/PM experience alongside productivity — AI tools that destroy flow aren't productive

**Don't:**
- Don't measure AI productivity by lines of code generated — it's meaningless
- Don't skip baselining before AI adoption — you need "before" numbers to prove impact
- Don't assume more output = better outcomes — quality and user impact matter more

**Next Steps:**
- [ ] Baseline your current (Volume × Quality) ÷ Time metrics before expanding AI adoption
- [ ] Set up an AI-assisted OKR review as part of your quarterly planning
- [ ] Add "deployment frequency" and "time from idea to production" as standard team metrics

---

## 6. Design & Prototyping

### How AI Is Being Used

Jenny Wen (Head of Design at Claude, Anthropic) made the boldest claim in this area: "This design process that designers have been taught, we sort of treat it as gospel. That's basically dead. You as a designer actually do not have the time to make these beautiful mocks anymore." Her argument isn't that design doesn't matter — it's that the process has fundamentally changed. Instead of the traditional discover → mock up → spec → hand off flow, designers at Anthropic now work in **rapid low-fidelity exploration** — generating multiple directions quickly, then iterating collaboratively with engineers in the actual product rather than in Figma. She described hiring for three new designer archetypes to support this shift. The role of the designer moves from "here's the design" to "helping engineers and teams execute."

Dylan Field (Figma CEO) reinforced this from the tooling side: "AI makes design, craft, and quality the new moat for startups." As code generation becomes commoditized, the companies that win are the ones with better taste and design — not better engineering. He sees design tools evolving to support AI-assisted workflows where designers work at higher abstraction levels.

Simon Willison described a practical technique: "Prototype 3 different design approaches quickly since UI creation is now 'free.' Use actual human usability testing (not AI simulation) to choose the best direction." Guillermo Rauch (v0/Vercel) introduced the concept of the **"Git commit inversion"** — instead of doing work then summarizing intent in a commit, you state intent and receive code. This means designers can go from concept to working prototype by describing what they want.

### Concrete Examples, Techniques & Prompts

**3-direction rapid prototyping (Simon Willison):** ([▶ YouTube @25:00](https://youtu.be/wc8FBhQtdsA?t=1500)) Instead of designing one mockup, generate 3 working prototypes with different approaches using Lovable, Bolt, or v0. Run actual usability tests on all three. The cost of generating each is near-zero; the value of testing real alternatives is enormous.

**Lazar's design reference technique:** ([▶ YouTube](https://youtu.be/0XNkUdzxiZI?t=792)) Instead of describing a design in words, upload a screenshot from Mobbin or Dribbble as a reference, plus code snippets from 21st.dev or DotBuild. "Tools understand code better than English" — a CSS snippet communicates design intent more reliably than a paragraph of description.

**Intent-to-prototype workflow (Guillermo Rauch, v0):** ([▶ YouTube @14:36](https://youtu.be/-QsTmu2CqhA?t=876)) Type a description of what you want into v0: "A dashboard with a sidebar navigation, a main content area showing a data table with sortable columns, and a chart above it." Get a working React prototype in seconds. Iterate by describing changes.

**Lovable's chat mode (Anton Osika):** ([▶ YouTube @19:20](https://youtu.be/DZtGxNs9AVg?t=1160)) When a prototype isn't matching your vision, switch to chat mode: "How does this work? I'm not getting what I want here, am I missing something? What should I do?" — a way to debug your intent before generating more code.

### Dos, Don'ts & Next Steps

**Do:**
- Generate multiple prototype directions and test them with real users — the cost of each prototype is now near-zero
- Use visual references (screenshots, Mobbin, Dribbble) and code snippets instead of verbal descriptions — AI tools understand code better than English
- Involve designers in the build process, not just the spec process — "helping engineers execute, not just telling them 'here's the design'" (Jenny Wen)
- Invest in taste development — Guillermo Rauch recommends tracking "exposure hours" (time spent using and studying great products)

**Don't:**
- Don't spend weeks on high-fidelity Figma mocks before testing concepts — prototype in code first
- Don't simulate usability testing with AI — Simon Willison specifically warns against this; use real humans
- Don't let designers become disconnected from implementation — the handoff model is dying
- Don't assume AI prototyping tools produce production-ready code — they produce testable prototypes

**Next Steps:**
- [ ] Try generating 3 different design directions for your next feature using Lovable, Bolt, or v0
- [ ] Experiment with providing visual references + code snippets instead of written design specs
- [ ] Discuss with your design team how the role is evolving — Jenny Wen's "three archetypes" model may be relevant

---

## 7. Stakeholder Alignment & Communication

### How AI Is Being Used

Stakeholder alignment is an area where AI augments but doesn't replace human judgment. Jessica Fain (Webflow, ex-Slack) was featured specifically on "The art of influence: the single most important skill that AI can't replace" — making the case that as AI handles more execution, the human skills of persuasion, alignment, and influence become more valuable, not less. The bottleneck in product development has shifted from coding to decision-making and alignment (a theme echoed by Alexander Embiricos at OpenAI and Jenny Wen at Anthropic).

That said, AI dramatically accelerates the artifacts of alignment. Dan Shipper's team uses AI to convert meeting notes and rambling discussions into structured decision documents — the Head of AI Operations captures processes in prompts so "every time I sat down with him and told him, 'here's how you tell a story, here's how you think about a headline,' he recorded all of it, put it into a prompt, and he never made the same mistake twice." Zevi Arnovitz uses AI to generate stakeholder-ready documents from technical plans — his `/create plan` command outputs scope, approach, validation method, and grading criteria in a format designed for review.

Julie Zhuo (former Facebook VP of Design) described the shift as moving "from managing people to managing AI" — where leaders need to get much better at specifying intent clearly, because AI (like a new hire) needs explicit context and clear success criteria to produce good work. This maps directly to stakeholder alignment: the clearer you can articulate what "good" looks like, the better AI can help you produce the artifacts that align people around it.

### Concrete Examples, Techniques & Prompts

**Meeting-to-decision-doc prompt:** "Here are the notes from our product review meeting: [paste notes]. Convert these into a structured decision document with: (1) Context/background, (2) Options discussed, (3) Tradeoffs for each option, (4) Decision made and rationale, (5) Action items with owners and dates. Flag any open questions that need follow-up."

**Stakeholder update generator:** "Here's what our team shipped this week: [paste updates]. Write a stakeholder update that: leads with user impact (not technical details), highlights risks or blockers that need executive attention, and includes 1-2 metrics that show progress. Keep it under 200 words. Tone: confident but transparent."

**Pre-meeting alignment prep (adapted from multiple sources):** Before a key meeting, prompt: "I'm presenting [feature/decision] to [audience]. Their main concerns are likely [X, Y, Z]. Draft talking points that address each concern directly. Anticipate the three hardest questions they'll ask and draft responses."

### Dos, Don'ts & Next Steps

**Do:**
- Use AI to convert messy meeting notes and discussions into clean decision documents and stakeholder updates
- Prepare for alignment meetings by having AI anticipate objections and draft responses
- Invest in your own clarity of thinking — AI amplifies clarity but also amplifies muddled thinking
- Remember that influence and persuasion are the skills AI can't replace (Jessica Fain)

**Don't:**
- Don't send AI-generated stakeholder communications without reviewing for tone, accuracy, and political sensitivity
- Don't use AI as a substitute for face-to-face alignment on high-stakes decisions
- Don't assume stakeholders will be impressed by AI-generated volume — quality and conciseness matter more

**Next Steps:**
- [ ] Create a stakeholder update template prompt tuned to your audience's priorities
- [ ] Start converting meeting notes to decision documents with AI as a standard post-meeting step
- [ ] Practice the "anticipate objections" prompt before your next high-stakes presentation

---

## 8. Developer Communication & Technical Specs

### How AI Is Being Used

The boundary between PM and engineering communication is dissolving. Tomer Cohen (LinkedIn CPO) described LinkedIn's transformation toward **"full-stack builders"** — PMs who can prototype, write basic code, and communicate with engineers in technical terms, aided by AI. His teams built specialized AI agents for different functions: a Trust Agent that catches harm vectors at the spec stage, a Growth Agent that critiques idea quality, a Research Agent that provides institutional knowledge access, and an Analyst Agent that lets anyone query data without SQL.

Zevi Arnovitz's workflow is the most detailed example: he maintains a `Claude.md` file in his codebase that provides persistent context to Claude about the project architecture, coding conventions, and technical decisions. When he creates a plan for a feature, the AI automatically generates scope definitions, data models, UX/UI approaches, and validation methods — all in language that bridges PM intent and engineering execution. His `/review` command has Claude review its own code, then he cross-reviews with multiple models (Claude, Codex) to catch issues.

Boris Cherny (Head of Claude Code) noted that at Anthropic, "everyone on the Claude Code team codes — PMs, designers, data scientists, finance." The traditional spec-handoff model is being replaced by PMs who can directly create working implementations, dramatically reducing the communication gap.

### Concrete Examples, Techniques & Prompts

**Technical spec generation (Zevi Arnovitz):** ([▶ YouTube @25:26](https://youtu.be/1em64iUFt3U?t=1526)) After exploring a feature with `/explore`, use `/create plan` to generate: scope definition, data model, UX/UI approach, validation method, grading criteria, and system prompt changes. This produces a document that both PMs and engineers can work from.

**Claude.md as persistent context:** ([▶ YouTube @25:26](https://youtu.be/1em64iUFt3U?t=1526)) Create a markdown file in your project root that describes: project architecture, key technical decisions, coding conventions, and current priorities. Every AI conversation in that project automatically loads this context.

**Cross-model code review:** ([▶ YouTube @25:26](https://youtu.be/1em64iUFt3U?t=1526)) After generating code, have multiple AI models review it. Zevi uses Claude for initial generation, then Codex for review: "Finds bugs, critical issues, medium/low issues automatically."

**LinkedIn's specialized agents (Tomer Cohen):** (transcript @19:17) Build focused agents for specific communication needs — a Trust Agent for safety/compliance review, a Growth Agent for growth-readiness review, an Analyst Agent for data access.

### Dos, Don'ts & Next Steps

**Do:**
- Maintain a project context file (Claude.md or similar) that gives AI ongoing context about your architecture and conventions
- Use AI to generate technical specs that bridge PM intent and engineering detail
- Cross-review AI-generated technical content with multiple models
- Explore building specialized agents for specific review needs (trust, growth, data)

**Don't:**
- Don't assume AI-generated technical specs are complete — they need engineering review for feasibility and edge cases
- Don't skip the "challenge my thinking" step — have AI push back on your technical assumptions
- Don't rely on a single model for review — different models catch different issues

**Next Steps:**
- [ ] Create a Claude.md (or equivalent) project context file for your main product
- [ ] Experiment with AI-generated technical specs for your next feature
- [ ] Set up a cross-model review process for technical documents

---

## 9. Building, Coding & Implementation

### How AI Is Being Used

This is the most rapidly evolving area. Boris Cherny (Head of Claude Code) states flatly: "100% of my code is written by Claude Code. I have not edited a single line by hand since November." He ships 10-30 pull requests per day, running multiple agents in parallel. Sherwin Wu (Head of Engineering, OpenAI) reported that 95% of OpenAI engineers use Codex daily, with engineers opening 70% more PRs than those not using Codex — and the gap is widening. The productivity gains are not incremental: Boris reports "productivity per engineer has increased 200%." To put this in context, he notes that previous tools achieved single-digit percentage productivity gains.

Simon Willison drew a critical distinction between **"vibe coding"** and **"agentic engineering."** Vibe coding is building without reviewing code — acceptable for personal projects and prototypes, but not for production. Agentic engineering is the professional approach: engineers review code, understand the system, and maintain quality standards while using agents for implementation. He described a **"dark factory" pattern** where companies like StrongDM built swarms of agent testers that simulate end users 24/7 (costing $10,000/day in tokens) — effectively replacing manual QA with AI QA.

For non-technical PMs, the entry ramp is getting easier. Lazar Jovanovic builds production-quality applications with zero hand-coding by investing heavily in planning documents (Master Plan, Implementation Plan, Design Guidelines, User Journey, Tasks.md) and then pointing an agent at them with: "Read all files first. Don't do anything before reading PRDs. Read tasks.md for next task. Execute. Tell me what you did and how to test."

### Concrete Examples, Techniques & Prompts

**Lazar's agent execution prompt:** ([▶ YouTube @13:12](https://youtu.be/0XNkUdzxiZI?t=792)) "Read all files in the project docs folder first. Don't do anything before reading PRDs. Read tasks.md for the next task. Execute it. Tell me what you did and how to test it."

**Boris Cherny's parallel agent workflow:** ([▶ YouTube @20:50](https://youtu.be/We7BZVKbCVw?t=1250)) Run multiple Claude Code agents simultaneously on different tasks. Each agent works on a focused, well-scoped problem. Review all PRs — 100% code review even when AI writes the code.

**Zevi's progressive escalation for PMs:** ([▶ YouTube @25:26](https://youtu.be/1em64iUFt3U?t=1526)) Start with ChatGPT for architecture questions → move to Bolt/Lovable for visual prototypes → graduate to Cursor + Claude Code for full implementation. Don't jump straight to the terminal.

**Token budget strategy (Boris Cherny):** ([▶ YouTube @26:19](https://youtu.be/We7BZVKbCVw?t=1579)) Give engineers unlimited tokens initially to experiment. "Some engineers at Anthropic spend hundreds of thousands per month in tokens." Only optimize after scaling — move to cheaper models (Haiku vs. Opus) once patterns are validated.

**StrongDM's agent QA (via Simon Willison):** ([▶ YouTube @12:41](https://youtu.be/wc8FBhQtdsA?t=761)) Build simulated versions of your dependencies (APIs, databases) and have AI agents test against them continuously. This removes rate limits and external dependencies from your testing loop.

### Dos, Don'ts & Next Steps

**Do:**
- Distinguish between vibe coding (fine for prototypes) and agentic engineering (required for production)
- Always review AI-generated code — 100% review rate, even when AI writes it
- Invest in planning documents before pointing agents at implementation
- Give teams generous token budgets initially — optimization comes after learning

**Don't:**
- Don't let AI-generated code skip code review — this is the "agentic engineering" vs "vibe coding" distinction
- Don't assume AI code is correct — Simon Willison warns of a coming "Challenger disaster" from unchecked AI code
- Don't start non-technical PMs at the terminal — progressive escalation (ChatGPT → Bolt → Cursor) works better

**Next Steps:**
- [ ] Establish a clear team policy on vibe coding vs. agentic engineering — when each is acceptable
- [ ] If you're not using Claude Code or Cursor, trial it with one team member on a bounded project
- [ ] Create planning document templates (Master Plan, Implementation Plan, Tasks.md) so any team member can direct an AI agent

---

## 10. Testing, QA & AI Evals

### How AI Is Being Used

AI evals — the practice of defining what "good" looks like and systematically measuring AI output against it — emerged as perhaps the single most important new PM competency from these episodes. Hamel Husain and Shreya Shankar (creators of the #1 eval course) described evals as "the hottest new skill for product builders." The core workflow is: create question-answer pairs that define ideal behavior → convert those into automated tests → iterate on your AI system until it passes. Brendan Foody (Mercor) put it more bluntly: "If the model is the product, the eval is the PRD."

Nick Turley (Head of ChatGPT, OpenAI) emphasized that real production failures are more valuable than benchmarks for driving improvement. His team uses actual user failures to create evals, not synthetic test cases. Kevin Weil (OpenAI CPO) explained the practical workflow: "Create Q&A pairs, define amazing answers, convert to evals, measure improvement." He also introduced the concept of **"poor man's fine-tuning"** — including examples of desired behavior directly in prompts as a fast alternative to actual fine-tuning.

At a more traditional QA level, Simon Willison described companies running "swarms of agent testers" that simulate end users 24/7 — effectively AI-powered continuous QA. Nicole Forsgren adapted her DORA metrics framework for AI-era measurement, focusing on deployment frequency and change failure rate rather than code output volume.

### Concrete Examples, Techniques & Prompts

**Eval creation workflow (Hamel Husain & Shreya Shankar):** ([▶ YouTube @1:00:56](https://youtu.be/BsWxPI9UM4c?t=3656))
1. Start with manual error analysis — actually look at where your AI is failing
2. Create a rubric defining "ideal" responses for each failure type
3. Convert rubric into automated evals (Q&A pairs with grading criteria)
4. Run evals on every model/prompt change
5. Use a "benevolent dictator" pattern — one person owns the eval set and prevents bloat

**Poor man's fine-tuning (Kevin Weil, OpenAI):** ([▶ YouTube @25:10](https://youtu.be/scsW6_2SPC4?t=1510)) Include 3-5 examples of ideal behavior in your prompt: "Here's an example input and here's what a perfect response looks like. [Repeat 3x]. Now handle this new input." This captures 80% of fine-tuning value with zero infrastructure.

**Production-failure-driven evals (Nick Turley, OpenAI):** ([▶ YouTube @23:22](https://youtu.be/ixY2PvQJ0To?t=1402)) When your AI product fails in production, capture the input, the bad output, and what the correct output should have been. Add this as a new eval case. Over time, your eval set becomes a comprehensive map of your product's failure modes.

**Continuous agent QA (Simon Willison / StrongDM):** ([▶ YouTube @12:41](https://youtu.be/wc8FBhQtdsA?t=761)) Build simulated test environments and run AI agents against them 24/7. Monitor for regressions. This catches issues that periodic manual QA misses.

### Dos, Don'ts & Next Steps

**Do:**
- Start building evals now — even simple ones. This is the new table-stakes PM competency
- Use real production failures to create evals, not synthetic benchmarks
- Include example-based "poor man's fine-tuning" in your prompts before investing in actual fine-tuning
- Have one person own the eval set to prevent bloat and maintain quality

**Don't:**
- Don't skip manual error analysis — automation should follow understanding, not replace it
- Don't rely on model provider benchmarks — your product's failure modes are unique
- Don't treat evals as a one-time exercise — update them continuously as your product evolves

**Next Steps:**
- [ ] Catalog your AI product's top 10 failure modes and create eval cases for each
- [ ] Implement "poor man's fine-tuning" — add 3-5 examples of ideal behavior to your key prompts
- [ ] Designate an "eval owner" on your team

---

## 11. Launch, Growth & Distribution

### How AI Is Being Used

The most important shift in this phase is recognizing that **shipping a feature is the starting line, not the finish line.** The PM job increasingly extends beyond launch into adoption, impact measurement, and sustained distribution. A feature that ships but doesn't change customer behavior hasn't delivered value — and AI is making it possible to track and accelerate the full journey from launch to landed outcome at a pace that wasn't feasible before.

Elena Verna (Head of Growth) warned that **product-market fit resets approximately every three months** in AI products because the underlying model capabilities keep changing. This means traditional launch cycles — build for months, launch, measure — are too slow. Her AI growth playbook emphasizes rapid iteration loops: build an MVP, get it to users in days, and iterate on AI capabilities as models improve.

Ethan Smith (Graphite) introduced **AEO — Answer Engine Optimization** — as a new growth channel. As more buyers discover products through AI assistants (ChatGPT, Perplexity, Google AI Overviews), optimizing for AI citations is becoming as important as SEO. His data shows that AI citations disproportionately favor authentic content (particularly Reddit discussions and independent reviews) over corporate marketing content. Early-stage companies have a disproportionate advantage here because AI models tend to surface niche, specific recommendations.

Brian Balfour (Reforge) framed AI assistants as "the next big growth channel" with specific implications for product launches: your product's narrative needs to be AI-legible, your documentation needs to clearly explain use cases and differentiators, and user-generated content (reviews, discussions, tutorials) becomes your most valuable growth asset.

Grant Lee (Gamma) shared a specific growth experimentation loop: "Idea in morning → functional prototype → recruit real users → run experiment in the afternoon → iterate by evening." AI tools make this possible by compressing the build cycle from weeks to hours.

### Measuring Whether a Feature Actually Landed

Across every domain — consumer SaaS, enterprise platforms, internal tools — the strongest PMs define what "landed" means *before* they ship, then track adoption through structured tiers:

| Adoption Tier | What It Measures | Example |
|---|---|---|
| **Feature shipped** | Code complete, available to users | API live, toggle enabled, GA announced |
| **Awareness** | Target users know it exists | Docs published, changelog sent, demo delivered |
| **Activation** | Users tried it for the first time | First API call, first configuration, first workflow run |
| **Sustained adoption** | Regular usage above baseline | % of eligible users/accounts actively using week-over-week |
| **Outcome achieved** | Customer behavior changed | Provisioning time reduced, manual toil eliminated, churn decreased |
| **Adoption threshold met** | Pre-defined success target hit | "Landed = 20% of eligible accounts adopted within 90 days" |

The key discipline: **define your adoption threshold before launch** (e.g., "20% of eligible accounts within 90 days," "3 named enterprise customers unblocked"). This converts "did we ship it?" into "did it solve the problem?" — which is the real measure of PM impact.

AI tools accelerate every tier: automated adoption dashboards from telemetry, AI-synthesized feedback from early adopters, anomaly detection on activation drop-off, and LLM-generated outreach for accounts that haven't activated.

### Expanding Distribution Beyond Launch Day

A feature that ships without a distribution plan is a feature that won't land. The strongest teams treat distribution as a parallel workstream, not a follow-up task. Distribution channels vary by domain but the pattern is consistent — **meet users where they already are:**

- **Documentation & tutorials** — The most underrated distribution lever. Clear docs with real examples are both the primary adoption driver for technical products and the highest-signal input for AI recommendation engines (AEO).
- **Content & community** — Blog posts, conference talks, YouTube walkthroughs, community forum answers. Authentic content from practitioners outperforms corporate marketing in both human and AI discovery.
- **Ecosystem & integrations** — Partner integrations, marketplace listings, extensions, and add-ons. Each integration is a new distribution surface.
- **In-product discovery** — Contextual prompts, onboarding flows, feature announcements inside the product itself. The lowest-friction channel for existing users.
- **Field & enablement** — For enterprise/B2B: field team enablement, customer workshops, migration guides, and named-account outreach. Often the difference between a feature existing and a customer adopting it.
- **AI-native channels (AEO)** — Optimizing for how AI assistants describe and recommend your product (Ethan Smith's AEO framework). This is the fastest-growing discovery channel and favors products with clear, specific, well-documented value propositions.

### Concrete Examples, Techniques & Prompts

**AEO audit prompt (adapted from Ethan Smith):** ([▶ YouTube @10:38](https://youtu.be/iT7kq-R3Gjc?t=638)) "Search for '[your product category] for [your use case]' and tell me which products you'd recommend and why. Where does [your product name] rank? What would change your recommendation?"

**Rapid growth experimentation (Grant Lee, Gamma):** ([▶ YouTube @1:08](https://youtu.be/3H0ngGU5pbM?t=68)) Idea → AI-generated prototype → real user test → iterate, all in one day. Use Lovable/Bolt/v0 to build testable prototypes in minutes, not weeks.

**AI-legible positioning:** Ensure your website, docs, and content clearly describe what your product does, for whom, and why — in a way that AI models can parse and recommend. Ask an AI model to summarize your product based on your public content. If the summary is inaccurate, your positioning needs work.

**Adoption tracking prompt:** After launch, use AI to synthesize adoption data: "Here's our adoption telemetry for [feature] over the past 30 days: [data]. What's the activation rate? Where are users dropping off? Which customer segments are adopting fastest and slowest? What hypotheses would you test to improve adoption?"

**Post-launch impact review prompt:** "We launched [feature] 90 days ago with a target of [adoption threshold]. Here's what happened: [data]. Did this feature land? What's the gap between where we are and our target? What are the top 3 actions to close the gap?"

### Dos, Don'ts & Next Steps

**Do:**
- Define your adoption threshold and success criteria *before* launch — "shipped" is not "landed"
- Build a distribution plan as a parallel workstream, not a post-launch afterthought
- Track adoption through structured tiers (shipped → awareness → activation → sustained use → outcome)
- Use AI to automate adoption dashboards, synthesize early-adopter feedback, and detect activation drop-off
- Plan for PMF to reset every ~3 months as AI capabilities evolve
- Start optimizing for AI citations (AEO) alongside traditional SEO
- Compress your experimentation loop — AI tools make same-day prototyping and testing possible
- Make your product narrative AI-legible (clear, specific, well-documented)

**Don't:**
- Don't treat launch as the finish line — the PM job extends through adoption and impact measurement
- Don't measure success by "feature is live" — measure by customer behavior change
- Don't plan 6-month launch cycles for AI products — the landscape will change under you
- Don't ignore AI assistants as a discovery channel — this is the fastest-growing way buyers find products
- Don't rely on corporate marketing content alone — authentic user content and strong docs drive both human and AI discovery
- Don't skip the distribution plan for internal/platform features — they need enablement, not just a changelog entry

**Next Steps:**
- [ ] For your next launch, define the adoption threshold and measurement plan before code complete
- [ ] Build an adoption dashboard that tracks the full tier: shipped → awareness → activation → sustained use → outcome
- [ ] Run an AEO audit on your product
- [ ] Try a same-day experimentation loop: idea → prototype → user test → iterate
- [ ] Review your distribution plan: are you covering docs, community, ecosystem, in-product, field, and AI channels?
- [ ] Schedule a 90-day post-launch impact review — did the feature land or just launch?

---

## 12. Team Structure, Hiring & AI Adoption

### How AI Is Being Used

The organizational implications of AI are as significant as the tactical ones. Tomer Cohen (LinkedIn CPO) implemented a **three-pillar framework: Platform, Tools, Culture**. Platform means building internal AI infrastructure; Tools means equipping every team member with AI capabilities; Culture means making AI adoption a performance expectation. His most effective change management tactics: adding "AI fluency" to hiring and performance reviews, creating exclusive early-access programs (leveraging FOMO), celebrating wins publicly with specific examples, and using "permission > mandate" — letting early adopters demonstrate value rather than forcing adoption.

Howie Liu (Airtable) restructured his entire organization into **"fast thinking" and "slow thinking" teams** (referencing Kahneman). Fast thinking teams ship major AI capabilities weekly with AI-native velocity; slow thinking teams handle infrastructure and long-term architecture. He asks himself constantly: "How would Cursor or Windsurf execute? Are we matching that pace?"

Boris Cherny's philosophy is to **"under-resource projects slightly to force teams to Claude-ify."** When a project is slightly too big for the team, they're forced to use AI to close the gap — and once they do, they never go back. He gives engineers unlimited tokens initially: "Some engineers at Anthropic spend hundreds of thousands per month in tokens." Optimize costs after learning, not before.

Eoghan McCabe (Intercom) took the most aggressive approach: 40% staff turnover, rewritten company values emphasizing resilience and high standards, and a "founder mode" culture where leadership makes unilateral decisions and owns outcomes. His view: "Great companies are founder-led. Professional CEOs are told 'don't mess up.' Founders get bored if not taking risks." After 15-16 months of this approach, Intercom went from its lowest Glassdoor rating to 98-99% leadership approval.

### Concrete Examples, Techniques & Prompts

**Tomer's adoption measurement formula:** (transcript @31:54) (Volume × Quality) ÷ Time — apply to any product activity to measure AI impact at team level.

**Boris's under-resourcing tactic:** ([▶ YouTube @10:43](https://youtu.be/We7BZVKbCVw?t=643)) Intentionally scope projects slightly beyond team capacity. The gap forces AI adoption. Once teams bridge it with AI, they don't revert.

**Howie's meeting restructuring:** ([▶ YouTube @14:49](https://youtu.be/GT0jtVjRy2E?t=889)) Replace recurring 1:1s with: sprint check-ins on AI execution (frequent, standing), topical meetings when new insights need immediate discussion, and monthly in-person sessions for relationship building. Cut all other standing meetings.

**Tomer's change management playbook:** (transcript @46:07)
1. Add AI fluency to hiring criteria and performance reviews
2. Create exclusive early-access programs (FOMO drives adoption)
3. Celebrate wins publicly with specific "before/after" examples
4. Use "permission > mandate" — let early adopters demonstrate value
5. Build an Associate Product Builder training program for non-technical staff
6. Track team-level (Volume × Quality) ÷ Time to identify who's adopted and who hasn't

### Dos, Don'ts & Next Steps

**Do:**
- Add AI fluency to your hiring criteria and performance reviews
- Give teams generous token budgets and freedom to experiment before optimizing costs
- Under-resource projects slightly to force creative AI usage
- Track AI adoption at the team level using (Volume × Quality) ÷ Time
- Restructure meetings — AI makes many status meetings unnecessary

**Don't:**
- Don't mandate AI adoption top-down without demonstrating value first — "permission > mandate" works better
- Don't optimize AI costs before teams have learned to use the tools effectively
- Don't assume your current team structure is optimal — the fast/slow thinking split may serve you better
- Don't ignore the cultural dimension — tools without culture change produces minimal adoption (Tomer's insight: "5% early adopters + 95% need management")

**Next Steps:**
- [ ] Audit your team's current AI adoption level using (Volume × Quality) ÷ Time across key activities
- [ ] Add AI fluency criteria to your next round of hiring and performance reviews
- [ ] Identify one project to intentionally under-resource as a forcing function for AI adoption
- [ ] Consider the fast thinking / slow thinking team split for your org

---

## Appendix: Tools Referenced

| Tool | Primary Use | Referenced By |
|------|------------|---------------|
| **Claude Code** | Coding, PRD writing, file analysis, automation | Boris Cherny, Dan Shipper, Zevi Arnovitz, Simon Willison |
| **Cursor** | IDE with AI coding assistance | Zevi Arnovitz, Lazar Jovanovic, multiple |
| **ChatGPT / GPTs** | Custom agents, planning, analysis | Logan Kilpatrick, Claire Vo, Zevi Arnovitz |
| **Lovable** | AI software engineer (describe → build) | Anton Osika, Lazar Jovanovic |
| **Bolt** | Text-to-app (browser-based) | Eric Simons, Zevi Arnovitz |
| **v0 (Vercel)** | Intent-to-code, design-to-prototype | Guillermo Rauch |
| **Codex (OpenAI)** | Code generation and review | Sherwin Wu, Alexander Embiricos |
| **Windsurf** | AI code editor | Varun Mohan |
| **Devin (Cognition)** | Autonomous AI engineer | Scott Wu |
| **Gamma** | AI-powered presentations | Grant Lee |
| **ChatPRD** | AI-powered PRD writing | Claire Vo |
| **Cowork (Anthropic)** | Non-coding AI automation | Boris Cherny, Amol Avasare |
| **Wispr Flow** | Voice-to-text for quick capture | Zevi Arnovitz |
| **Granola** | AI note-taking | Dan Shipper |
| **Linear** | Issue tracking (AI-integrated) | Zevi Arnovitz |
| **Mobbin / Dribbble** | Design references for AI prototyping | Lazar Jovanovic |
| **21st.dev / DotBuild** | Code templates for AI tools | Lazar Jovanovic |
| **Supabase** | Backend-as-a-service (used with Lovable/Bolt) | Anton Osika, Eric Simons |

## Appendix: Episode Index

Episodes analyzed (January 2025 – April 2026), sorted by relevance to this report:

**Tier 1 — Directly Actionable for PM Teams:**
- Zevi Arnovitz — "The non-technical PM's guide to building with Cursor" (Jan 18, 2026)
- Dan Shipper — "The AI-native startup: 5 products, 7-figure revenue, 100% AI-written code" (Jul 17, 2025)
- Lazar Jovanovic — "The rise of the professional vibe coder" (Feb 8, 2026)
- Claire Vo — "From skeptic to true believer: How OpenClaw changed my life" (Mar 29, 2026)
- Sander Schulhoff — "AI prompt engineering in 2025: What works and what doesn't" (Jun 19, 2025)
- Jenny Wen — "The design process is dead. Here's what's replacing it." (Mar 1, 2026)
- Tomer Cohen — "Why LinkedIn is turning PMs into AI-powered full stack builders" (Dec 4, 2025)
- Hamel Husain & Shreya Shankar — "Why AI evals are the hottest new skill" (Sep 25, 2025)

**Tier 2 — Strategic Context & Frameworks:**
- Simon Willison — "An AI state of the union" (Apr 2, 2026)
- Boris Cherny — "Head of Claude Code: What happens after coding is solved" (Feb 19, 2026)
- Kevin Weil — "OpenAI's CPO on how AI changes must-have skills" (Apr 10, 2025)
- Mike Krieger — "Anthropic's CPO on what comes next" (Jun 5, 2025)
- Aparna Chennapragada — "Microsoft CPO: If you aren't prototyping with AI, you're doing it wrong" (May 18, 2025)
- Howie Liu — "How we restructured Airtable's entire org for AI" (Aug 31, 2025)
- Nicole Forsgren — "How to measure AI developer productivity in 2025" (Oct 19, 2025)
- Sherwin Wu — "Engineers are becoming sorcerers" (Feb 12, 2026)
- Alexander Embiricos — "Why humans are AI's biggest bottleneck" (Dec 14, 2025)

**Tier 3 — Product Building & Growth in the AI Era:**
- Anton Osika — "Building Lovable: $10M ARR in 60 days" (Mar 9, 2025)
- Eric Simons — "Inside Bolt: Near-death to ~$40M ARR in 5 months" (Mar 13, 2025)
- Guillermo Rauch — "Everyone's an engineer now: Inside v0" (Apr 13, 2025)
- Elena Verna — "The new AI growth playbook for 2026" (Dec 18, 2025)
- Ethan Smith — "The ultimate guide to AEO" (Sep 14, 2025)
- Brian Balfour — "Why ChatGPT will be the next big growth channel" (Aug 17, 2025)
- Dylan Field — "Why AI makes design, craft, and quality the new moat" (Oct 16, 2025)
- Eoghan McCabe — "Intercom rose from the ashes by betting everything on AI" (Aug 21, 2025)
- Brendan Foody — "Why experts writing AI evals is creating the fastest-growing companies" (Sep 18, 2025)
- Chip Huyen — "AI Engineering 101" (Oct 23, 2025)

**Tier 4 — Vision & Leadership:**
- Keith Rabois — "Hard truths about building in the AI era" (Apr 12, 2026)
- Marc Andreessen — "The real AI boom hasn't even started yet" (Jan 29, 2026)
- Bret Taylor — "Future of careers, coding, agents" (Jul 31, 2025)
- Jeetu Patel — "AI is critical for humanity's survival" (Feb 26, 2026)
- Karina Nguyen — "OpenAI researcher on why soft skills are the future of work" (Feb 9, 2025)
- Scott Wu — "Inside Devin: World's first autonomous AI engineer" (May 4, 2025)
- Michael Truell — "The rise of Cursor: $300M ARR" (May 1, 2025)
- Varun Mohan — "Building Windsurf: AI code editor for 1M developers" (Apr 20, 2025)
- Amol Avasare — "Anthropic's growth: Claude is growing itself" (Apr 5, 2026)
- Benjamin Mann — "Anthropic co-founder on AGI predictions" (Jul 20, 2025)
- Julie Zhuo — "From managing people to managing AI" (Sep 21, 2025)
- Oji Udezue — "How AI is reshaping the product role" (Sep 7, 2025)
- Dhanji Prasanna — "How Block is becoming the most AI-native enterprise" (Oct 26, 2025)
- Logan Kilpatrick — "OpenAI developer relations" (early 2025)
- Grant Lee — "Gamma: Dumbest idea to $100M ARR" (Nov 13, 2025)
- Nick Turley — "Inside ChatGPT: Fastest-growing product in history" (Aug 9, 2025)
- Sander Schulhoff 2.0 — "The coming AI security crisis" (Dec 21, 2025)
