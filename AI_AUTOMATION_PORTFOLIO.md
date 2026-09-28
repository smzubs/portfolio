# AI Optimization & Automation Portfolio

**SM Zobayer**  
AI automation builder · Founder, Verdorian Technologies LLC  
[GitHub](https://github.com/smzubs) · [Verdorian](https://verdorian.com) · [LinkedIn](https://linkedin.com/in/smzobayer)

This page is the shortest path through the work most relevant to an AI Optimization / Automation role.

## How I approach automation

I start with the operating problem, not the model:

1. Identify repetitive, slow, error-prone, or high-friction work.
2. Map the people, systems, data, handoffs, and failure points.
3. Decide whether the right solution is an LLM, deterministic automation, an API integration, a database workflow, or a combination.
4. Prototype quickly.
5. Test output quality, edge cases, permissions, and operational failure modes.
6. Measure whether the workflow is actually faster, safer, or easier.
7. Harden, automate, monitor, and keep optimizing.

## Capability map

| Area | Hands-on work |
|---|---|
| **AI models** | Claude / Anthropic, OpenAI / ChatGPT, Gemini; choosing models by task rather than forcing one model everywhere |
| **Agents** | Claude Code agents, Codex delegation/review, MCP servers, automated review workflows |
| **Prompt / context engineering** | Structured prompts, tool/context design, output constraints, validation gates |
| **APIs / integrations** | REST APIs, JSON, webhooks, auth, SaaS integrations, serverless functions |
| **Workflow automation** | n8n, custom application workflows, scheduled/background jobs, document pipelines |
| **Data** | PostgreSQL, Supabase, SQL, Row-Level Security, reporting pipelines, KPI dashboards |
| **QA / reliability** | Validation gates, automated review, security policies, audit trails, error monitoring |
| **Delivery** | Next.js, TypeScript, JavaScript, Python, React Native / Expo, Vercel, CI/CD |

## 1. QRSafePro - field operations + compliance automation

**Problem:** Inspections, equipment tracking, and compliance documentation were fragmented across paper, spreadsheets, and manual follow-up.

**System:** A multi-tenant SaaS product where field workers scan QR codes to reach the correct inspection or inventory workflow, records are attributable and exportable, and AI can generate written OSHA programs from organization-specific information.

**Relevant automation patterns**
- QR scan -> correct workflow with no manual lookup
- Structured inspection / inventory records -> reporting
- AI document generation with a validation gate
- Database-enforced tenant isolation
- Audit-oriented recordkeeping

**Business result:** The production system is used for field workflows and reporting rather than being a demo-only prototype.

[Full case study](./case-studies/qrsafepro.md) · [Live product](https://qrsafepro.com)

## 2. PolicyPilot - AI extraction + document automation

**Problem:** Insurance teams repeatedly re-key the same information into standardized ACORD forms.

**System:** AI reads carrier PDFs, converts the content into structured policy data, stores one authoritative record, and drives automated PDF generation - including a form with 302 mapped fields.

**Relevant automation patterns**
- Unstructured PDF -> AI extraction -> structured JSON/data
- Single source of truth -> multiple downstream documents
- Type-safe data flow
- Deterministic document generation after AI extraction
- Sensitive-data access controls

[Full case study](./case-studies/policypilot.md) · [Working demo](https://policypilot-one.vercel.app)

## 3. VoicePencil - voice + AI transformation pipeline

**Problem:** Voice capture is fast, but raw transcripts still create cleanup work.

**System:** Audio capture -> transcription -> AI transformations -> structured notes, delivered inside a subscription iOS product.

**Relevant automation patterns**
- Multi-stage AI pipeline
- 16 AI content transforms
- 12 serverless functions in the application workflow
- RevenueCat entitlement logic and release automation
- AI-assisted debugging and deployment workflow

[Full case study](./case-studies/voicepencil.md)

## 4. ChangeOrderAI - operational document generation

**Problem:** Construction field changes are often documented late or poorly, which creates revenue leakage and disputes.

**System:** A contractor describes a change in plain language; AI structures scope, justification, and cost into a professional change-order workflow.

**Relevant automation patterns**
- Natural-language operational input -> structured business record
- Domain-specific output requirements
- Document generation
- Web + mobile workflow
- Contractor/job data isolation

[Full case study](./case-studies/changeorderai.md)

## 5. Claude Code + Codex orchestration - public code

I also work directly on the AI-development workflow itself. My public codex-plugin-cc repository shows a practical pattern for using Codex from Claude Code for independent review, adversarial review, delegated engineering tasks, background runs, and result retrieval.

This is a useful example of how I think about **model specialization, orchestration, review, and human-in-the-loop control**, not just prompt writing.

[Inspect the public repository](https://github.com/smzubs/codex-plugin-cc)

## Operations and analytics experience

My AI work is backed by years of operating inside metrics- and compliance-heavy environments.

At Knight Electric, I built internal tools, KPI dashboards, and digital workflows to replace paper-heavy processes. My current resume documents 99.5% accuracy across 200+ weekly compliance records with reporting for leadership and clients.

Earlier roles included safety/data operations at Amazon, product planning and forecasting at Hankook AtlasBX, and compliance recordkeeping at LG Electronics.

## What I can walk through in an interview

- How I decide what should use AI versus deterministic automation
- A PDF -> structured data -> generated-document pipeline
- Multi-tenant SaaS security with Postgres Row-Level Security
- A QR-driven field workflow that removes manual lookup steps
- How I use multiple AI agents/models for implementation and independent review
- How I design validation gates when AI output must be accurate and auditable
- How I move from operational pain point -> prototype -> production system

## Public-code / private-production boundary

Most commercial application source is private because it contains client or production implementation details. The public case studies intentionally expose the problem, workflow, architecture pattern, and business value without secrets, customer data, or proprietary infrastructure.
