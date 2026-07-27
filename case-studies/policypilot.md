# PolicyPilot

🔗 **Working demo:** [policypilot-one.vercel.app](https://policypilot-one.vercel.app) — in progress

![PolicyPilot homepage](../assets/screenshots/policypilot/home.png)

## Summary

PolicyPilot is a document-automation tool for insurance agencies. Agencies live on **ACORD forms** — the standardized paperwork that moves a policy from submission to binding — and re-key the same client and policy information across form after form. PolicyPilot uses AI to **read carrier PDFs and extract the underlying data**, then auto-fills the ACORD forms from it, including a 302-field form. Repetitive manual paperwork becomes a generated document.

## Problem

Insurance agencies re-enter the same information across many standardized forms by hand. It's slow, error-prone, and scattered — the same data retyped into document after document, with transcription mistakes creeping in along the way.

## Solution

A web app where an agent enters client and policy data once, and the system generates filled, carrier-ready ACORD PDFs from it through a controlled document-automation pipeline. One authoritative record drives every form.

## My Role

**Solo product owner and AI-assisted implementation builder** — product design, architecture direction, AI-assisted implementation, deployment, and operations.

## Development Approach

Built with an AI-assisted workflow using Claude Code / Codex. I owned the data model, the form-automation pipeline, and the type-safe data layer; AI tools accelerated implementation and refactoring.

## Key Features

- AI extraction of client and policy data from carrier PDFs
- Enter or extract data once, reuse across all forms
- Automated ACORD form generation into carrier-ready PDFs, up to 302 fields per form
- One authoritative record per client, reducing re-keying and transcription errors
- Type-safe data layer end to end

## AI / Automation Features

- AI intake: reads carrier PDFs and extracts structured policy data *(core flow)*
- Document automation: structured data → filled, pixel-accurate ACORD PDFs *(core flow)*
- Workflow automation: a single record drives every downstream form *(core flow)*

## Tech Stack

- **Frontend:** Next.js (App Router), Tailwind CSS, shadcn/ui
- **Backend / DB:** Supabase (Postgres), Drizzle ORM (type-safe data layer)
- **AI:** LLM-based extraction of policy data from carrier PDFs
- **Document generation:** headless browser rendering (Puppeteer) → filled PDF forms
- **Deployment:** Vercel

## Architecture Overview

> Illustrative pattern — not real deployment topology.

```mermaid
flowchart TD
    A[Carrier PDF or manual entry] --> B[Next.js App Router]
    B --> K[AI extraction → structured policy data]
    K --> C[Server Action]
    C --> F[(Supabase Postgres)]
    C --> H[ACORD template engine]
    H --> I[Headless render → filled PDF]
    I --> J[Download / send to carrier]
```

User action → API route → database → document-generation pipeline → filled PDF → saved/sent.

## Safety / Security / Compliance Notes

No proprietary source, customer data, or internal infrastructure detail is reproduced here. The app handles sensitive client information, so it's designed with database-enforced access control (Row-Level Security) scoping data to each agency, and a single authoritative record per client for clean data handling.

## Business Value

- Designed to reduce manual documentation and data-entry time
- Designed to cut transcription errors by sourcing every form from one record
- Designed to standardize the submission-to-binding paperwork workflow

## What I Learned

Faithful document output matters as much as the data model — carriers expect the exact, real forms, so rendering accurate fillable PDFs (rather than approximations) was central. I also learned how a single-source-of-truth record simplifies an entire downstream workflow.

## Status

**In progress** — working demo at [policypilot-one.vercel.app](https://policypilot-one.vercel.app). Private production repo.

## Next Improvements

- Support for additional form types beyond the initial ACORD set
- Carrier-specific output templates

## Screenshots / Demo

_Product homepage:_

![PolicyPilot homepage](../assets/screenshots/policypilot/home.png)

Coming soon:

- Data-entry → form-generation workflow screenshot
- Generated ACORD PDF preview
- 1–2 minute demo video

---

[← Back to portfolio index](../README.md)
