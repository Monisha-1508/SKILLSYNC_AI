<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:001E3C,50:0070AD,100:17ABDA&height=200&section=header&text=SkillSync%20AI&fontSize=60&fontColor=ffffff&fontAlignY=38&desc=Your%20AI-Powered%20Placement%20Preparation%20Platform&descAlignY=58&descSize=18&animation=fadeIn" width="100%"/>

<br/>

<img src="https://img.shields.io/badge/SkillSync-AI%20Platform-0070AD?style=for-the-badge&logo=buffer&logoColor=white&labelColor=001E3C" height="35"/>

<br/><br/>

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Visit%20Now-17ABDA?style=for-the-badge&labelColor=001E3C)](https://skillsync-ai.capgemini-demo.placeholder.io)
[![Documentation](https://img.shields.io/badge/Docs-Read%20Here-0070AD?style=for-the-badge&labelColor=001E3C)](#-table-of-contents)
[![Report Bug](https://img.shields.io/badge/Bug-Report%20Issue-FF6B6B?style=for-the-badge&labelColor=001E3C)](https://github.com/Monisha-1508/Capegemini_Skillsync/issues)

<br/>

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.115-009688?style=flat-square&logo=fastapi&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-15-black?style=flat-square&logo=next.js&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-Orchestration-1DB954?style=flat-square&logo=langchain&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o-412991?style=flat-square&logo=openai&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-Tracing-F5A800?style=flat-square&logo=opentelemetry&logoColor=black)

<br/>

![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Build](https://img.shields.io/badge/Build-Passing-brightgreen?style=flat-square&logo=github-actions)
![Tests](https://img.shields.io/badge/Tests-5%2F5%20Passing-brightgreen?style=flat-square&logo=pytest)
![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-0070AD?style=flat-square)
![Hackathon](https://img.shields.io/badge/Capgemini-Hackathon%202026-FF6B35?style=flat-square)

<br/>

> **Built for the Capgemini Hackathon - AI-Assisted Learning Track**
>
> *Six specialised agents. One traced pipeline. A placement-ready plan that shows its work at every step.*

</div>

---

## Table of Contents

<details open>
<summary><strong>Click to expand</strong></summary>

- [What is SkillSync AI?](#what-is-skillsync-ai)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [The Six Agents](#the-six-agents)
- [LangGraph Pipeline](#langgraph-pipeline)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [API Reference](#api-reference)
- [Dashboard Panels](#dashboard-panels)
- [Running Tests](#running-tests)
- [Project Structure](#project-structure)
- [Security and Proctoring](#security-and-proctoring)
- [Observability](#observability)
- [Contributing](#contributing)

</details>

---

## What is SkillSync AI?

<div align="center">

```
+---------------------------------------------------------------------------+
|                                                                           |
|   Tell SkillSync the role you are chasing and the hours you have.        |
|   It maps your skill gap, drafts three week-by-week routes,              |
|   lines up curated resources, and keeps a readable trail of              |
|   every decision it made - so the plan you follow is one                 |
|   you can question, not just one you received.                           |
|                                                                           |
+---------------------------------------------------------------------------+
```

</div>

SkillSync AI is a full-stack, multi-agent placement preparation platform that turns a three-minute intake form into a personalised, week-by-week study roadmap. Unlike generic learning platforms, every decision is explained, every resource is scored, and every checkpoint is proctored - making the system accountable by design.

<table>
<tr>
<td align="center" width="33%">

**Intelligent Gap Analysis**

Profiles your current skill level against industry-standard role requirements using ESCO/O*NET taxonomy with an India placement overlay.

</td>
<td align="center" width="33%">

**Three-Route Roadmaps**

Generates Safe, Target, and Stretch variants of your study plan - each sized to your actual available hours and deadline.

</td>
<td align="center" width="33%">

**Full Transparency**

Every agent step is streamed to your screen in real time. No black boxes. The reasoning is shown as it happens, not summarised after the fact.

</td>
</tr>
</table>

---

## Key Features

<div align="center">

| Feature | Description | Status |
|:---:|:---|:---:|
| **Skill Gap Map** | Radar chart of 41 skills mapped against target role requirements | Live |
| **Three-Variant Roadmap** | Safe / Target / Stretch routes with feasibility scoring | Live |
| **Curated Resources** | Trust-scored free and paid resources locked by week | Live |
| **FSRS Revision Deck** | Spaced-repetition flashcards using the FSRS-4.5 algorithm | Live |
| **Proctored Checkpoints** | Anti-cheat weekly MCQ tests with copy-paste and tab-switch detection | Live |
| **Mock Interviews** | Role-specific 20-question interview banks scored on rubric | Live |
| **Dynamic Reflow** | Missed weeks are merged forward, keeping the plan realistic | Live |
| **Learning Recovery** | AI diagnosis plus micro-evaluation for recurring checkpoint failures | Live |
| **Gamification** | Points, levels, and achievement badges across all learning activities | Live |
| **Deadline Alerts** | Pace-tracking banners that fire when progress trails the runway | Live |
| **Audit Trail** | Full agent audit log with confidence scores streamed live | Live |
| **Validation Sign-off** | Independent validator agent checks every plan before delivery | Live |

</div>

---

## System Architecture

```mermaid
graph TB
    subgraph CLIENT["Browser Client - Next.js 15"]
        LP[Landing Page]
        OB[Onboarding Flow]
        DB[Dashboard - 9 Panels + 9 Tabs]
        SSE[SSE Stream - Live Agent Trace]
    end

    subgraph GATEWAY["FastAPI Gateway - Python 3.11"]
        AUTH[Auth Router - JWT + BCrypt]
        PROF[Profiles Router - Intake + Personas]
        DASH[Dashboard Router - Aggregated View]
        RM[Roadmap Router - Select + Progress + Reflow]
        WT[Weekly Test Router - Board + Start + Answer]
        REV[Revision Router - Deck + Review]
        INT[Interview Router - Start + Answer]
        REC[Recovery Router - Status + Start + Answer]
        EXP[Explain Router - Skill + Resource + Replan]
    end

    subgraph PIPELINE["LangGraph Agent Pipeline"]
        SUP{Supervisor Orchestrator}
        AG1[Profiling Agent]
        AG2[Roadmap Architect]
        AG3[Resource Curator]
        AG4[Coach and Adapter]
        AG5[Output Validator]
        AG6[Mock Interviewer]
    end

    subgraph DATA["Data Layer"]
        DB2[(SQLite / Postgres - Async SQLAlchemy)]
        GRAPH[Skill Graph - 41 nodes, 6 families]
        RBANK[Resource Bank - Trust-scored corpus]
        PBANK[Project Bank - Role-tagged projects]
        OTEL[OpenTelemetry - Traces + Logs]
    end

    CLIENT -->|REST + SSE| GATEWAY
    GATEWAY -->|Invoke| PIPELINE
    PIPELINE -->|Read/Write| DATA
    GATEWAY -->|Read/Write| DATA

    style CLIENT fill:#17ABDA,color:#001E3C,stroke:#0070AD
    style GATEWAY fill:#0070AD,color:#ffffff,stroke:#001E3C
    style PIPELINE fill:#001E3C,color:#ffffff,stroke:#17ABDA
    style DATA fill:#F0F4F8,color:#001E3C,stroke:#0070AD
```

---

## The Six Agents

```mermaid
graph LR
    A["Profiling Agent\n─────────────\nMaps self-ratings onto\n41-node skill graph\nFills gaps with inference"]
    B["Roadmap Architect\n─────────────\nGenerates Safe, Target\nand Stretch week-by-week\nroutes with feasibility"]
    C["Resource Curator\n─────────────\nTrust-scores every\nresource against 5-factor\nformula, locks by week"]
    D["Coach and Adapter\n─────────────\nAssesses engagement\nsignals, proposes and\napplies re-plans"]
    E["Output Validator\n─────────────\n5 independent checks\nprerequisite ordering\ntrust floor, feasibility"]
    F["Mock Interviewer\n─────────────\nRole-specific Q banks\nrubric grading, section\nbreakdowns + benchmarks"]

    A --> B --> C --> D --> E
    D -.->|replan loop| B
    F -.->|independent| E

    style A fill:#17ABDA,color:#001E3C,stroke:#0070AD,stroke-width:2px
    style B fill:#0070AD,color:#ffffff,stroke:#001E3C,stroke-width:2px
    style C fill:#001E3C,color:#ffffff,stroke:#17ABDA,stroke-width:2px
    style D fill:#38D9A9,color:#001E3C,stroke:#0070AD,stroke-width:2px
    style E fill:#FF6B6B,color:#ffffff,stroke:#001E3C,stroke-width:2px
    style F fill:#CC5DE8,color:#ffffff,stroke:#001E3C,stroke-width:2px
```

### Agent Responsibilities

<details>
<summary><strong>Profiling Agent</strong></summary>

- Accepts learner self-ratings across 41 skill nodes grouped into 6 families
- Infers skill levels for un-rated nodes using graph proximity
- Produces a gap map with covered / developing / gap / unknown buckets
- Generates a radar chart across skill families
- Provides a confidence score that drives the responsible AI disclosure

</details>

<details>
<summary><strong>Roadmap Architect</strong></summary>

- Reads the gap map and target role to draft three plan variants
- Calculates feasibility score from hours available vs hours needed
- Sequences skills so prerequisites always precede dependents
- Marks blackout weeks and sizes each milestone to the weekly hour budget
- Supports dynamic re-planning when the Coach flags a pace gap

</details>

<details>
<summary><strong>Resource Curator</strong></summary>

- Scores every resource against a 5-factor trust formula (authority, recency, depth, free-access, community signal)
- Enforces a trust floor - resources below 0.55 are excluded
- Locks resources to the week they become available based on roadmap unlock state
- Respects free/paid budget mode set at intake

</details>

<details>
<summary><strong>Coach and Adapter</strong></summary>

- Reads engagement signals (completion rate, quiz scores, streak)
- Proposes a re-plan when pace trails the runway by a configurable threshold
- Applies approved re-plans by redistributing remaining milestones
- Drives the dynamic reflow engine for missed weeks

</details>

<details>
<summary><strong>Output Validator</strong></summary>

- Runs 5 independent checks: resource trust floor, prerequisite ordering, feasibility margin, skill coverage, plan completeness
- Signs off with overall pass / flagged status
- Provides narration overrides that personalize the displayed rationale without touching underlying data

</details>

<details>
<summary><strong>Mock Interviewer</strong></summary>

- Maintains role-specific 20-question banks across 4 interview drives
- Supports MCQ and open-ended question types
- Grades answers on a rubric with per-dimension scoring
- Produces post-round reports with section breakdowns and drive benchmarks
- Anti-cheat proctoring matches the weekly checkpoint system

</details>

---

## LangGraph Pipeline

```mermaid
sequenceDiagram
    participant U as Learner
    participant FE as Next.js Frontend
    participant BE as FastAPI Backend
    participant SUP as LangGraph Supervisor
    participant DB as Database

    U->>FE: Submit intake form
    FE->>BE: POST /api/profiles
    BE->>SUP: Invoke pipeline
    SUP->>SUP: profile_gaps node
    SUP-->>FE: SSE: profiling_complete
    SUP->>SUP: build_roadmap node
    SUP-->>FE: SSE: roadmap_ready
    SUP->>SUP: curate_resources node
    SUP-->>FE: SSE: resources_locked
    SUP->>SUP: draft_revision_deck node
    SUP-->>FE: SSE: deck_built
    SUP->>SUP: validate_plan node
    SUP-->>FE: SSE: validation_done
    SUP->>DB: Persist all outputs
    BE-->>FE: Pipeline complete
    FE->>U: Dashboard loads with full plan
```

---

## Tech Stack

<div align="center">

### Backend

| Layer | Technology | Purpose |
|:---:|:---|:---|
| **Runtime** | Python 3.11+ | Core language |
| **Framework** | FastAPI 0.115 | Async REST API + SSE streaming |
| **Orchestration** | LangGraph 0.2 | 5-node supervisor agent graph |
| **LLM** | OpenAI GPT-4o-mini / Azure OpenAI | Agent reasoning and generation |
| **ORM** | SQLAlchemy 2.0 (async) | Database access layer |
| **Database** | SQLite (dev) / PostgreSQL (prod) | Persistent storage |
| **Auth** | PyJWT + BCrypt | JWT authentication |
| **Observability** | OpenTelemetry | Distributed tracing + logging |
| **Spaced Rep** | FSRS-4.5 | Revision deck scheduling |

### Frontend

| Layer | Technology | Purpose |
|:---:|:---|:---|
| **Framework** | Next.js 15 (App Router) | React SSR/SSG |
| **Styling** | Tailwind CSS 3 | Utility-first styling |
| **Charts** | Recharts | Radar, bar, and progress charts |
| **Icons** | Lucide React | Consistent icon set |
| **Animations** | CSS keyframes | Confetti, balloons, sparkles |
| **Streaming** | EventSource (SSE) | Live agent trace display |

</div>

---

## Getting Started

### Prerequisites

```bash
# Required
Python 3.11+
Node.js 18+
npm 9+

# Optional (for live LLM)
OpenAI API Key  OR  Azure OpenAI credentials
```

### 1 - Clone the Repository

```bash
git clone https://github.com/Monisha-1508/Capegemini_Skillsync.git
cd Capegemini_Skillsync
```

### 2 - Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv .venv

# Activate (Windows)
.venv\Scripts\activate

# Activate (macOS / Linux)
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 3 - Frontend Setup

```bash
cd frontend
npm install
```

### 4 - Environment Configuration

Create `backend/.env` and fill in the values below:

```env
# LLM Provider - use "simulated" for offline demo, "openai" for live
LLM_PROVIDER=simulated

# OpenAI (if LLM_PROVIDER=openai)
OPENAI_API_KEY=sk-...

# Azure OpenAI (if LLM_PROVIDER=azure_openai)
AZURE_OPENAI_ENDPOINT=https://your-resource.openai.azure.com/
AZURE_OPENAI_API_KEY=...
AZURE_OPENAI_CHAT_DEPLOYMENT=gpt-4o

# Database (defaults to SQLite)
DATABASE_URL=sqlite+aiosqlite:///./data/skillsync.db

# CORS
CORS_ORIGINS=http://localhost:3000
```

### 5 - Run the Application

**Terminal 1 - Backend**

```bash
cd backend
uvicorn main:app --reload --port 8000
```

**Terminal 2 - Frontend (Development)**

```bash
cd frontend
npm run dev
```

**Terminal 2 - Frontend (Production build)**

```bash
cd frontend
npm run build
npm start
```

### 6 - Open the App

```
Frontend  ->  http://localhost:3000
API Docs  ->  http://localhost:8000/docs
Health    ->  http://localhost:8000/api/health
```

### Demo Account

The backend seeds a demo account automatically on first run:

```
Email    :  demo@skillsync.ai
Password :  skillsync-demo
```

Five pre-built personas (Aarav, Priya, Rohan, Sneha, Vikram) are also available from the onboarding screen to skip the intake form entirely.

---

## Configuration

<details>
<summary><strong>LLM Provider Options</strong></summary>

| Value | Description |
|:---|:---|
| `simulated` | Fully offline - deterministic mock responses, no API key needed |
| `openai` | OpenAI API - requires `OPENAI_API_KEY` |
| `azure_openai` | Azure OpenAI - requires endpoint, key, and deployment name |

</details>

<details>
<summary><strong>Token Economy</strong></summary>

SkillSync is designed to consume minimal tokens. The profiling and roadmap agents use structured prompts with deterministic post-processing so the LLM only reasons about gaps and priorities, not formatting. Resource curation and validation run against a pre-scored corpus, not live search.

</details>

<details>
<summary><strong>Database Options</strong></summary>

```env
# SQLite (default, zero config)
DATABASE_URL=sqlite+aiosqlite:///./data/skillsync.db

# PostgreSQL (production)
DATABASE_URL=postgresql+asyncpg://user:pass@localhost:5432/skillsync
```

</details>

---

## API Reference

<details>
<summary><strong>Authentication</strong></summary>

| Method | Endpoint | Description |
|:---:|:---|:---|
| `POST` | `/api/auth/register` | Create a new account |
| `POST` | `/api/auth/login` | Log in, receive JWT |
| `GET` | `/api/auth/me` | Get current user profile |

</details>

<details>
<summary><strong>Profiles and Onboarding</strong></summary>

| Method | Endpoint | Description |
|:---:|:---|:---|
| `GET` | `/api/personas` | List available demo personas |
| `POST` | `/api/profiles` | Create profile from intake form |
| `POST` | `/api/profiles/from-persona/{key}` | Instant profile from persona |
| `GET` | `/api/profiles/mine` | List all plans for current user |
| `GET` | `/api/profiles/{id}/onboarding-stream` | SSE: live agent trace |

</details>

<details>
<summary><strong>Dashboard and Roadmap</strong></summary>

| Method | Endpoint | Description |
|:---:|:---|:---|
| `GET` | `/api/dashboard/{profile_id}` | Full aggregated dashboard |
| `POST` | `/api/roadmap/{id}/select` | Switch active variant |
| `POST` | `/api/roadmap/{id}/progress` | Log week progress |
| `POST` | `/api/roadmap/{id}/replan/propose` | Ask Coach for re-plan |
| `POST` | `/api/roadmap/{id}/replan/decide` | Apply or reject re-plan |
| `POST` | `/api/roadmap/{id}/reflow/{week}` | Merge missed week forward |

</details>

<details>
<summary><strong>Weekly Checkpoints</strong></summary>

| Method | Endpoint | Description |
|:---:|:---|:---|
| `GET` | `/api/weekly-test/{id}/board` | Checkpoint board state |
| `POST` | `/api/weekly-test/{id}/start` | Start a sitting |
| `POST` | `/api/weekly-test/{id}/answer` | Submit an answer |

</details>

<details>
<summary><strong>Revision, Interview and Recovery</strong></summary>

| Method | Endpoint | Description |
|:---:|:---|:---|
| `GET` | `/api/revision/{id}/deck` | Fetch due flashcards |
| `POST` | `/api/revision/{id}/review` | Grade a flashcard (FSRS) |
| `POST` | `/api/interview/{id}/start` | Start a mock round |
| `POST` | `/api/interview/{id}/answer` | Submit interview answer |
| `GET` | `/api/recovery/{id}/{week}/status` | Recovery gate status |
| `POST` | `/api/recovery/{id}/{week}/start` | Start micro-evaluation |
| `POST` | `/api/recovery/{id}/answer` | Submit recovery answer |

</details>

---

## Dashboard Panels

<div align="center">

```
+----------------------------------------------------------------------------+
|                          SKILLSYNC DASHBOARD                              |
+------------+------------+------------+------------+------------------------+
| Skills     | Plan       |Feasibility | Revision   | Plan Check             |
| Covered    | Progress   |  Score     |   Deck     | Validator Sign-off     |
| 0/41       |   0%       |   44%      | 18 due     | All Clear              |
+------------+------------+------------+------------+------------------------+
|  0 points - Getting your bearings  [=========>    ]  150 pts to next level |
+----------------------------------------------------------------------------+
| Overview | Gap Map | Roadmap | Progress | Resources | Revision | ...      |
+----------------------------------------------------------------------------+
|                                                                            |
|   Gap Map Summary          |   Engagement Signals                         |
|   ──────────────────────   |   ──────────────────────                     |
|   Radar: 5 skill families  |   Completion  Streak  Last quiz              |
|   8 gaps, 33 unknowns      |                                              |
|                            |                                              |
|   Selected Route           |   Output Validator Sign-off                  |
|   ──────────────────────   |   ──────────────────────                     |
|   safe  [target-active]    |   All checks passed                          |
|   stretch                  |   Resource trust floor  PASS                 |
|                            |   Prerequisite ordering PASS                 |
+----------------------------------------------------------------------------+
```

</div>

| Tab | Panel | What it shows |
|:---:|:---|:---|
| **Overview** | Summary bento grid | Key metrics, gamification bar, gap snapshot, validator sign-off |
| **Gap Map** | Radar + skill buckets | 41 skills across 6 families, covered/developing/gap counts |
| **Roadmap** | Week-by-week schedule | Active milestones, reflow indicators, feasibility, re-plan controls |
| **Progress** | Week log table | Log complete/partial/missed, trigger reflow for missed weeks |
| **Resources** | Trust-scored cards | Curated resources per skill, locked until week unlocked |
| **Revision** | FSRS flashcard deck | Flip cards, grade Again/Hard/Good/Easy, due count live |
| **Mock Interview** | Round simulator | Pick drive and round, answer under timer, post-round report |
| **Checkpoint** | Proctored MCQ + Recovery | Weekly test board, anti-cheat sitting, learning recovery panel |
| **Validation** | Full validator report | All 5 checks, pass/flagged status, timestamps |

---

## Running Tests

```bash
cd backend

# Set PYTHONPATH (Windows PowerShell)
$env:PYTHONPATH = "C:\path\to\Capegemini_Skillsync"

# Set PYTHONPATH (macOS / Linux)
export PYTHONPATH=/path/to/Capegemini_Skillsync

# Run all tests
.venv/Scripts/python -m pytest tests/ -v     # Windows
.venv/bin/python -m pytest tests/ -v         # macOS / Linux
```

### Test Results

```
============================= test session starts ==============================
platform win32 -- Python 3.13.0, pytest-8.4.2

tests/test_profiling_e2e.py::test_profiling_persona_cold_run[aarav]   PASSED
tests/test_profiling_e2e.py::test_profiling_persona_cold_run[priya]   PASSED
tests/test_profiling_e2e.py::test_profiling_persona_cold_run[rohan]   PASSED
tests/test_profiling_e2e.py::test_profiling_persona_cold_run[sneha]   PASSED
tests/test_profiling_e2e.py::test_profiling_persona_cold_run[vikram]  PASSED

========================== 5 passed in 3.23s ===================================
```

---

## Project Structure

```
Capegemini_Skillsync/
|
+-- backend/
|   +-- agents/                  # LangGraph agent implementations
|   |   +-- supervisor.py        # 5-node LangGraph pipeline
|   |   +-- profiling.py         # Skill gap analysis
|   |   +-- roadmap_architect.py # 3-variant roadmap generation
|   |   +-- resource_curator.py  # Trust-scored resource selection
|   |   +-- coach.py             # Engagement + re-plan logic
|   |   +-- validator.py         # 5-check output validation
|   |   +-- interviewer.py       # Mock interview generation
|   |   +-- weekly_test.py       # MCQ generation + grading
|   |   +-- learning_recovery.py # Diagnosis + micro-evaluation
|   |   +-- reflow.py            # Deterministic week reflow
|   |   +-- project_advisor.py   # Completed-roadmap project suggestions
|   |
|   +-- data/
|   |   +-- skill_graph.json     # 41-node skill knowledge graph
|   |   +-- resource_bank.py     # Curated + trust-scored resource corpus
|   |   +-- project_bank.py      # Role-tagged project suggestions
|   |   +-- demo_personas.json   # 5 pre-built learner personas
|   |   +-- golden_evals.json    # Golden evaluation dataset
|   |
|   +-- models/
|   |   +-- database.py          # SQLAlchemy async models
|   |   +-- schemas.py           # Pydantic request/response schemas
|   |
|   +-- routers/
|   |   +-- auth.py              # JWT register/login/me
|   |   +-- profiles.py          # Intake + onboarding SSE stream
|   |   +-- dashboard.py         # Aggregated dashboard endpoint
|   |   +-- roadmap.py           # Progress, replan, reflow
|   |   +-- revision.py          # FSRS deck + review
|   |   +-- weekly_test.py       # Proctored checkpoint board
|   |   +-- interview.py         # Mock interview rounds
|   |   +-- recovery.py          # Learning recovery flow
|   |   +-- explain.py           # Skill/resource/replan explainer
|   |
|   +-- utils/
|   |   +-- auth.py              # Password hashing + JWT
|   |   +-- gamification.py      # Points, levels, badges
|   |   +-- skill_graph.py       # Graph traversal helpers
|   |   +-- responsible_ai.py    # Confidence + disclosure
|   |   +-- seed.py              # DB seeding + demo account
|   |   +-- tracing.py           # OpenTelemetry setup
|   |
|   +-- tests/
|   |   +-- test_profiling_e2e.py
|   |
|   +-- config.py                # Pydantic settings (env-driven)
|   +-- main.py                  # FastAPI app + CORS + router wiring
|
+-- frontend/
|   +-- src/
|   |   +-- app/
|   |   |   +-- page.js              # Landing page
|   |   |   +-- login/page.js        # Login + register
|   |   |   +-- onboarding/page.js
|   |   |   +-- dashboard/page.js    # Full dashboard with 9 tabs
|   |   |   +-- plans/page.js        # My plans account hub
|   |   |
|   |   +-- components/
|   |   |   +-- panels/              # 11 dashboard panel components
|   |   |   +-- OnboardingTrace.js
|   |   |   +-- GamificationReward.js
|   |   |   +-- Celebration.js
|   |   |   +-- AlertBanner.js
|   |   |
|   |   +-- lib/
|   |       +-- api.js               # Thin fetch wrapper + auth token
|   |       +-- AuthContext.js       # React auth state
|   |
|   +-- tailwind.config.js           # Capgemini brand tokens
|   +-- next.config.mjs              # API proxy to :8000
|
+-- .gitignore
+-- README.md
```

---

## Security and Proctoring

SkillSync includes a full anti-cheat system for both weekly checkpoints and mock interviews.

```mermaid
graph LR
    subgraph PROCTOR["Proctoring System"]
        CP[Copy-Paste Detection]
        TS[Tab Switch Counter]
        FS[Fullscreen Monitor]
        TM[Per-Question Timer]
        AS[Auto-Submit on Violation]
    end

    subgraph GATE["Celebration Gate"]
        CP -->|0 attempts| PASS
        TS -->|max 3 switches| PASS
        FS -->|maintained| PASS
    end

    PASS -->|All conditions met| CELEB[Full Celebration Overlay]
    PASS -->|Any flag fires| BLOCK[Celebration Suppressed]

    style PROCTOR fill:#001E3C,color:#ffffff,stroke:#17ABDA
    style GATE fill:#0070AD,color:#ffffff,stroke:#001E3C
    style CELEB fill:#38D9A9,color:#001E3C,stroke:#0070AD
    style BLOCK fill:#FF6B6B,color:#ffffff,stroke:#001E3C
```

- **Copy-paste events** are captured and counted per sitting
- **Tab visibility changes** are tracked with a per-category counter
- **Fullscreen exits** are detected and logged
- **Timers** are per-question and auto-submit when they hit zero
- The **celebration overlay** is withheld entirely if any proctoring flag fires

---

## Observability

```mermaid
graph TD
    AGT[Agent Step] -->|traced_step ctx mgr| SPAN[OpenTelemetry Span]
    SPAN --> ATTR[Attributes: agent_name, action, confidence, output_summary]
    ATTR --> AUDIT[AuditLog Table - Postgres / SQLite]
    AUDIT --> DASH[Dashboard - Audit Trail Panel]
    SPAN --> CONSOLE[Console Exporter - Dev Mode]

    style AGT fill:#0070AD,color:#ffffff
    style SPAN fill:#F5A800,color:#001E3C
    style AUDIT fill:#001E3C,color:#ffffff
    style DASH fill:#17ABDA,color:#001E3C
```

Every agent step emits an OpenTelemetry span with the agent name, action taken, confidence score, and a plain-English output summary. These are persisted to the `AuditLog` table and surfaced verbatim in the dashboard's Audit Trail panel so a learner (or a hackathon judge) can read exactly what each agent did and how confident it was.

---

## Contributing

Contributions, issues, and feature requests are welcome.

1. **Fork** the repository
2. **Create** your feature branch: `git checkout -b feature/YourFeature`
3. **Commit** your changes: `git commit -m 'Add YourFeature'`
4. **Push** to the branch: `git push origin feature/YourFeature`
5. **Open** a Pull Request

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:17ABDA,50:0070AD,100:001E3C&height=120&section=footer&animation=fadeIn" width="100%"/>

<br/>

**Built with care for the Capgemini Hackathon 2026 - AI-Assisted Learning Track**

<br/>

[![Made with Python](https://img.shields.io/badge/Made%20with-Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Powered by FastAPI](https://img.shields.io/badge/Powered%20by-FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![Built on Next.js](https://img.shields.io/badge/Built%20on-Next.js-black?style=flat-square&logo=next.js&logoColor=white)](https://nextjs.org)
[![LangGraph](https://img.shields.io/badge/Orchestrated%20with-LangGraph-1DB954?style=flat-square)](https://github.com/langchain-ai/langgraph)

<br/>

*Reasoning shown at every step, by design.*

</div>
