# Final narrative — Instacart APM take-home (deck source of truth)

**Purpose:** One file that tells a **single coherent story** from your module work (`M1`–`M8`, `99_appendix_verbal.md`). Use it to **rewrite or rebuild slides** so every slide answers a question the previous slide raised — not a stack of isolated factoids.

**Storytelling layer (headlines, arc, transitions, progressive reveal):** `FINAL_data_storytelling_layer.md` — applies the **`data-storytelling`** skill (`.agents/skills/data-storytelling`) on top of this doc.

**Audience:** Product leaders evaluating whether you think like an **APM**: hypothesis, tradeoffs, gates, stakeholders, and honest risk.

**How to use:** Read §0 aloud once. For each slide section, put the **headline + bullets** on the slide; put **bridge** and **if they push back** in speaker notes.

---

## 0. The story in 45 seconds

Grocery’s long-term leverage is **last-mile fulfillment**: it’s expensive on human rails, competitors are **learning with robots and drones**, and regulation is **moving** (not uniform, but not frozen). Instacart should **not** manufacture robots; it should **own** what it’s uniquely good at — **routing, retailer integration, trust UX, and exception policy** — and **partner** for hardware and regulated ops.

**Not every order should be autonomous.** Short, small-basket trips inside proven **operator envelopes** → **robots first**; light, urgent trips where airspace and landing work → **drones, phase-gated**; heavy shops, compliance-heavy SKUs, and bad conditions → **humans retain**.

That strategy only works if **customers, shoppers, and retailers** experience a designed **chain of custody** (not “surprise robot”). **Trust** is product: **mode clarity**, **honest ETAs**, **predictable recovery**. **Economics** are utilization-gated: robots beat modeled human **~$10.20**/order only above **~2.2** trips/day/unit; drones near **~7.2** — so the pilot must **prove density**.

**Risks are real** (regulation, safety, reliability, trust, workforce, partners); each has a **mitigation** and a **trigger**. **Proof** = stress-testing **Instacart orchestration** (retailer → picker → handoff → tracking → exceptions) under **real volume** in a **named campus geofence** — **George Mason University, Fairfax, VA** — **90 days**, **partner ground ops already normalized on campus**, **≤20%** aerial in limited beta, **numeric GO/NO-GO** at day 90.

**Metric lock (one hero set everywhere on-slide):** see §9.

---

## 1. Story spine — question chain

| After this slide… | The reviewer should ask… | Next slide answers… |
|-------------------|--------------------------|----------------------|
| Title | “Why should I care?” | **Why now** — cost, regulation, competition, window. |
| Why now | “Where would we even use this?” | **Segmentation** — matrix + ODD + robots-first. |
| Segmentation | “What actually changes for users?” | **Experience** — customer, shopper, retailer + handoffs. |
| Experience | “How do we earn trust?” | **Trust + mocks** — three patterns + evidence in UI. |
| Trust | “Does the math work?” | **Economics** — stacks, breakeven, J-curve honesty. |
| Economics | “What could kill us?” | **Risks** — six rows + workforce honesty. |
| Risks | “How would you prove it?” | **Pilot** — orchestration-first **why**, then GMU, stack, MVP, 0–30–60–90. |
| Pilot | “How do we decide?” | **Metrics** — learning questions + day-90 GO. |

If a slide doesn’t **advance this chain**, cut it or merge it.

---

## 2. Slide 1 — Title (concept deck)

**Headline:** Autonomous last-mile delivery — strategy & gated campus pilot  

**Subhead:** Partner-first autonomy · Grocery orchestration & trust · Proof at George Mason University  

**Speaker note (one line):** “I’m going to show **where** autonomy fits, **what** we ship for three sides of the marketplace, **how** we design trust, **whether** the math can work, **what** kills us, and **how** we’d prove it in 90 days with clear GO/NO-GO metrics.”

---

## 3. Slide 2 — Why invest now (M1)

**Bridge from title:** “The open question isn’t novelty — it’s whether Instacart should **earn the right** to remove the human last-mile leg in **fit zones**. That starts with **why the window is 2026**, not someday.”

**The point in one line:** Last-mile is **structurally expensive** and **competitively active**; waiting cedes **learning and partnerships** — but scale belongs behind **trust, regulation, and economics gates**.

### On-slide layout (recommended)

**Left — People (why it can be wanted)**  
- Async, low-contact delivery is **normal**; autonomy extends that to “**predictable machine handoff**” for people who want **fewer stranger-at-door** moments (campus, late night, pet/safety edges — pick **one** persona icon).  
- **Trust is product-shaped** — mode clarity, honest ETAs, recovery when the machine stops (paid off on slide 5).

