# Data storytelling layer — APM deck (companion to `FINAL_narrative_deck_source.md`)

**Skill basis:** `data-storytelling` — story structure, narrative arc, three pillars (data + narrative + visuals), progressive reveal, headline patterns, transitions, uncertainty language.

**Use this file to:** rehearse aloud, rewrite slide titles, and sequence **when** numbers appear so the deck **builds** instead of listing facts. **Canonical facts and tables** stay in `FINAL_narrative_deck_source.md`; this file adds the **dramaturgy**.

---

## 1. Macro story — Setup → Conflict → Resolution

| Act | What the reviewer feels | Your one-paragraph version |
|-----|-------------------------|----------------------------|
| **Setup** | “I know this company.” | Instacart wins on **getting groceries to the door**. The hardest, most variable piece is the **last mile** — the part that touches traffic, weather, labor rules, and customer emotion. |
| **Conflict** | “This is harder than the hype.” | Human fulfillment is **expensive** (~**$10.20**/order in our modeled baseline), **gig rules aren’t relaxing**, and **competitors are already pairing with robot and drone operators**. Waiting isn’t neutral — it **burns the partnership and learning window**. But **blanket autonomy** would break **trust, regulation, retail SLAs, and unit economics**. |
| **Resolution** | “There’s a disciplined bet.” | **Segment** missions (robots first, drones gated, humans retain hard cases). **Ship** a three-sided experience and **designed trust**. **Prove** economics need **utilization** (~**2.2** robot trips/day/unit to beat human). **Name risks and triggers**. **Pilot** at **GMU** for **90 days** — lead with **orchestration** proof (not hardware novelty), **partner ground already on campus**, **numeric GO/NO-GO** — only then widen the fence. |

**Elevator version (use in first 20 seconds):**  
“We’re last-mile constrained. Autonomy is **here in pockets**, not everywhere. My recommendation is **partner-first orchestration**, **segment-gated rollout**, and a **campus pilot** that proves **density and trust** before we bet the city.”

---

## 2. Narrative arc — hook through call to action

| Beat | Role | Scripted spine (adapt in your voice) |
|------|------|--------------------------------------|
| **1. Hook** | Earn attention with **tension + specificity** | “The last mile is where margin goes to die — and where **everyone** is experimenting. The question isn’t *if* robots show up in grocery; it’s whether **we** own **trust, routing, and retailer handoffs** — or become a thin layer on someone else’s fleet.” |
| **2. Context** | Baseline + stakes | Human last-mile sits in an **~$8–12** band in industry framing; our **hero model** anchors **$10.20**. Competitors are **scaling via partners**; **Scout** proved hardware without fit **dies**. |
| **3. Rising action** | Choices and tradeoffs (slides 3–6) | **Where** it fits (matrix + GMU). **Who** changes (customer, shopper, retailer). **How** trust is **built** (three patterns + mocks). **Whether** math works (**$1.50** robot @ **15**/day — **if** you fill the bot). |
| **4. Climax** | Highest-stakes insight | “The inflection isn’t the robot **price** — it’s **trips per day per unit**. Below **~2.2**, the robot **loses** to human on **this** model. So the pilot is really a **density and reliability** experiment dressed as a tech demo.” |
| **5. Resolution** | Concrete path | **Instacart’s stack** under volume first: **GMU**, **one geofence**, **one MFC**, **Starship** (existing campus modality) **+ phase-gated Wing**, **90-day** gates. |
| **6. Call to action** | What decision you want | “If we hit **450** completions, **80%** on-time, **NPS ≥25**, **cost ≤1.5×** human baseline, and **zero** serious injuries — **we widen**. If not — **we hold** and fix **one** lever at a time.” |

---

## 3. Problem–solution story (full skeleton)

Use this as a **spoken** outline; slides are illustrations.

```markdown
## The hook
"We can defend last-mile margin — but only if we learn in a fence, not in a city."

## The context
- Human modeled last-mile: **$10.20**/order (hero baseline)
- Robot @ utilization: **$1.50** @ **15** trips/day/unit — **$4.41** @ **5**
- Competitors: partner-led robot/drone scale; Scout retrenched

## The problem
- Not every basket or mile is AV-eligible
- Trust fails without mode clarity + honest ETAs + recovery
- Economics fail without density; regulation fails without dual-track permits

## The insight
Breakeven vs human: robot **~2.2** trips/day/unit, drone **~7.2** — 
so **campus ODD** is the right shape of proof — **orchestration + density**, not “first robot on dirt.”

## The solution
1. Segment-gated routing (robots first, drones gated)
2. Three-sided custody design (H1/H5/H7/H9/H11 on-slide)
3. Trust patterns + AI mocks (customer, picker, ops)
4. Six risks with explicit triggers
5. GMU pilot — lead with **Instacart stack** at volume; partner ground **already on campus**; 0/30/60/90 with numeric gates

## Expected impact (honest range)
- Learning: valid GO/NO-GO on **demand + ops + trust + unit cost**
- Scale: **only** after gates — production SLA targets **stricter** than pilot bar

## The ask (implicit for take-home)
"Treat this as a **gated portfolio bet**, not a moonshot."
```

---

## 4. Three pillars — how each slide earns its keep

