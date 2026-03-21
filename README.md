<!-- GitHub Profile README — Siddharth Vekariya -->
<!-- Paste this into your GitHub profile repo: sidvekariya510/sidvekariya510/README.md -->

<div align="center">

```
  ███████╗██╗██████╗ ██████╗ ██╗  ██╗ █████╗ ██████╗ ████████╗██╗  ██╗
  ██╔════╝██║██╔══██╗██╔══██╗██║  ██║██╔══██╗██╔══██╗╚══██╔══╝██║  ██║
  ███████╗██║██║  ██║██║  ██║███████║███████║██████╔╝   ██║   ███████║
  ╚════██║██║██║  ██║██║  ██║██╔══██║██╔══██║██╔══██╗   ██║   ██╔══██║
  ███████║██║██████╔╝██████╔╝██║  ██║██║  ██║██║  ██║   ██║   ██║  ██║
  ╚══════╝╚═╝╚═════╝ ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝  ╚═╝  ╚═╝
```

### AI-Powered SaaS Engineer · NestJS · Next.js · LLM Workflows · Azure · Python

[![Portfolio](https://img.shields.io/badge/Portfolio-siddharthvekariya.netlify.app-4ade80?style=flat-square&logo=netlify&logoColor=black)](https://siddharthvekariya.netlify.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-siddharth--vekariya-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/siddharth-vekariya)
[![Email](https://img.shields.io/badge/Email-siddharthvekariya510@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:siddharthvekariya510@gmail.com)
[![Availability](https://img.shields.io/badge/Status-Available%20for%20Freelance-4ade80?style=flat-square)](https://siddharthvekariya.netlify.app)

</div>

---

## What I actually build

I architect and ship **AI-native SaaS systems** — multi-tenant, production-ready, built to scale before you need it to.

Right now I'm the full-stack lead on **[Kavlo](https://www.kavlo.com)** — an enterprise contract intelligence platform in private beta. It connects to 50+ document sources and ERP systems via Nylas + MergeDev integrations, extracts every contract term and obligation using AI document intelligence pipelines (FastAPI + Celery + LLM), stores structured data in Supabase JSONB with dual-defense tenant isolation (RLS + app-level filtering), and triggers multi-step vendor workflows from Slack, Claude, or any MCP-connected tool. Human-in-the-loop supported.

Before that: rebuilt **[TypingBolt](https://www.typingbolt.com)** from a legacy PHP codebase. Migrated 50K+ users and 11M+ test records from MySQL to MongoDB. Added AI-personalized learning paths. Running stable in production for over a year.

I use **Claude Code** as a development orchestration layer. I own every architectural decision. AI handles execution velocity. Clients get the throughput of a small team at the accountability of one senior engineer.

---

## Architecture — how Kavlo is built

```
  ┌─────────────────────────────────────────────────────────────────────┐
  │  EXTERNAL SOURCES                                                   │
  │  Google Drive · SharePoint · Gmail · Outlook · SAP · Oracle · Slack │
  └──────────┬─────────────┬───────────────┬───────────────┬────────────┘
             │             │               │               │
  ┌──────────▼─────────────▼───────────────▼───────────────▼────────────┐
  │  INGESTION LAYER                                                    │
  │  MergeDev (file sync)  │  Nylas (email sync)  │  MCP Server         │
  │  FastAPI + Celery (document intelligence workers)                   │
  └──────────┬─────────────────────────────────────┬────────────────────┘
             │  PDF → LLM extraction → JSONB        │
  ┌──────────▼──────────────────────────────────────▼──────────────────┐
  │  CORE                                                              │
  │  NestJS API  │  Supabase / PostgreSQL (RLS + multi-tenant)         │
  │  Redis (cache + BullMQ)  │  Azure ACA (Docker + CI/CD)             │
  └──────────┬──────────────────────────┬──────────────────────────────┘
             │                          │
  ┌──────────▼──────────────────────────▼──────────────────────────────┐
  │  SURFACE                                                           │
  │  Next.js App  │  Workflow Engine (HITL)  │  Slack / Claude / Teams │
  └────────────────────────────────────────────────────────────────────┘

  Green arrows = AI pipeline   Blue = core data flow   Dashed = async
  Dual-defense isolation: Supabase RLS + application-level filtering on every query
```

---

## Stack

```
Backend    NestJS · Node.js · Python (FastAPI · Celery) · Express.js
Frontend   Next.js · React · TypeScript · Tailwind CSS · TanStack Query
Data       PostgreSQL · Supabase (RLS + JSONB) · NeonDB · MongoDB · Redis
DevOps     Azure (ACA · VM · Blob) · Docker · GitHub Actions CI/CD
Integr.    Nylas · MergeDev · WebSockets · Stripe
AI/LLM     Claude Code · MCP · OpenRouter · Document intelligence pipelines · Complex Automated workflows (HITL)
```

---

## Selected work

| Project | Scale | What I did |
|---|---|---|
| **[Kavlo](https://kavlo.com)** — Enterprise Contract Intelligence | Private Beta | Full-stack lead. Multi-tenant SaaS, document AI pipeline, MCP-native workflow automation |
| **[TypingBolt](https://typingbolt.com)** — Typing Platform (Bolt AI) | 50K+ users · 11M+ tests | Solo rebuild from PHP. MySQL → MongoDB migration. AI learning paths. |
| **KYC Portal** — Stock Market Onboarding | Production | Webcam integration, document verification, role-based dashboards |
| **Insurance Broker ERP** — Policy Management | Production | 4-panel MERN ERP: Admin · POSP · Employee · Customer |

---

## Case study — TypingBolt migration

**Problem:** Legacy PHP + MySQL platform serving 50K+ users couldn't handle concurrent test load, had no analytics infrastructure, and needed AI features added — all without downtime or data loss.

**Approach:** Full platform rebuild in Node.js + React + TypeScript. Designed a MongoDB schema that preserved all historical test data relationships. Built a staged migration pipeline: parallel write → validation → cutover → cleanup. Added background processing for analytics aggregation, CDN-backed static assets, and DB indexing strategy that kept query times predictable at scale.

**Result:** Zero downtime migration of 50K users and 11M test records. Platform running stable for 12+ months in production. AI-personalized learning paths shipped post-migration.

---

## How I work

**01 — Architecture first.**
Before any code: domain research, docs review, data model design, tenant isolation strategy, API contracts, integration boundaries. All decided before writing a line.

**02 — Claude Code execution.**
I use Claude Code & other tools as an orchestration layer. I write the implementation plans, own all architectural decisions, and review every output. Net result: small-team throughput.

**03 — Integration over mocking.**
Each module tested against real data before wiring to the next. Document pipelines process real PDFs. Auth flows tested across tenant boundaries. Nothing ships unverified.

**04 — CI/CD as a deliverable.**
Every project ends with a working deployment pipeline. GitHub Actions, Docker, Azure Container Apps or VM. Blue-green deploys where downtime isn't acceptable.

---

## GitHub stats

<div align="center">

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs?username=sidvekariya510&show_icons=true&locale=en&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=4ade80&text_color=888885)

</div>

---

## Let's talk

Building a SaaS product? Need an AI integration layer? Scaling something that's starting to show its early architectural decisions? [siddharthvekariya510@gmail.com](mailto:siddharthvekariya510@gmail.com)

**Available for full-time freelance.** Response within 24 hours.

<div align="center">

```
  kavlo.com · typingbolt.com · siddharthvekariya.netlify.app
  India · Open to remote worldwide
```

![Profile views](https://komarev.com/ghpvc/?username=sidvekariya510&color=4ade80&style=flat-square&label=profile+views)

</div>