**Right — Business (why Instacart should fund learning now)**  
- Human last-mile modeled **~$8–12**/order band (finance owns GAAP reconciliation; **hero baseline $10.20** on economics slide).  
- **Gig / classification pressure** stays live (e.g. USDOL IC rule **FR 2024-00067**, eff. Mar 2024).  
- **Ground + air autonomy scaling via partners** (e.g. Serve–Uber robot scale; Starship delivery counts; Wing consumer envelope; FAA BVLOS progress — **cite appendix**, don’t clutter slide).  
- **Cautionary precedent:** hardware without durable fit gets cut (e.g. **Amazon Scout** wind-down) → **partner-first**, not **build-your-own robot** by default.

**North star (one careful line):** Long-term, remove **variable-cost human last-mile** in **fit zones** — **not** “fire shoppers”: picking, exceptions, and fleet ops stay **human-heavy**; gig last-mile **shrinks where AV-eligible** (workforce slide).

**Optional one-line evolution:** “Grocery keeps removing friction from store to home — autonomy is the next step **where ODD and economics allow**.”

**If they push back — “Why not wait?”** Competitors are **shipping volume**; gig **repricing** doesn’t remove the structural cost problem; controlled ODD lets us **learn** before citywide bets.

---

## 4. Slide 3 — Where autonomy fits (M2)

**Bridge:** “So we invest — but **one mode doesn’t win every mission**. Next is **routing logic**: distance × basket × urgency, grounded in **real operator envelopes**.”

**The point in one line:** **Robots first** for short hub-and-spoke grocery; **drones gated** after ground control charts are stable; **humans retain** hard cases.

### Segment matrix (deck-ready)

Use **GO / conditional / NO-GO** — not vibes. Keep **one footnote**: Wing-class aerial = **~2.5 lb**, **~12 mi RT** (don’t silently shrink to “6 mi” without a reason).

| Distance / profile | Basket | Robot | Drone | Human |
|--------------------|--------|-------|-------|-------|
| **0–2 mi**, small–medium | Snacks, few bags | **GO** | Conditional (corridor + landing) | Backup |
| **Light, urgent**, air-viable | Small | NO-GO | **GO** if corridor | Default |
| **Heavy / large** | Weekly shop | Conditional / NO-GO | NO-GO | **GO** |
| **Long urban leg** | Medium–large | NO-GO | NO-GO (today) | **GO** |

### Controlled ODD first

- **Campus / micro-geofence** before open suburbs: **density**, repeated trips, simpler traffic, cleaner measurement — **Bird/Lime** campus density analogy.  
- **Named pilot:** **George Mason University, Fairfax, VA** (bounded geofence; sidewalk volume day one).  
- **Phase 2** (verbal only on this slide): hospitals, towers, events — **not** MVP success criteria.

### Build / buy / partner (one strip)

- **Partner:** regulated hardware / OEM fleets (Starship, Wing, etc.).  
- **Own:** dispatch, **eligibility**, **trust UX**, retailer integration, **exception** and fallback policy.  
- **Avoid:** Scout-style **hardware-first** bet without proven grocery-campus fit.

**If they push back — “Why robots before drones?”** Lower **regulatory surface** and **lower breakeven utilization** on the ground (**economics slide**); aerial stays **≤20%** in limited beta (**pilot slide**).

---

## 5. Slide 4 — Experience: three users, one system (M3)

**Bridge:** “Routing decides *eligibility*. Experience decides whether anyone *accepts* the handoff. Autonomy changes **three** journeys at once.”

**The point in one line:** Move from **handoff-to-driver** to **custody-to-machine** with explicit **retailer** rules — or adoption and SLAs break.

### Future-state story (seven stages — collapse to 5 rows on-slide if needed)

| Stage | Customer | Shopper | Retail |
|-------|----------|---------|--------|
| **Setup** | Sees **eligible** autonomous slot; **mode + ETA range** before pay | — | Publishes **eligibility** by zone/SKU/time |
| **Accepted** | “Picker + vehicle reserved” | Pick + **dock lane** (no driving) | Confirms **staging** capacity |
| **Pick** | Async subs | Pick to **AV packaging** spec | Tamper-evident materials |
| **Load** | “Vehicle loading” + lock ETA | Load pod → **scan seal** | Verify seal → **release dock** |
| **Transit** | **Mode chip** + map + **ETA band** | Exception monitor | Lane health (ops/partner) |
| **Arrival** | Countdown + **PIN / unlock** | Remote assist if needed | Retrieve / relaunch if fail |
| **Post** | Proof + feedback | Reverse logistics if return | Custody logs + incident $ |

