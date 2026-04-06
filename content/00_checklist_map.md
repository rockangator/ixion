# Phase A — Checklist → content modules + pilot conflict log

**Purpose:** Bind every `instacart_apm_checklist.json` item to a work module (M1–M8), appendix, or cross-cutting rule. No slide build yet.

**Module definitions (unchanged from plan):**

| Module | Focus |
|--------|--------|
| **M1** | Why invest now — business + human opening |
| **M2** | When autonomy fits — segmentation, ODD, constraints |
| **M3** | Experience evolution — customer, shopper, retailer, tradeoffs |
| **M4** | Trust, exceptions, mock specs (what AI mocks must prove) |
| **M5** | Per-order unit economics + breakeven / J-curve |
| **M6** | Risks, regulatory, safety, trust, workforce + risk register |
| **M7** | Pilot — hypothesis, where/how, vendors, MVP, timeline |
| **M8** | Metrics, learning questions, go/no-go |

---

## 1. Pilot venue / scope — **LOCKED** (Option A + aerial)

### Primary named site

**George Mason University — Fairfax, VA** (bounded geofence: campus core + adjacent Fairfax City corridors that Starship-eligible routes already cover).

### Why this site (impact + learnings)

| Criterion | Why GMU wins |
|-----------|----------------|
| **Learning rate** | Meal and class peaks create **dense, repeated demand** in a small ODD → you hit statistical power on utilization, reliability, and repeat behavior within **90 days**. |
| **Integration risk vs novelty** | Pilot is *not* “does a robot roll?” — it’s “does **Instacart’s** merchant → picker → handoff → tracking → exception → fallback **stack** work at volume?” Starting where **sidewalk autonomy is already normalized** isolates **your** product variables. |
| **Aerial credible in-pilot** | **Ground = day 0** (Starship-class sidewalk robots). **Air = phase-gated** (e.g. days 45–90 or after sidewalk readiness gate): **Wing**-style **lightweight / high-urgency** corridor (partner-operated, strict airspace + landing zone), *or* a **single hub-to-pad** lane. That satisfies **“pilot includes aerial”** without betting the go/no-go on BVLOS complexity on day one. |
| **Narrative + defense** | One named geography, one hypothesis, one metrics baseline — matches **product review** expectations and your checklist **S8-2** (“name a specific location”). |

**VERIFY before final deck:** Starship (or chosen robot partner) **current** GMU deployment status + any **public** Fairfax/campus permit references; add citations in M7.

### Aerial in the pilot (how we say it)

- **Lane A (volume):** Sidewalk robot — default for eligible baskets inside geofence.  
- **Lane B (aerial, gated):** Drone for **narrow SKU/weight/urgency** profile once **Day 0–30** sidewalk gates pass — proves **multi-modal orchestration** and answers the case’s **aerial** angle without conflating success criteria.

*(Vendor names stay aligned with Paperclip: e.g. Starship ground + Wing aerial as **phase-gated** partner; Zipline as **alternate** aerial path in appendix if needed.)*

### Alternative ODDs — **subtext only** (Phase 2 / “if we expanded”)

Use as **one line + verbal Q&A**, not parallel pilots:

| Alternative | Role in story |
|-------------|----------------|
| **Hospital / medical campus** | Controlled traffic, high trust bar — good **Phase 2** once campus playbook works. |
| **Corporate office park** | Lunch density, repeat B2B-like behavior — **second geofence** candidate. |
| **Parks, arenas, mixed retail-entertainment** | Higher permit and crowd variance — **S2-5** experiential / event drone story fits here as **follow-on**, not MVP success definition. |
| **High-rise / tower** | **S2-6** — drone-to-pad or rooftop; keep as **strategy teaser** tied to aerial Phase 2. |

### Paperclip note

`Pilot.txt` contains a **later variant** (e.g. UCSB + Bird/Lime framing). **Canonical for this project:** **GMU / Fairfax** + **phase-gated aerial**, unless you explicitly switch — keeps one thread for M7–M8 and avoids conflicting numbers across extracts.

**Economics gates:** Use **explicit dollar amounts** (e.g. **$6.50** cost-per-completed where that thread applies) everywhere; fix any `<=.50` artifacts from old extracts when we draft M8.

---

## 2. Cross-cutting (every module)

| ID | Text (short) | How to use |
|----|----------------|------------|
| **S10-2** | PM vocabulary in headers / lead-ins | Apply when drafting each module’s headline options and bullet openers. |
| **S10-3** | Ground bold claims in precedent or citation | Every module: tag bullets as **cited** vs **VERIFY** before final cut. |

---

## 3. Appendix-only (not primary deck body)

| ID | Section | Note |
|----|---------|------|
| **S5-4** | Interactive website (carrot-themed) | `supp` — only after PDF story is complete; AI fluency extra. |
| **S10-1** | “My approach to execution” hiring close | `core` in checklist but **verbal backup + optional 1 slide or Q&A**; do not bloat Part A/B. |
| **S11-1** | Full competitive landscape | Q&A deep dive |
| **S11-2** | Regulatory by state/city | Q&A |
| **S11-3** | Hardware vendor matrix (full) | Q&A; M5/M7 stay summary |
| **S11-4** | 3-year financial model | Q&A |
| **S11-5** | Shopper retraining program detail | Q&A; M6 stays summary + principles |
| **S11-6** | Phase 2 drone deep dive | Q&A; M2/M7 cite one-line teaser |
| **S11-7** | Agentic / Isaac / ROS2 stack depth | Q&A; M7 names stack at pilot level |
| **S11-8** | Time-of-day utilization model | Q&A |

