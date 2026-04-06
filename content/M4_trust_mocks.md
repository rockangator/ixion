# M4 — Trust, exceptions, and mock briefs (AI fluency spine)

**Scope:** Checklist **S4-4**, **S4-5**, **S5-1**, **S5-2**, **S5-3**. **S5-4** (microsite) → appendix only — see `00_checklist_map.md`.  
**Sources:** `Paperclip extracted/CX.txt` (INS-3 revised package — exceptions + trust URLs + screen briefs), `Paperclip generated/cx-deliverables-part2.md` (exception summary matrix + mock list fragments).  
**Prep:** Fleet / ops dashboard + pilot map (**APM Case Prep**) — **system-thinking** mocks beyond a single app skin.  
**Upstream:** **`M3_experience.md`** (blueprint H1–H11).

---

## 1. Checklist coverage

| ID | Addressed |
|----|-----------|
| S4-4 | §3 exception flows A/B/C + §4 notify matrix |
| S4-5 | §2 three trust patterns + precedent links |
| S5-1 | §5.1 **Mock A** — checkout / mode selector |
| S5-2 | §5.2 **Mock B** — live tracking (robot or drone state) |
| S5-3 | §5.3 **Mock C** — shopper/ops handoff + §5.4 **Mock D** — fleet ops (differentiator) |

---

## 2. Core argument — what this slide proves (not “pretty pictures”)

**Trust in autonomous grocery is designed, not assumed.** Three **product interventions** carry the story: **(1) mode clarity** — the customer always knows *what* is coming and *who* monitors it; **(2) ETA honesty** — ranges and confidence track dock, corridor, and weather variance; **(3) exception recovery** — when the machine stops, the UI names the state, names the owner, and offers a **time-bound** or **human** fallback. **Mocks** should evidence those decisions across **customer**, **shopper**, and **ops** — otherwise the deck reads like a concept video, not a PM review.

---

## 3. Trust-building patterns (S4-5) — ship + precedent

### 3.1 Mode clarity (Waymo-style)

| Element | Ship |
|---------|------|
| UI | Persistent **mode chip** (Human / **Robot** / **Drone**), vehicle illustration, route treatment matches modality (sidewalk vs air corridor). |
| Copy pattern | e.g. **“Autonomous sidewalk robot”** + **“Monitored by remote support.”** |
| Why | Removes **ambiguity** when no human courier is at the door. |

**Sources (CX.txt / INS-3):**  
https://waymo.com/waymo-one  
https://waymo.com/waymo-one-austin/

### 3.2 ETA confidence bands (Lyft / Uber-style)

| Element | Ship |
|---------|------|
| UI | **Range** (e.g. 12–18 min) + **confidence** (High / Updating), updates on state changes (dock queue, corridor, weather). |
| Copy pattern | e.g. **“Arrives in 12–18 min (high confidence).”** |
| Why | **False precision** erodes trust faster than a wide band. |

**Sources:**  
https://help.lyft.com/hc/en-us/articles/115013078668-Scheduled-rides-for-passengers  
https://www.uber.com/us/en/ride/elite/

### 3.3 Exception recovery (Amazon-style)

| Element | Ship |
|---------|------|
| UI | One card: **what happened** (plain) → **what we’re doing** → **by when** → **one primary CTA** (wait / human fallback / reschedule). |
| Copy pattern | e.g. **“Delivery attempted…”** + next step + proof + timing. |
| Why | **Predictable recovery** beats silent spinner. |

**Sources:**  
https://track.amazon.com/  
https://shipping.amazon.com/insights-and-news/how-to-track-your-package

---

## 4. Exception flows — slide-ready (S4-4)

### A) Robot stuck

| Element | Spec |
|---------|------|
| **Trigger** | No movement **>90s** off planned stop (tune in pilot). |
| **Notify** | Customer: push + in-app banner. Ops: console alert. Picker/store: only if retrieval likely. |
| **Tree** | **Recoverable ≤5 min** → remote reroute → **ETA band updates**. **Not recoverable >5 min** → **human fallback courier** from nearest hub. |
| **Customer copy** | *“Robot paused. We’re rerouting now. New ETA: 14–22 min.”* (example band) |
| **Picker** | *“Stand by for possible retrieval.”* → *“No action”* or *“Retrieve order.”* |
| **Retailer** | *“Dock exception active”* + custody status. |

### B) Drone signal lost

| Element | Spec |
|---------|------|
| **Trigger** | C2/link quality below threshold. |
| **Notify** | Customer: push + **SMS** (safety-first). Ops: **critical** alert. Store: relay-prep if payload integrity unclear. |
| **Tree** | Signal returns in safety window → resume → **tighten** band. Else → **safe land** → **ground courier relay**. |
| **Customer copy** | *“Safety check in progress. Ground backup is being arranged.”* |
| **Picker** | *“Drone diverted”* + replacement prep yes/no. |
| **Retailer** | Payload integrity / restock instruction. |

### C) Customer not home / no unlock

| Element | Spec |
|---------|------|
| **Trigger** | Arrival + **3** unanswered unlock attempts. |
| **Notify** | Push → SMS → **call** cascade; ops timer; store return/restage possible. |
| **Tree** | Response in **5-min grace** → secure unlock → complete. **Safe drop** allowed → photo/proof. **No safe drop** → hub/store → **redelivery** / policy. |
| **Customer copy** | *“We’re here. Unlock now or choose redelivery / drop option.”* |
| **Picker** | *“Attempted delivery”* + next custody owner. |
| **Retailer** | *“Return incoming”* — inventory = attempted. |

