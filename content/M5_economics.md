# M5 — Per-order economics, OEM snapshot, breakeven, J-curve

**Scope:** Checklist **S6-1 — S6-6**.  
**Canonical source:** `Paperclip extracted/finance.txt` — **INS-6** slide-ready package (Apr 2026), **QA PASS** + **CEO approval** on thresholds.  
**Superseded:** `Paperclip generated/finance-deliverables.md` (older equations with **$10.52** human and **~7.13 / ~12.15** breakeven) — **do not mix** with INS-6; use INS-6 for one consistent story.  
**Aligns with:** **M1** ($8–12 band narrative), **M2** (robot-first, drone-second), **M7/M8** (pilot utilization realism).

---

## 1. Checklist coverage

| ID | Addressed |
|----|-----------|
| S6-1 | §3 human baseline stack + §2 POV |
| S6-2 | §3 robot column + §4 scenarios |
| S6-3 | §3 drone column + §4 scenarios |
| S6-4 | §5 OEM table |
| S6-5 | §6 breakeven + hero rounding rule |
| S6-6 | §7 J-curve + pilot realism |

---

## 2. PM headline (board-facing)

**Robot-first now, drone-second later.** Under the **labeled model** below, **sidewalk robot** all-in cost drops **below** the human baseline above **~2.2 deliveries/day/unit**; **aerial drone** crosses below human only above **~7.2 deliveries/day/unit** (given **stated** drone capex + oversight assumptions). **Lead with sidewalk density**; treat drone as **BVLOS- and landing-constrained** (**M2**).

**QA / CEO note (finance.txt):** Closed-form crossover is **~2.15 / ~7.17** — use **~2.2 / ~7.2** in **hero copy only**; keep precise values in **appendix** if needed (**one rounding rule** everywhere on-slide).

---

## 3. Per-order cost stack (USD/order @ **15 del/day/unit** for AV lines)

*Human total is independent of “u” in this presentation slice; robot/drone fixed costs are spread using **u**.*

| Line item | Human baseline | Sidewalk robot | Aerial drone | Source vs assumption |
|-----------|----------------|----------------|--------------|----------------------|
| Driver / remote ops labor | $6.32 | $1.00 | $1.40 | Human: minutes/order × wage — **BLS** Light Truck Drivers median **$23.51/hr** (May 2024, 53-3033) or **Payscale** delivery-driver band for gig framing. AV: **modeled oversight ratios** (not OEM per-order disclosures). |
| Fuel / energy / miles | $2.18 | $0.01 | $0.08 | Human: **IRS 2026** mileage **72.5¢/mi** × **~3 mi** trip churn/order (**assumption**). AV: modeled kWh × utility (**assumption**). |
| Platform overhead | $0.70 | $0.00 | $0.00 | Modeled **7%** on direct fulfillment — framing aligned with **McKinsey** online grocery fulfillment cost work. |
| Failed delivery / rework | $1.00 | $0.00 | $0.00 | Modeled fail-rate × rework; industry commentary (e.g. **DispatchTrack**-class failure cost context). AV rework **not zero** in production — **flag**; held $0 on base slide for clarity. |
| Hardware amortization | $0.00 | $0.24 | $1.68 | Robot: **$3,500/unit** scenario, 5-yr amortization spread over **u**; public bracket **MIT Technology Review** Starship **$5,500** / **$2,250** target (2018). Drone: **$25k** aircraft (**assumption**; public comps often higher). |
| Maintenance | $0.00 | $0.11 | $1.01 | **% of capex/year** ÷ (**u** × 365) — **assumption**. |
| Insurance | $0.00 | $0.10 | $0.61 | Annual policy per unit ÷ (**u** × 365) — **assumption**. |
| **Total** | **$10.20** | **$1.50** | **$4.98** | Human sits inside **$8–12** last-mile band from **case brief (INS-1)**. |

**Explicit assumption flags:** trip minutes, miles/order, fail-rate, **$3.5k** robot / **$25k** drone, maint %, insurance $, oversight staffing (**1:20** robots @ **$25/hr** × 8 hr; drone **1:20** @ **$35/hr** × 8 hr), kWh — **sensitivity dials**, not OEM facts.

---

## 4. Scenario table — utilization stress (S6-2, S6-3, S6-5)

| Deliveries/day/unit | Robot $/order | Drone $/order | Human $/order |
|--------------------:|--------------:|---------------:|---------------:|
| **5** (low) | $4.41 | $14.54 | $10.20 |
| **15** (mid — **primary chart anchor**) | $1.50 | $4.98 | $10.20 |
| **25** (high) | $0.92 | $3.07 | $10.20 |

**Deck layout (CEO):** Hero = **15/day** column; **5** and **25** as **compact band** (footnote, small table, or sensitivity strip).

**Breakeven vs $10.20 human:** Robot crosses below human at **~2.2/day/unit** (hero); Drone at **~7.2/day/unit** (hero). Appendix may cite **~2.15 / ~7.17** precise.

