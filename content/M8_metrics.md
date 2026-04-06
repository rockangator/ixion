# M8 — Learning goals, metrics, go/no-go

**Scope:** Checklist **S8-7**, **S8-8**, **S9-1 — S9-6**.  
**Sources:** `Paperclip extracted/Pilot.txt` (Apr 2, 2026 ASCII blocks + **Mar 26** `$6.50` correction); **`M5_economics.md`** (human baseline **$10.20**); **`M6_risks_workforce.md`** (SLA triggers).  
**Upstream:** **`M7_pilot.md`** phases and hypothesis.

---

## 1. Checklist coverage

| ID | Addressed |
|----|-----------|
| S8-7 | §3 learning questions |
| S8-8 | §2 day-90 + §4 crosswalk |
| S9-1 | §2 cost gates + Q economics |
| S9-2 | §2 on-time + Q on-time |
| S9-3 | §5 handoff / completion proxy |
| S9-4 | §2 NPS + Q satisfaction |
| S9-5 | §3 exception / rescue rates |
| S9-6 | §3 density + repeat (implicit); add **30-day repeat** if desired |

---

## 2. Day-90 go / no-go (primary — Apr 2 package)

**GO** if **all** true:

| Metric | Threshold | Notes |
|--------|-----------|--------|
| **Cumulative completed orders** | **≥ 450** | Autonomous completions in geofence |
| **On-time %** | **≥ 80%** | OTA vs **promised window** (define “on-time” in pilot SOP) |
| **NPS** | **≥ 25** | Pilot survey **n ≥ 80** |
| **Serious safety events** | **0** | Define “serious” with legal/Ops (align **M6** safety row) |

**NO-GO:** Any miss → **hold** geography expansion; **30-day** root-cause containment (**M7**).

### Phase gates (recap)

| Gate | Threshold |
|------|-----------|
| **Dry run (0–30)** | **≥10** orders, **≥90%** success without manual rescue |
| **Limited beta (30–60)** | **≥100** paid orders; **on-time ≥75%**; **contact ≤15%** |
| **Scale (60–90)** | **≥450** cumulative; **on-time ≥80%**; **0** reportable injuries |

---

## 3. Learning questions — hypothesis → measure → bar (S8-7)

| Question | Measurement | Success threshold |
|----------|-------------|-------------------|
| **Handoff acceptance** | Post-delivery survey + **contact rate** | **≥70%** satisfied/very satisfied; **contact ≤15%** |
| **On-time under multi-modal routing** | OTA vs promised time | **≥80%** on-time by day 90 |
| **Blended unit economics at pilot utilization** | Vendor invoices + staging labor → **$/completed delivery** | **≤ 1.5×** human **baseline $/order** (**M5**: **$10.20** anchor → ceiling **~$15.30** for this framing) |
| **Ground vs aerial reliability** | Exception codes | **Robot rescue ≤12%** of robot trips; **drone abort ≤8%** of drone trips |
| **Density / efficiency** | Orders/hour by zone, peak days | A zone with **≥8 orders/hour** peak on **≥3 days/week** |

**Optional add (Mar 26 thread, QA-corrected):** **Cost per completed autonomous delivery ≤ $6.50** *and* **≥20% lower than matched human lane** — **different accounting** than “1.5× baseline”; **pick one primary cost headline** for slides to avoid contradictions (**§4**).

---

## 4. Crosswalk — reconcile pilot.txt variants vs M5/M6

| Topic | Mar 26 package (stricter) | Apr 2 package (on slide now) | Recommendation |
|-------|---------------------------|--------------------------------|----------------|
| **Day-90 on-time** | **≥95%**, completion **≥97%** | **≥80%** | **Hero for deck:** keep **Apr 2** as **pilot learning** bar; add **footnote** “**Production target 95%+** aligned with risk register” (**M6**) or **tighten** pilot hero to **≥90%** if you want one number. |
| **Order mix** | Autonomous **≥20%** of eligible | **70%** of **robot-eligible** completed autonomously | **Different denominators** — define on-slide: **“% of eligible orders that complete via AV.”** |
| **Cost** | **≤$6.50** / completed + vs control | **≤1.5×** human **$10.20** | **≤$6.50** is **absolute** pilot metric; **1.5×** is **ratio**. **Choose one** hero, put the other in **appendix** or **speaker notes**. |
| **NPS** | **+8** vs control | **≥25** absolute | Use **≥25** with **n≥80** (Apr 2) **or** **+8** vs control (Mar 26) — **not both** without two charts. |
| **Shadow missions** | **≥50**, **<2** incidents/100, **p95** intervention **<120s** | Replaced by **10-order** dry run | **Keep** dry run for slide brevity; **optional appendix** shadow ops for ops-heavy reviewers. |

**PM call for final PDF:** One **“metrics dashboard”** figure with **single** set of **day-90** numbers; **second line** for **stretch** or **production** alignment.

---

## 5. Case rubric mapping (S9 quick index)

| Case / checklist | Primary metric in this pilot |
|------------------|----------------------------|
| **Per-order cost** | **S9-1** — blended **$/completed** vs **M5** human baseline; **§3** Q3 |
| **On-time vs SLA** | **S9-2** — phase + day-90 **on-time %** |
| **Handoff / acceptance** | **S9-3** — contact rate, completion, unlock success |
| **NPS / CSAT** | **S9-4** — pilot NPS + satisfaction |
| **Intervention / fallback** | **S9-5** — rescue %, abort %, remote assist volume |
| **Repeat use** | **S9-6** — add **30-day repeat** for autonomous mode if not already in hypothesis (Mar 26 had **≥25%** repeat — optional bullet) |

---

## 6. Headline options

1. **“450 completions, 80% on-time, NPS ≥25 — then we widen the fence.”**  
2. **“Five learning questions; every metric ties to a ship/kill decision.”**  
3. **“Economics ceiling + reliability floor — no Phase 2 without both.”**

---

## 7. Visual spec (content-only)

- **Single dashboard mock:** KPI tiles (orders, on-time, NPS, $/delivery, exceptions, safety).  
- **Timeline:** 0–30–60–90 with **GO/NO-GO** diamonds.  
- **Footnote strip:** Assumption definitions (on-time, completed, serious injury).

---

## 8. VERIFY

- [ ] **Pick** cost headline: **$6.50** vs **1.5×** vs **M5 model** — align with **finance**.  
- [ ] **Harmonize** **80%** vs **95%** on-time with **M6** service-reliability trigger.  
- [ ] **Survey n ≥ 80** feasible for **90-day** campus pilot.  
- [ ] Legal sign-off on **“reportable injury”** / **serious** definitions.

---

## 9. Content modules — status

| Module | File |
|--------|------|
| M1 | `M1_why_now.md` |
| M2 | `M2_segmentation.md` |
| M3 | `M3_experience.md` |
| M4 | `M4_trust_mocks.md` |
| M5 | `M5_economics.md` |
| M6 | `M6_risks_workforce.md` |
| M7 | `M7_pilot.md` |
| M8 | `M8_metrics.md` (this file) |

**Remaining (not slide build):** **S10** hiring close + **S11** appendix — optional **`content/99_appendix_verbal.md`** when you want.