**Handoffs to label on-slide (pick 3–4):** **H1** eligibility → UI · **H5** packaging gate · **H7** marshal → robot · **H9** machine → customer · **H11** incident → recovery.

### Honest tradeoffs (one line each — footnote or verbal)

- Not always **fastest vs car** — sell **reliability + cost + availability** in zone.  
- Weather / terrain **degrade** robot SLA → **fallback** volume required.  
- Alcohol / restricted SKUs → often **human** in v1.  
- Dock + marshal time = **real retailer cost** — **co-designed** SOPs.

**If they push back — “You forgot stores.”** Retail is the **third user**: dock real estate, packaging, shrink, **incident economics**.

---

## 6. Slide 5 — Trust & AI mocks (M4)

**Bridge:** “When the robot stops, **the product is the exception UX**. Trust isn’t marketing — it’s **designed states**.”

**The point in one line:** Three interventions — **mode clarity**, **ETA honesty**, **recovery** — and mocks must show **customer, picker, and ops** (not one glossy app screen).

### Three trust patterns (ship + precedent — footnote URLs)

1. **Mode clarity (Waymo-style)** — Persistent **Human / Robot / Drone** chip + plain language (“Autonomous sidewalk robot · Monitored by remote support”).  
2. **ETA confidence (Lyft/Uber-style)** — **Range** + **confidence**; band **widens** on dock queue, weather, corridor — **false precision** erodes trust faster than a wide band.  
3. **Recovery (Amazon-style)** — One card: **what happened** → **what we’re doing** → **by when** → **one primary CTA** (wait / human fallback / reschedule).

### Exceptions (name three — detail in speaker notes)

- **Robot stuck** — notify customer + ops; recover or **human fallback** within bounded time.  
- **Drone link loss** — **safety-first** messaging; ground relay.  
- **Not home / no unlock** — grace timer → options → return/restage policy.

### Mock tiers (what to generate with AI)

| Mock | Shows |
|------|--------|
| **A — Checkout** | Eligibility + **mode choice** + price/time tradeoff + trust line. |
| **B — Tracking** | Mode chip, map, **ETA range + confidence**. |
| **C — Dock handoff** | Scan seal, load to robot, mistake prevention. |
| **D — Fleet / ops** | Active units, p95 time, exceptions, **cost placeholder**, geofence health — proves **platform** thinking. |

**Footer:** “Concept UI · AI-generated — not affiliated with Instacart branding unless permitted.”

**If they push back — “Mocks are fluff.”** Each mock maps to **S4-5** patterns and **S4-4** exceptions — it’s **evidence of product judgment**, not decoration.

---

## 7. Slide 6 — Unit economics (M5)

**Bridge:** “Trust gets you trials; **utilization** decides whether autonomy is a business or a hobby.”

**The point in one line:** At **15 deliveries/day/unit**, modeled **robot** stack **~$1.50**/order vs human **~$10.20**; **drone ~$4.98** — but **breakeven** vs human is **~2.2** (robot) and **~7.2** (drone) trips/day/unit **under stated assumptions**.

### Hero table (@ 15 del/day/unit)

| Line | Human | Robot | Drone |
|------|------:|------:|------:|
| Labor / oversight | $6.32 | $1.00 | $1.40 |
| Fuel / energy | $2.18 | $0.01 | $0.08 |
| Platform overhead | $0.70 | $0.00 | $0.00 |
| Failed / rework | $1.00 | $0.00 | $0.00 |
| Hardware amortization | $0.00 | $0.24 | $1.68 |
| Maintenance | $0.00 | $0.11 | $1.01 |
| Insurance | $0.00 | $0.10 | $0.61 |
| **Total** | **$10.20** | **$1.50** | **$4.98** |

**Footnote (required):** Labeled model — trip minutes, miles/order, capex (**$3.5k** robot / **$25k** drone scenario), maint %, insurance, oversight ratios — **sensitivity in appendix**, not OEM-reported per-delivery costs.

### Utilization sensitivity (one mini table or chart)

| del/day/unit | Robot $/order | Drone $/order | Human |
|-------------:|--------------:|--------------:|------:|
| 5 | $4.41 | $14.54 | $10.20 |
| **15** | **$1.50** | **$4.98** | $10.20 |
| 25 | $0.92 | $3.07 | $10.20 |

**J-curve (verbal discipline):** Illustrative pilot crossover ~**month 6** **if** ramp hits **10+** del/day/unit sustained — many pilots **stall below** that → **M8** tracks real utilization.