### Summary matrix (deck-friendly)

| Exception | Customer | Picker | Retailer | Channels | Fallback |
|-----------|----------|--------|------------|----------|----------|
| Robot stuck | Recovery state | Optional retrieve task | Incident + SLA | Push, in-app, SMS | Human courier / reschedule / return |
| Drone link loss | Safety-first pause | Ops / ground handoff | If dock/roof contract | Push, in-app, SMS | Ground crew / new window |
| Not home | Countdown + options | If return trip | If inventory return | Push, in-app, SMS/voice | Locker, hub, redelivery |

---

## 5. Mock briefs — priority for PDF + case “AI fluency”

### Tier 1 — **Must** (maps directly to prompt + rubric)

| Mock | Checklist | CX screen name | Must show |
|------|-----------|----------------|-----------|
| **A** | **S5-1** | Checkout — mode selector | Eligibility (zone/basket), **Human vs Robot vs Drone** (or locked to pilot modes), **price/time tradeoff**, trust line (“monitored by remote support”). |
| **B** | **S5-2** | In-transit (normal) | **Mode chip**, map, **ETA range + confidence**, proximity (“2 stops away” optional). |
| **C** | **S5-3** | Picker — dock handoff | **Assign to robot / load** flow, **scan seal**, **one-tap** confirm, mistake prevention. |

### Tier 2 — **Strongly recommended** (your prep + PM signal)

| Mock | Role | Must show |
|------|------|-----------|
| **D** | **Internal ops / fleet** | **Active AV count**, **delivery time**, **failed / exception count**, **cost per delivery** (pilot metric placeholders), **zones** on small map, **weather** strip, **battery** health — proves **platform thinking**. |
| **E** (optional) | Exception | **Robot stuck** or **recovery choice** card — proves **S4-4** in pixels. |

### Tier 3 — **Cut if slide budget tight**

- Substitution approval, seal verification standalone, drone-specific last mile (merge into **B** with mode toggle), retailer portal incident row, pilot “control panel” map (or **one** map reused in **M7**).

### Pilot map mock (**M7 overlap**)

If the deck already has **D**, add **lightweight** geofence + “eligible order” highlight on **M7** instead of a sixth full UI chrome.

---

## 6. Full numbered designer spec (from CX.txt — INS-3)

Use for **AI image / HTML mock** prompts; **collapse** to Tier 1–2 for slides.

1. Checkout mode selector — curious, risk-aware; eligibility, constraints, tradeoffs, default.  
2. Order confirmed + dual-track — picker + vehicle reserved; two timelines; first ETA band.  
3. Substitution approval — countdown; no-delay framing.  
4. Seal / load verification — custody, tamper/temp iconography.  
5. In-transit normal — mode chip, route, band + trend.  
6. Exception robot stuck — cause, owner, fallback timer.  
7. Recovery choice — wait vs human vs cancel + **time/cost** impact.  
8. Arrival + secure unlock — one-tap, identity, safety copy.  
9. Unavailable flow — grace timer, safe drop, redelivery.  
10. Completion + trust repair — proof, mode feedback, credit if incident.

**Part2 / alternate list** also names: **last mile robot** (etiquette), **last mile drone** (safety copy), **ETA band widening** — merge into **B** and **E** as states, not separate slides.

---

## 7. Fleet ops dashboard (**Mock D**) — field list from prep

| Widget | Purpose |
|--------|---------|
| **Active robots / drones** | Live fleet by modality (pilot: mostly ground + 0–N aerial). |
| **Delivery time (p95 / avg)** | Ops health vs SLA. |
| **Failed deliveries / exceptions** | Stuck, link loss, not-home taxonomy. |
| **Cost per delivery** | Pilot placeholder tied to **M5/M8** — even if “TBD” in UI, shows intent. |
| **Zones** | Campus geofence + lane status. |
| **Weather** | Degrade predictor for robot SLA. |
| **Battery / mission state** | Fleet readiness. |

**Feeling:** calm control room — **not** consumer glossy; slightly **dense** is good for “PM loves this.”

---

## 8. Headline options (slide)

1. **“Trust = mode clarity + honest ETAs + recovery you can predict.”**  
2. **“When the robot stops, the product is the exception UX.”**  
3. **“Three UI interventions that decide adoption.”**

**AI fluency one-liner (footer):** “Mocks generated with [tool] — customer, picker, and ops surfaces.”

---

## 9. Visual spec (content-only)

- **Layout:** 2×2 grid **or** primary **customer** large + **picker** + **fleet** thumbnails.  
- **Consistency:** Same **Instacart-adjacent** green/neutral system when you build (avoid generic purple); **no** trademarked Instacart logo unless you have rights — “concept UI” label if needed.  
- **Drone panel:** Subtle **safety / air corridor** cue vs sidewalk path in **B**.

---

## 10. VERIFY / QA

- [ ] Precedent URLs **200 OK** on submit day.  
- [ ] **90s / 5 min / 3 attempts** timers — mark as **pilot tunable** in speaker notes.  
- [ ] **S5-4** microsite: only if PDF done and time remains.  
- [ ] Align exception copy with **legal** / **safety** review tone (especially drone).

---

## 11. Next module

**M5** — Unit economics (**S6-*`): `finance-deliverables.md` + `Paperclip extracted/finance.txt`.