| Slide | **Data pillar** (evidence) | **Narrative pillar** (meaning) | **Visual pillar** (clarity) |
|-------|----------------------------|--------------------------------|-----------------------------|
| Title | — | You will show a **full stack** PM story | One strong title + **three** chips (partner-first · three-sided · gated pilot) |
| Why now | $8–12 band, **$10.20** anchor, citations | **Window** + **risk of waiting** | Split **People \| Business**; optional thin evolution strip |
| Where it fits | Matrix GO/NO-GO, GMU name | **Discipline** beats “robots everywhere” | Color-coded R/D/H; **ODD ladder** campus-first |
| Experience | H-handoffs as “APIs” between actors | **Custody**, not magic | Swimlane or **before → after** one arrow |
| Trust + mocks | Exception timers (90s, 5 min, 3 tries — tunable) | **Designed states** beat adjectives | 2×2 mocks + **one** recovery state if space |
| Economics | **$10.20 / $1.50 / $4.98**, **5·15·25** table, **2.2 / 7.2** | Utilization is the **hero** | Waterfall or grouped bars; **breakeven** vertical line |
| Risks | Six rows + triggers | **Adult** PM; no hand-waving | Single table; optional liability **2×2** |
| Pilot + metrics | **450**, **80%**, **NPS 25**, **1.5×**, phase gates | **Orchestration proof** + **decision**, not activity | **Why campus / why here** → timeline **0–30–60–90** + **GO** diamond |

---

## 5. Executive headlines — swap weak titles for strong ones

Use **specific number + implication** where possible (skill formula).

| Slide | Weak | Strong |
|-------|------|--------|
| 2 | “Market analysis” | “**Last-mile runs ~$10/order** — and competitors aren’t waiting on us” |
| 3 | “Segments” | “**Robots first, drones gated** — humans keep the hard miles” |
| 4 | “User journeys” | “**Three sides, one custody chain** — store to bin to door” |
| 5 | “Trust” | “**When the bot stops, the product is the recovery screen**” |
| 6 | “Financial model” | “**$1.50 vs $10.20** @ 15 trips/day — **if** we fill the robot” |
| 7 | “Risks” | “**Six kill zones** — each with a trigger, not a vibe check” |
| 8 | “Pilot plan” | “**90 days — prove Instacart’s orchestration in one fence**” *(alt: “**GMU: 450** completions or we don’t widen”)* |

---

## 6. Progressive reveal — optional animation / build order

If you **click** through builds, stack **meaning** before **detail**:

1. **Economics slide:** (a) Human **$10.20** total bar only → (b) Add robot **$1.50** @ **15/day** → (c) Add **5** and **25** sensitivity footnote → (d) Reveal **~2.2 / ~7.2** breakeven callout.  
2. **Segmentation:** (a) One row “short + small = robot” → (b) Full matrix → (c) GMU pin.  
3. **Pilot:** (a) **Orchestration-first why** (campus · partner ops already there) → (b) Map/geofence → (c) Phases → (d) **GO** metrics panel.

---

## 7. Slide-by-slide — transitions + soundbites

Paste into speaker notes. Phrases adapted from the skill’s **transition** lists.

| From → To | **Transition in** | **Soundbite** |
|-----------|-------------------|---------------|
| Title → Why now | “This leads us to ask: **why should Instacart care in 2026?**” | “Autonomy is a **portfolio** question, not a gadget.” |
| Why now → Fit | “When we dig deeper, **where** should we even try?” | “**Operator envelopes**, not vibes.” |
| Fit → Experience | “Routing is cheap to write; **acceptance** is not.” | “Eligibility is code; **custody** is the product.” |
| Experience → Trust | “The pattern becomes clear when something **goes wrong**.” | “**Recovery** is the trust moment.” |
| Trust → Economics | “Trials need trust; **scale** needs utilization.” | “**Density** is the hidden variable.” |
| Economics → Risks | “The model is **conditional** — so what breaks the condition?” | “**Gates**, not hope.” |
| Risks → Pilot | “Based on this analysis, the honest next step is **bounded proof**.” | “**Orchestration under volume — one fence, one MFC, measured GO**.” |
| Pilot → Close | “The implication is clear: **we decide with numbers**.” | “**Widen or hold** — no middle.” |

---

## 8. Handling uncertainty (economics + forecast Q&A)

Use **ranges and assumptions** without sounding defensive:

- “With **labeled assumptions**, robot beats human in **this** model above **~2.2** trips/day/unit — sensitivity lives in **appendix**.”  
- “**$10.20** is our **hero** human baseline; GAAP last-mile **isn’t** one clean public line — finance reconciles.”  
- “J-curve crossover **~month 6** is **illustrative**; pilots that stall under **~10** trips/day/unit are the **execution** risk we’re measuring.”  
- “**80%** on-time is a **learning** bar; **production** should move toward **human-parity SLA** — I’d **tighten** before scale.”

---

## 9. Rule of three — memorable triads for the interview

Repeat these; they **stick**:

1. **Three modes:** Robot · Drone · Human (each owns different missions).  
2. **Three users:** Customer · Shopper · Retailer.  
3. **Three trust levers:** Mode clarity · Honest ETA · Recovery.  
4. **Three proof layers:** Can they **order**? Can we **deliver**? Can we **afford** to repeat?

---

## 10. Link to primary doc

- **Facts, tables, metric lock, mock specs:** `FINAL_narrative_deck_source.md`  
- **Module depth:** `M1`–`M8`, `99_appendix_verbal.md`

**Rebuild order:** Finalize **story layer** headlines + transitions → align **pptx** titles and build steps → keep appendix citations in footnotes, not on the **hook** slides.