---

## 5. OEM / capability snapshot (S6-4)

| OEM | Unit cost (public) | Payload | Range / radius | Scale / throughput signal | Citations |
|-----|-------------------|---------|----------------|---------------------------|-----------|
| **Starship** | **$5,500** stated (2018); **$2,250** target — article | ~**20 lb** cargo (incl. Wikipedia recap) | Short sidewalk; **~2 mi** (FAQ); ~40 km/day typical travel cited | **2,700** robots, **9M+** deliveries (2025 press recap) | MIT Technology Review; Wikipedia — Starship; Starship FAQ |
| **Serve (SVRO)** | No stable retail “price per robot” | **Up to ~50 lb** (filings/materials) | **Under ~2.5 mi** typical; **20–30** del/day theoretical | **2,000+** robots / multi-city (verify current IR) | Serve SEC annual report PDF; NVIDIA case study; Serve IR |
| **Zipline P2** | Not disclosed | **~6–8 lb** (press) | **~10 mi** radius / **~24 mi** leg (press) | System throughput in ops press | CNBC P2; Business Wire |
| **Wing** | Not disclosed | **~2.5 lb** baseline; **~5 lb** larger box (2024) | **12 mi RT**; **~65 mph** cruise | **1,000+** pkg/day capability described; **750k+** residential deliveries (corporate) | Wing aircraft library blog; Wing delivery network overview |

**Third-party estimate (not OEM):** ~**$4,000**/robot in some analyst notes — label **“third-party estimate”** only (e.g. AInvest-style summaries).

---

## 6. J-curve + campus pilot (S6-6)

**Illustrative pilot (not GAAP):** One-time **$150,000** — **20** robots @ **$3,500** + **~$80k** program/dock/charging (**assumptions**).

**Utilization ramp (assumption):** **6 → 10 → 14 → 18** deliveries/day/unit over months (meal peaks + dense geofence — **GMU** narrative).

| Month | Utilization (del/day/unit) | Robot $/order | Monthly savings vs human on 20 robots | Cumulative cashflow |
|------:|---------------------------:|--------------:|--------------------------------------:|--------------------:|
| 0 | — | — | — | -$150,000 |
| 1 | 6 | $3.69 | $23,445 | -$126,555 |
| 3 | 6 | $3.69 | $23,445 | -$79,664 |
| 6 | 10 | $2.23 | $47,805 | **+$63,753** |
| 9 | 14 | $1.61 | $72,165 | +$280,249 |
| 12 | 14 | $1.61 | $72,165 | +$496,745 |
| 18 | 18 | $1.26 | $96,525 | +$1,075,898 |

**Readout:** Illustrative **crossover ~month 6** on this ramp. **Execution risk:** many geofenced pilots **stall under ~10/day/unit** without merchant density + hours — **M8** gates must track **real** utilization, not model optimism.

---

## 7. Key links (appendix / footnotes)

- BLS OEWS 53-3033 (median wage cross-check)  
- Payscale Delivery Driver hourly  
- IRS 2026 mileage (72.5¢)  
- McKinsey — profitable online grocery fulfillment  
- MIT Technology Review — Starship cost quotes  
- Starship FAQ; Wikipedia Starship recap (verify dates)  
- Serve SEC filings / IR; NVIDIA Serve  
- CNBC / Business Wire — Zipline P2  
- Wing aircraft + network posts  

*(Full URLs in `finance.txt` INS-6 comments.)*

---

## 8. Headline options

1. **“Utilization gates economics: robot-first, drone-second.”**  
2. **“~$10.20 human baseline vs ~$1.50 robot @ 15 trips/day — if you can fill the bot.”**  
3. **“The J-curve is real: month ~6 only if the campus hits 10+ deliveries/day/unit.”**

---

## 9. Visual spec (content-only)

- **Hero:** Stacked bar or waterfall — human vs robot vs drone **@ 15/day**.  
- **Second:** Line chart — $/order vs **u** for robot and drone crossing **$10.20**.  
- **Third (optional):** J-curve cumulative cashflow — **appendix** if crowded.  
- **Footnote block:** “Assumptions — not OEM-reported per-delivery costs.”

---

## 10. VERIFY before PDF

- [ ] **Single** breakeven pair on all slides: **~2.2 / ~7.2** (hero).  
- [ ] Remove any stray **$10.52** or **7.13 / 12.15** from old `finance-deliverables.md` paste.  
- [ ] **Pilot cost gate** in **M8** — if interview uses **$6.50** completed autonomous delivery, reconcile narrative (**per-order model** vs **pilot metric definition**) in speaker notes.  
- [ ] Spot-check **Wikipedia / press** figures against **primary** OEM pages on submit week.

---

## 11. Next module

**M6** — Risks & workforce (**S7-*`): `Paperclip extracted/Risk.txt` (+ strategy cross-refs).