**Do not mix** deprecated **$10.52** human line or old breakeven pair from legacy finance deliverables.

**If they push back — “Numbers are made up.”** Every number is an **assumption with a dial**; OEM **public** facts live in the **OEM snapshot** (appendix); the PM move is **sensitivity**, not false precision.

---

## 8. Slide 7 — Risks, regulation, workforce (M6)

**Bridge:** “Economics only matter if we **survive** regulation, incidents, reliability, trust, labor politics, and retailer patience.”

**The point in one line:** Six risks, each with **mitigation** and **GO/NO-GO trigger** — autonomy scales on **gates**, not hope.

### Six-row register (slide-ready)

| Risk | Mitigation | Trigger (tune with Ops) |
|------|------------|-------------------------|
| **Regulatory delay** (FAA paths + local PDD) | Dual-track: **sidewalk/PDD now**; waivers / Part 135 / future Part 108 for air | No operable path in agreed window → **no-go** |
| **Safety incident** | Conservative ODD, geofence, speed caps, OEM case, insurance, pause authority | Severe injury tied to system fault or rate **> threshold** → **no-go** |
| **Service reliability** | Human fallback, weather holds, retail joint ops | e.g. autonomous **on-time <95%** **2 weeks** or **failure >3%** any week → **no-go** *(pilot learning bar may be **80%** — say aloud: learning vs production)* |
| **Trust erosion** | M4 patterns, human opt-out, community comms | NPS/CSAT **trails human by >10 pts** 2 cycles → **no-go** |
| **Workforce backlash** | **Named transition** program; tele-ops, field tech, exception roles; transparent metrics | Labor/city action threatens permits or brand threshold → **freeze** |
| **Retail friction** | Co-designed SOPs, handoff zones, pilot co-funding | **>20%** merchant opt-out or **prep SLA** misses → **no-go** |

### Regulation (tight — appendix for links)

- **BVLOS / Part 108:** NPRM and comment/reopen timelines — **not final** on all dates; treat as **planning**, not “done.”  
- **Today:** Part 107 **VLOS** baseline unless waivered; **Part 135** package paths for mature operators.  
- **Sidewalk / PDD:** **Virginia** statewide PDD (**Va. Code § 46.2-908.1:1**) supports **Fairfax/GMU** narrative; local practice still matters — **product review**, not legal advice.

### Workforce (name the tension)

Margin pulls toward **fewer gig last-mile trips** in AV-eligible zones; **social license** requires **visible** transition paths (**fleet tech, remote assist, QA**) — measure **hours shifted**, not pretend zero displacement.

### Liability (2×2 or four lines)

**Control-based split:** OEM (defect), operator (on-route), **Instacart** (marketplace dispatch + fallback policy), retailer (handoff/pack). **Serve–Uber** exhibits = **architecture precedent**, not copy-paste contract.

**If they push back — “You’ll get sued.”** Liability **follows control**; contracts allocate **indemnity, insurance, reporting** — same as marketplace logistics today, with **new parties**.

---

## 9. Slide 8 — Pilot: GMU, 90 days, GO/NO-GO (M7 + M8)

**Bridge:** “We’ve set strategy, experience, trust, economics, and risks — here’s the **minimum proof** that de-risks Phase 2.”

### Lead — orchestration-first (on-slide, above the fold)

**What we’re proving:** Not “does a robot roll?” — whether **Instacart’s layer** holds at volume: **routing + retailer/MFC integration + picker→vehicle handoff + live status + exception policy + human fallback** with partner-operated ground (and gated air).

**Why a campus ODD:** **Meal and class peaks** → fast repetition on dispatch, concurrency, and recovery; a **tight geofence** → **cleaner attribution** (stack bugs vs open-city noise). Goal is **learning rate** on orchestration — not full demographic coverage of every US grocery mission on day one.

**Why existing partner ground on campus helps:** **Starship-class ops** already there → **real integrations** (APIs, dock timing, runbooks), not a slideware handoff. Convenience/food trips and **grocery** can be **additive** (different SKUs, basket shape, Instacart ingress). **VERIFY:** **capacity** allocation and **contract** path so Instacart-shaped volume isn’t blocked or starved.

**The point in one line:** One **geofence**, one **MFC**, **two modalities** with **aerial capped**; **90-day** phase gates; **day-90 GO** only if **all** metrics pass — framed as **orchestration + density** proof, not hardware novelty.

**Headline option:** **90 days — prove Instacart’s orchestration inside one fence** · sub: **GMU · Starship ground + gated Wing · numeric GO**

