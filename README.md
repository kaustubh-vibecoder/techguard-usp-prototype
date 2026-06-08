# TechGuard USP — Unified Service Platform
### Interactive prototype · Salesforce Director PM take-home assignment

---

## 🔗 Live demo

**[Open the prototype →]https://kaustubh-vibecoder.github.io/techguard-usp-prototype/*

Best viewed in **Chrome or Edge** on desktop at **1440×900 or higher**.

---

## What this prototype is

A functional product mockup for **TechGuard's Unified Service Platform (USP)** — an AI-first, proactive IT service resolution system built on Salesforce Agentforce, Data Cloud, Slack, and MuleSoft. The prototype demonstrates product logic, AI workflow, and UX across three personas and three horizons.

The strategic thesis is that the **portal-to-ticket era of IT service is dissolving**. AI doesn't bolt onto the ticket workflow — it dissolves the ticket itself. The prototype shows what that change looks like in practice: one continuous incident traveling through three personas with three AI-to-human handoffs.

**Personas demonstrated:**
- **Maya** — Customer Service Agent (Frontline · Service Cloud Console)
- **Rohan** — IT Operations Engineer (Backend · Slack + Telemetry)
- **Maria** — Field Service Technician (On-site · Field Service Mobile)

**Horizons demonstrated:**
- **H1 · Year 1 — Augmented Service** (AI in the loop, humans close the loop)
- **H2 · Year 2 — Autonomous Service** (Agents act, not just suggest)
- **H3 · Years 3–5 — Outcome Platform** (TechGuard becomes a platform vendor)

---

## How to view (~7 min self-guided tour)

The prototype opens to the **Home** view with a top-navigation bar to switch between sections. The recommended path:

### 1. Home (~1 min)

Read the hero thesis. Note the live counter top-right showing the proposed **North Star Metric — AROE (Autonomous Resolved Outcomes per 1,000 endpoints/month)**, currently tracking at ~87 with a Y1 target of 100. Scan the three persona cards and the three-horizon roadmap.

### 2. ▶ Canonical Demo (~3 min) — *the centerpiece*

Click the prominent orange **"Start Canonical Demo"** button.

This walks the **predictive server failure** journey end-to-end — the canonical journey map from §5.2 of the product document. The same incident travels across all three personas with three AI-to-human handoffs.

**Navigation:** Use `→` and `←` arrow keys, or the on-screen Next / Prev buttons, to advance through nine steps. Press `R` to restart.

**Key moments to look for:**
- **Step 3** — the blast-radius classifier deciding which steps auto-approve vs. require human sign-off
- **Steps 4, 6, 9** — the three AI-to-human handoffs (Agent → Rohan, Agent → Maria, Insight Loop → Rohan)
- **Step 8** — the counterfactual "T-0 — the failure that wasn't"
- **Architectural callouts** in blue boxes throughout (hybrid retrieval, planner/action separation, Trust Dial)

### 3. Maya — Customer Service Agent (~1 min)

Click **"Maya · CSA"** in the top navigation. Salesforce Service Cloud Console mock during a live customer call. Three things to observe:

1. The **pre-populated Endpoint Graph context strip** — the caller's full profile loaded automatically the moment the call connected
2. The **Agent Assist panel** showing what the Triage Agent already completed (12-point diagnostic, restart executed, feed verified restored) before Maya finished greeting the caller
3. The **auto-drafted wrap-up** with one-click approval, plus the customer-owned Trust Dial card at bottom right

### 4. Rohan — IT Operations (~1 min)

Click **"Rohan · ITOps"**. A Slack-style surface plus a telemetry dashboard. The center channel `#predictive-alerts` shows the same predictive alert from the Canonical Demo, plus a Cross-Domain RCA example (H2) and an Insight Loop suggestion (H3 federated learning).

The right rail shows the trust/audit queue, eval suite results, and weekly insights — the **trust infrastructure that makes autonomy scalable**.

### 5. Maria — Field Technician (~1 min)

Click **"Maria · Field"**. Two phone frames:
- **Left phone** — morning day plan with the predictive NVR-swap job highlighted, parts pre-staged, route optimized
- **Right phone** — in-job AR-overlay procedure with step-by-step swap instructions and voice documentation

