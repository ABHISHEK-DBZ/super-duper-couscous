# Exit Capsule Generator — Switch Multi-Agent Workforce & Architecture

> **Autonomous AI Dependency Resilience, Cryptographic Exit Capsules & Real-Time Slack Multi-Agent Collaboration via Switch.**

[![Switch Powered](https://img.shields.io/badge/Switch-Connected-3B82F6?logo=slack&logoColor=white)](https://switch.run)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python: 3.11+](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)](https://python.org)
[![React: 18](https://img.shields.io/badge/Frontend-React%20%7C%20Vite-61DAFB?logo=react&logoColor=white)](https://react.dev)
[![Tests: 49/49 Passing](https://img.shields.io/badge/Tests-49%2F49%20Passing-22C55E?logo=pytest&logoColor=white)](https://pytest.org)

---

## 📖 Overview

**Exit Capsule Generator** is an enterprise-grade developer intelligence and dependency migration platform. When maintaining Python repositories, libraries become deprecated, unmaintained, yanked, or incompatible. 

Exit Capsule Generator addresses this challenge through a transparent, evidence-first principle:
> *"AI proposes. The tool verifies in an isolated sandbox. The developer approves. Tests provide evidence."*

Behind the scenes, the entire multi-agent orchestration is coordinated through **Switch Console** and **Switch Gateway**, bridging autonomous AI specialists directly into a **Slack `#action` collaboration channel** for real-time visibility, human review, and milestone broadcasts.

---

## 🤖 The 6 Specialist Switch Agents

Rather than running monolithic scripts or simulated prompt chains, the system deploys **six discrete specialist agents** registered in the Switch Gateway. Each agent carries a defined identity, canonical responsibilities, and specific room memberships:

```
                  ┌─────────────────────────────────────────────────────────┐
                  │                 EXIT CAPSULE WORKFLOW                   │
                  └──────────────────────────┬──────────────────────────────┘
                                             │
                                   [Repository Submitted]
                                             │
                                             ▼
                                  ┌──────────────────────┐
                                  │  exit-orchestrator   │
                                  │  Coordinates tasks   │
                                  └──────────┬───────────┘
                                             │
                                             ▼
                                  ┌──────────────────────┐
                                  │     exit-analyst     │
                                  │  AST & Risk Scoring  │
                                  └──────────┬───────────┘
                                             │
                                             ▼
                                  ┌──────────────────────┐
                                  │    exit-architect    │
                                  │ Migration Evaluation │
                                  └──────────┬───────────┘
                                             │
                                             ▼
                                  ┌──────────────────────┐
                                  │    exit-verifier     │
                                  │ Isolated Sandbox Run │
                                  └──────────┬───────────┘
                                             │
                                             ▼
                                  ┌──────────────────────┐
                                  │     exit-auditor     │
                                  │ Capsule & Seal Audit │
                                  └──────────┬───────────┘
                                             │
                                             ▼
                                  ┌──────────────────────┐
                                  │     exit-planner     │
                                  │ 15-Point Action Plan │
                                  └──────────┬───────────┘
                                             │
                                             ▼
                                  [Developer Approval Gate]
                                             │
                                             ▼
                                🔒 Cryptographic Exit Capsule
```

### Detailed Agent Profiles:

| Agent Name | Canonical Role | Switch UUID / Identity | Primary Responsibilities |
| :--- | :--- | :--- | :--- |
| **`exit-orchestrator`** | Orchestrator | `cc70db26-fba8-4e68-9679-a6bffe723954` | Project lead. Listens for repo scan triggers, routes subtasks to specialists, and tracks end-to-end execution. |
| **`exit-analyst`** | Static Code Analyst | `4a1eb1d7-b8ca-43bc-937b-9fe96ce40082` | Traverses Python ASTs, maps imported symbols, counts call expressions, detects unpinned/yanked packages, and calculates 0–100 risk scores. |
| **`exit-architect`** | Migration Architect | `cc843406-f1d5-49aa-a438-fbc78825e546` | Designs migration routes, identifies breaking API changes, evaluates candidate replacements, and reviews proposals. |
| **`exit-verifier`** *(alias `exit-verify`)* | Verification Engineer | `0a831616-86f2-45e0-94cb-9c0490b40eb9` | Provisions temporary virtual environments, runs 10-point isolated verification, verifies symbol compatibility, and records test outputs. |
| **`exit-auditor`** | Cryptographic Auditor | `766d0871-b5b8-4f63-952f-6ad18fcbb3ec` | Validates verification evidence, inspects seal-chain integrity, ensures tamper-evident ledger consistency, and rejects unverified claims. |
| **`exit-planner`** | Implementation Planner | `4fcf1193-95af-450d-83bb-29452a4e3c2b` | Generates prioritized 15-point step-by-step action plans, dependency checklists, and tailored prompts once developer approval is signed. |

---

## 📡 Channel & Bridge Setup (Switch Gateway & Slack)

### 1. Architecture Topology
- **Switch Console & Core:** Local daemon managing Gateway (`:60398`), Control API (`:54291`), and PostgreSQL (`:60400`).
- **Target Room:** `action` (`29ef14a7-572f-46d9-8d59-883d13b70f35`).
- **Slack Bridge:** Room `action` is bridged bidirectionally to Slack. Messages posted by agents appear in real-time in the Slack `#action` channel, and developer Slack messages relay back to Switch.
- **Fail-Safe & Decoupling:** All Switch notifications are best-effort; core repository scanning, isolated test executions, and cryptographic approval continue smoothly even if the network or Switch Gateway drops.

### 2. Live Channel Observability Feed
The backend exposes:
- `GET /api/switch/status`: Health check, active rooms, and workforce presence.
- `GET /api/switch/workforce`: Real-time roster of the 6 agents, active rooms, and connector status.
- `GET /api/switch/rooms/{room_id}/messages`: Live chat stream from the Slack `#action` room for frontend observability.
- `POST /api/switch/notify`: Broadcast console allowing developers and backend workers to post milestones directly into the room.

---

## 🔒 Cryptographic Approval & Exit Capsule Verification

Exit Capsule Generator strictly enforces that **AI code changes never touch production code automatically**:

1. **SHA-256 Digest Sealing:** Every capsule is sealed deterministically with a SHA-256 digest calculated over normalized JSON metadata, test results, AST evidence, and risk profiles.
2. **Version-Linked Approvals:** Approvals require both `capsule_sha256` and `capsule_version`. If a capsule is regenerated or modified after developer review, approval fails with `HTTP 409 Conflict`.
3. **Audit Ledger:** Every seal event, scan, and approval is immutably logged and visible in the **Governance & Audit Trail** view (`/api/audit-logs`).

---

## 🛠️ Installation & Running the Project

### Prerequisites
- **Python 3.11+**
- **Node.js 18+** & npm
- **Switch Console** running locally (`127.0.0.1:60398`) with Slack bridge connected to `#action`.

### 1. Clone the Repositories
```bash
git clone https://github.com/ABHISHEK-DBZ/ancient-skull.git
cd ancient-skull
```

### 2. Backend Setup
```bash
# Set up Python virtual environment
python -m venv venv
venv\Scripts\activate   # Windows
# source venv/bin/activate # Linux/Mac

# Install dependencies
pip install -r backend/requirements.txt

# Run backend regression test suite (49 tests)
python -m pytest backend/tests -v

# Start the Backend Server (Port 8000)
python -m uvicorn app.main:app --app-dir backend --host 127.0.0.1 --port 8000 --reload
```

### 3. Frontend Setup
```bash
cd frontend

# Install packages
npm install

# Run frontend test suite (8 tests)
npm test -- --run

# Run TypeScript check & build
npm run build

# Start Frontend Dev Server (Port 5173)
npm run dev
```

### 4. Access the Dashboard
Open your browser to:
- **Command Center:** [http://localhost:5173](http://localhost:5173)
- **AI Workforce Command Center:** [http://localhost:5173?tab=workforce](http://localhost:5173?tab=workforce)
- **Governance & Audit Trail:** [http://localhost:5173?tab=audit-logs](http://localhost:5173?tab=audit-logs)
- **Exit Capsules:** [http://localhost:5173?tab=capsules](http://localhost:5173?tab=capsules)
- **Interactive Swagger Docs:** [http://localhost:8000/docs](http://localhost:8000/docs)

---

## 🔬 CLI Usage (Headless Automation)

You can analyze any repository and generate capsules directly from the terminal:

```bash
# Headless AST analysis, PyPI risk scoring, and capsule creation
python -c "import sys; sys.path.insert(0, 'backend'); from app.cli import main; sys.argv = ['cli', 'analyze', 'path/to/repo', '--no-ai']; main()"
```
Output artifacts generated:
- `capsule-report/capsule.json`: Machine-verifiable cryptographic capsule.
- `capsule-report/capsule.md`: Developer-facing executive summary.

---

## 🛡️ Security & Privacy Guarantee

- **No Secrets Pushed:** Tokens, OAuth client secrets, and database passwords are never hardcoded or pushed to public Git trees.
- **Isolated Sandbox Execution:** Test runs execute in isolated sub-environments without modifying the host system.
- **Zero Hallucination Tolerance:** Package maintenance scores, version lag, and yank states are fetched deterministically from PyPI; never invented.

---

## 👥 Contributors & Acknowledgements
- Built for the **Switch Hackathon** by **Abhishek & Team**.
- Powered by **Switch Console & Multi-Agent Collaboration Protocol**.