---

## 4. Full checklist mapping → M1–M8

### S1 — Business case & strategic context → **M1**

| ID | Route |
|----|--------|
| S1-1 | M1 |
| S1-2 | M1 (anchor; repeat touch in M5) |
| S1-3 | M1 |
| S1-4 | M1 (north star; align wording with M6 workforce — don’t ignore displacement) |
| S1-5 | M1 |
| S1-6 | M1 |
| S1-7 | M1 (partner-first; echoed in M7) |
| S1-8 | M1 (evolution narrative) |
| S1-9 | M1 |
| S1-10 | M1 (Waymo playbook → bridge to M2/M7 gating) |

### S2 — Segmentation → **M2**

| ID | Route |
|----|--------|
| S2-1 | M2 |
| S2-2 | M2 |
| S2-3 | M2 (+ ties to M7 primary ODD) |
| S2-4 | M2 |
| S2-5 | M2 (niche; Phase 2 / appendix if deck tight) |
| S2-6 | M2 (niche; same) |
| S2-7 | M2 |
| S2-8 | M2 |

### S3 — Human angle / personas → **M1** (primary)

| ID | Route |
|----|--------|
| S3-1 | M1 (story bullet or speaker note) |
| S3-2 | M1 |
| S3-3 | M1 |
| S3-4 | M1 |
| S3-5 | M1 (spine: evolution before data — pairs with S1-8) |

### S4 — Experience evolution (3 users) → **M3** + **M4**

| ID | Route |
|----|--------|
| S4-1 | M3 |
| S4-2 | M3 |
| S4-3 | M3 |
| S4-4 | M4 (exceptions) |
| S4-5 | M4 (trust patterns) |
| S4-6 | M3 (tradeoffs; can repeat one line in M6) |

### S5 — UI mocks → **M4**

| ID | Route |
|----|--------|
| S5-1 | M4 |
| S5-2 | M4 |
| S5-3 | M4 |
| S5-4 | Appendix (supplementary deliverable) |

**Note:** Your prep **fleet / pilot map mocks** are not separate JSON rows; treat as **M4** (internal ops dashboard) and **M7** (pilot control panel) mock specs when we draft those modules.

### S6 — Unit economics → **M5**

| ID | Route |
|----|--------|
| S6-1 | M5 |
| S6-2 | M5 |
| S6-3 | M5 |
| S6-4 | M5 (summary); detail → S11-3 |
| S6-5 | M5 |
| S6-6 | M5 |

### S7 — Risks & workforce → **M6**

| ID | Route |
|----|--------|
| S7-1 | M6 |
| S7-2 | M6 |
| S7-3 | M6 |
| S7-4 | M6 |
| S7-5 | M6 |
| S7-6 | M6 |

### S8 — Pilot design → **M7**

| ID | Route |
|----|--------|
| S8-1 | M7 |
| S8-2 | M7 |
| S8-3 | M7 |
| S8-4 | M7 |
| S8-5 | M7 |
| S8-6 | M7 |
| S8-7 | M8 (learning questions; drafted with M7, lives in M8 doc) |
| S8-8 | M8 (go/no-go; pairs with S9) |

### S9 — Metrics → **M8**

| ID | Route |
|----|--------|
| S9-1 | M8 |
| S9-2 | M8 |
| S9-3 | M8 |
| S9-4 | M8 |
| S9-5 | M8 |
| S9-6 | M8 |

### S10 — Candidate angle → **Appendix / verbal** (+ optional one slide later)

| ID | Route |
|----|--------|
| S10-1 | Appendix + talk track (optional final slide after you approve) |
| S10-2 | Cross-cutting |
| S10-3 | Cross-cutting |

### S11 — Supplementary → **Appendix**

| ID | Route |
|----|--------|
| S11-1 — S11-8 | Appendix (Q&A / follow-up) |

---

## 5. Coverage summary (by module)

| Module | Checklist IDs covered |
|--------|------------------------|
| **M1** | S1-1 — S1-10, S3-1 — S3-5 |
| **M2** | S2-1 — S2-8 |
| **M3** | S4-1, S4-2, S4-3, S4-6 |
| **M4** | S4-4, S4-5, S5-1, S5-2, S5-3 (+ fleet/pilot map mocks from prep, not in JSON) |
| **M5** | S6-1 — S6-6 |
| **M6** | S7-1 — S7-6 |
| **M7** | S8-1 — S8-6 |
| **M8** | S8-7, S8-8, S9-1 — S9-6 |
| **Appendix** | S5-4, S10-1, S11-1 — S11-8 |

**Explicit case prompt coverage:** Items tagged `explicit` in JSON are distributed across M1–M8 so nothing drops (why invest, when drones make sense, shopper+customer experience, per-order cost, risks, pilot how/where, MVP, learn, metrics, mocks).

---

## 6. Next step (Phase B)

Draft **`content/M1_why_now.md`** using:

- `Paperclip generated/strategy-deliverables.md` + `Paperclip extracted/strategy.txt`
- Checklist rows S1-* and S3-*

**Pilot:** Locked to **GMU / Fairfax**, **sidewalk day 0 + phase-gated aerial**; alternatives (hospital, parks, corporate) = subtext only — see §1 above.