The capabilities sidebar on the left tags every feature by horizon.

### 6. Metrics & Architecture (~1 min)

Click **"Metrics & Architecture"**. Contains:

- The **three-layer architecture diagram** (Surfaces · Agentforce Runtime · Data Cloud Endpoint Graph)
- The **goal tree** (6 supporting metrics under the AROE North Star)
- The **unit economics table** — ~$65–70M Y3 net P&L impact, ~$24–27M Y1 investment, ~16-month payback
- **Guardrails and counter-metrics** — including Field Tech NPS and CSA career mobility, because deflection metrics should not improve at the cost of dignity

---

## Horizon coverage at a glance

Every capability in the prototype carries a color-coded horizon badge so the roadmap is legible from any screen:

| Horizon | Theme | Representative capabilities visible in the prototype |
|---|---|---|
| 🟢 **H1 · Y1** | Augmented Service | Endpoint Graph · Frontline Copilot · Backend Triage Agent · Field Mobile Companion · Top-20 Use Case Library · Trust & Audit Layer |
| 🟡 **H2 · Y2** | Autonomous Service | Autonomous Action Library + Blast-Radius Classifier · Predictive Maintenance · Cross-Domain RCA · Per-Client Trust Dial · Agentforce Voice · Auto-Dispatch |
| 🟣 **H3 · Y3-5** | Outcome Platform | Federated Cross-Tenant Learning · Self-Healing Closed Loop · Outcome-Based Pricing · Vertical Agent Marketplace · USP-as-a-Platform |

---

## Design decisions worth noting

- **One unified prototype, not three separate persona prototypes.** USP is by definition a unified platform — three separate prototypes would have contradicted the architectural thesis. The prototype demonstrates three *surfaces* (Service Cloud Console, Slack, Field Mobile) on one Endpoint Graph.
- **The canonical journey as an interactive timeline.** The predictive-failure flow from §5.2 of the product document is rendered as a step-through walkthrough so the AI-to-human handoffs are explicit, not implied.
- **Horizon badges everywhere.** Tagging every feature by horizon makes the roadmap visible at a glance from any screen, rather than requiring readers to re-consult the strategy document.
- **Counter-metrics on equal footing with the North Star.** Field Tech NPS, CSA career mobility, and re-open rate are surfaced in the Metrics view to demonstrate the measurement framework explicitly guards against gaming.

---

## What this prototype is not

- **Not a production-grade frontend implementation.** Per the assignment brief, the focus is product logic, AI workflow, and UX — not frontend engineering. The prototype is a single HTML file with vanilla JS and Tailwind.
- **Not a backend integration.** Real implementation would use the Salesforce Models API, Agentforce runtime, Data Cloud, and MuleSoft. The prototype simulates state and agent behavior to demonstrate the user experience and product logic.
- **Not a customer-facing surface.** By design — per §6.4 of the product document, *no standalone client portal* is on the roadmap. Customer-side interactions appear via Slack, voice, email, and embedded in TechGuard's existing surfaces.

---

## Technical notes

- **Single HTML file** — no build step, no installation, opens by double-click
- **Browser** — Chrome, Edge, or Safari (latest versions). Optimized for desktop at 1440×900 or higher
- **Connectivity** — Tailwind CSS loads via CDN; requires internet for full visual styling. Functionally usable without internet, though layout will degrade
- **Keyboard shortcuts** (on Canonical Demo screen only):
  - `→` next step
  - `←` previous step
  - `R` restart

An **offline-capable version** with Tailwind inlined is available on request.

---

## Companion deliverables

- **Product Strategy & Specification Document** — 11-section strategy document covering strategic context, persona pain prioritization, phased solutions roadmap, technical architecture, tradeoffs, metrics, operating plan, and risks-to-validate
- **Presentation Deck (<20 slides)** — executive walkthrough intended for the live presentation round

*Both delivered separately by email as well as included in this repo.*

---

## Author

**Kaustubh Chaudhary**
Submission date: 7 June 2026

---

*Thank you for reviewing. I look forward to walking the prototype live in the next round.*