### Hypothesis (one sentence)

We believe **campus-eligible** users will complete a high share of **robot-eligible** orders via autonomous ground (and gated air), hitting **volume, on-time, satisfaction, and cost** thresholds — proving **demand + ops** in a **controlled ODD** before widening.

### Where & stack

- **Site:** GMU main campus core — residential + dining + retail adjacency; **partner sidewalk delivery already normalized** — pilot adds **grocery orchestration** on top of the modality.  
- **Ground:** **Starship** (campus playbook).  
- **Air (gated):** **Wing** (VA precedent story).  
- **Validation:** NVIDIA Isaac / sim for ODD widenings.  
- **Orchestration:** ROS2-class layer + vendor APIs + Instacart **order router + partner adapter**.

### MVP in / out

**In:** Geofence + SKU rules; customer tracking + **PIN**; single MFC staging; exception queue + remote assist; analytics; human fallback.  
**Out:** Citywide scale, full catalog autonomy, multi-retailer v1, custom perception stack.

### Phases & gates

| Phase | Window | Gate |
|-------|--------|------|
| Setup | 0–30 | **≥10** dry runs, **≥90%** without manual rescue |
| Limited beta | 30–60 | **≤500** users; robots primary; **drones ≤20%** of trips · **≥100** paid · **on-time ≥75%** · **contact ≤15%** |
| Scale-in-fence | 60–90 | **≥450** cumulative completed · **on-time ≥80%** · **0** serious/reportable injuries |

### Day-90 GO (all must be true) — **metric lock**

| Metric | Hero threshold |
|--------|----------------|
| Completed autonomous orders | **≥ 450** |
| On-time (vs promised window) | **≥ 80%** |
| NPS | **≥ 25** ( **n ≥ 80** ) |
| Serious safety events | **0** |
| Pilot unit economics (vs M5 human baseline) | **≤ 1.5×** **$10.20** → ceiling **~$15.30** fully loaded pilot accounting |

**Speaker note — reconcile 80% vs 95%:** Pilot **learns** at **80%**; **production** target aligns with risk register **95%+** — you don’t scale the fence until the **control chart** earns it.

**Do not** put **≤$6.50** and **1.5×** on the same slide without a **definition line** — pick **one** hero cost headline (this doc recommends **1.5×** with M5 baseline).

### Learning questions (optional second row on dashboard)

- Handoff acceptance / **contact ≤15%**  
- Blended **$/completed** vs baseline  
- Robot **rescue ≤12%** of robot trips; drone **abort ≤8%** of drone trips  
- Peak zone **≥8 orders/hour** on **≥3** days/week  

---

## 10. Closing signal for interview (S10 — verbal, not a ninth dense slide)

If you get **“What would you do in week one?”**:

- Co-own **metric definitions** with Ops + partners (on-time, serious injury, completed).  
- Shadow **3** picker shifts + **2** exception reviews — file **eligibility decision log**.  
- **5** interviews (students, store lead, shopper) on **handoff fear** and **trust copy** before geofence v2.  
- Weekly pilot review: **one owner per KPI**; no Phase 2 narrative without **gate** linkage.  
- Single **RACI** for MOU, MFC retailer, Starship/Wing POCs.

---

## 11. Pre-submit content checks (from `99_appendix_verbal.md`)

- [ ] **Metric lock** consistent across pilot + risk triggers (explain **learning vs production** aloud).  
- [ ] No stray **UCSB** pilot, **$10.52**, or conflicting **$6.50** without definition.  
- [ ] **Part 108 / BVLOS** wording matches **FAA / FR status on submit date**.  
- [ ] **Citations** spot-check (Waymo, FAA, Serve SEC, Starship FAQ, Wing).  
- [ ] Mocks labeled **concept / AI-generated** if required.

---

## 12. Source map (for your own edits)

| This narrative section | Primary module |
|------------------------|----------------|
| §3 | `M1_why_now.md` |
| §4 | `M2_segmentation.md` |
| §5 | `M3_experience.md` |
| §6 | `M4_trust_mocks.md` |
| §7 | `M5_economics.md` |
| §8 | `M6_risks_workforce.md` |
| §9 | `M7_pilot.md` + `M8_metrics.md` |
| §9 metric table | `99_appendix_verbal.md` §1 |
| §10–11 | `99_appendix_verbal.md` |

---

*Distill principle applied: one spine, one metric lock, no duplicate tables without purpose. Clarify principle applied: each slide states **who cares** and **what decision** it supports before tactics.*
