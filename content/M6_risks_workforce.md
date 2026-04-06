# M6 — Risks, regulation, workforce, liability

**Scope:** Checklist **S7-1 — S7-6**.  
**Sources:** `Paperclip extracted/Risk.txt` (Workstream E, INS-5 / INS-9; **QA PASS** on core blocks; **Apr 2026** refresh for regulatory timeline + Virginia/Fairfax clarity).  
**Pilot lock:** **GMU / Fairfax** — leverage **Virginia statewide PDD** statute + **Northern Virginia** local practice; **aerial** remains **waiver / Part 135 / future Part 108** path (**M2/M7**).  
**Upstream:** **M1** north star (dasher dependency) ↔ **M6** workforce honesty; **M4** trust UX; **M8** numeric gates should echo **trigger metrics** below where aligned.

---

## 1. Checklist coverage

| ID | Addressed |
|----|-----------|
| S7-1 | §3 regulatory bullets (FAA + local PDD) |
| S7-2 | §4 liability + safety row in §2 |
| S7-3 | §2 reliability row + §4 ops split |
| S7-4 | §2 trust row |
| S7-5 | §5 workforce narrative |
| S7-6 | §2 full **6 × 5** register |

---

## 2. Risk register — **6 rows** (slide-ready)

| Risk | Likelihood | Impact | Mitigation | Go/No-Go trigger (pilot SLOs — tune in M8) |
|------|------------|--------|------------|---------------------------------------------|
| **Regulatory delay** (FAA BVLOS / Part 108 + local PDD permits) | H | H | **Dual-track:** sidewalk/PDD permits now; **Part 135 + waivers** for aerial; staged geographies; regulator-ready safety dossier | No-go if **no** operable **local PDD** path **and** no viable **aerial** authority in agreed window; or **drone phase** blocked if **BVLOS** pathway unavailable by **day-90** expansion gate |
| **Safety incident** (contact / injury / property) | M | H | Conservative **ODD**, **geofence**, speed caps, **OEM safety case**, remote oversight, insurance floors, incident playbooks, **pause** authority | No-go on **severe** injury tied to system fault, or safety-critical rate **> agreed threshold** (e.g. **>1 / 10k** deliveries — calibrate) |
| **Service reliability** (late, failed handoff, weather, charging) | M | M–H | **Human fallback**, weather holds, redundant comms, maintenance SLAs, retail **joint ops** | No-go if autonomous **on-time completion <95%** for **2 consecutive weeks** or **completion failure >3%** any week |
| **Customer trust erosion** (nuisance, privacy, bad news) | M | M | **Mode clarity + ETA honesty + recovery** (**M4**), easy **human** opt-out, camera/audio policy, community comms | No-go if autonomous **NPS/CSAT trails human baseline by >10 pts** for **2** read cycles **or** sustained trust drop vs control |
| **Workforce displacement backlash** | M | H | **Named transition program** before scale (§5); priority paths to **tele-ops, field tech, exception handling**; transparent metrics; labor/comms engagement | No-go if **labor/city action** threatens permits **or** coordinated campaign hits **volume/brand** thresholds (define in M8) |
| **Retail partner friction** (handoff, shrink, SKU limits) | M | M | Co-designed **SOPs**, handoff zones, prep SLAs, escalation, **pilot** co-funding | No-go if **merchant opt-out >20%** in cohort **or** **prep-to-dispatch SLA misses >10%** |

**Deck density (QA):** **Full register on-slide**; **deep regulatory links** → **appendix**.

---

## 3. Regulatory summary — **tight bullets for slide**

- **BVLOS / “Part 108”:** NPRM *Normalizing UAS Beyond Visual Line of Sight Operations* published **Federal Register** (**Aug 7, 2025**; e.g. **2025-14992**). Comment period closed **Oct 6, 2025**; **reopening** published **Jan 28, 2026** with comments due **Feb 11, 2026** (**2026-01644**). **Not final law yet** — national routine BVLOS still largely **waivers / exemptions / Part 135** operational paths until final rule + compliance dates.  
- **Baseline today:** **Part 107** — **14 CFR §107.31** **VLOS** (or visual observer) unless waivered.  
- **Part 135 package delivery:** FAA **package delivery by drone** framework; **Wing** (2019 Part 135 milestone) and **Zipline** (2022 Part 135) as **mirror paths** — safety case, manuals, defined ODD, then **incremental** geographic expansion.  
- **Sidewalk / PDD — patchwork:** Examples only (not exhaustive): **San Francisco** ADD/PDW programs; **Washington, DC** DDOT PDD; **Los Angeles** LADOT PDD; **Virginia** statewide **Personal Delivery Devices** — **Va. Code § 46.2-908.1:1** (primary basis for **Fairfax County** robot ops; **no** separate Fairfax robot ordinance found in workstream — county **shared mobility** rules focus **scooters/bikes**). **Alexandria** publishes **local PDD** guidance — **Fairfax-adjacent** precedent for **GMU** narrative.

**VERIFY before submit:** Replace any secondary trade-press “H1 2026 final rule” guesses with **primary FR/FAA** status on your submission date.

---

## 4. Liability split — **control-based** (S7-2, S7-3)

| Domain | Primary party | Contract lever |
|--------|---------------|----------------|
| **Hardware/software defect** | OEM / autonomy provider | Product liability, indemnity, warranty |
| **On-route operations** (nav, incident response) | Fleet operator (often OEM partner) | SOPs, insurance minimums, reporting |
| **Marketplace** (dispatch, customer comms, **fallback policy**) | **Instacart** | T&Cs, SLA, remediation |
| **Store handoff / packing** | Retail partner | Merchant agreement, handoff protocol |
| **Third-party injury** | **Shared**, contract-allocated | Cross-indemnities, additional insured, claims governance |

**Serve ↔ Uber pattern (public):** Serve owns **robots + Safety Operators** and **regulatory compliance** for robot ops; Uber **platform**; **mutual indemnities** + commercially reasonable **insurance** (many $ details **redacted** in SEC exhibits) — use as **architecture precedent**, not copy-paste terms.

**Sources (Risk.txt):** FAA package delivery page; Serve–Uber SEC exhibits; Serve press.

---

## 5. Workforce — honest framing (S7-5, bridges **M1** S1-4)

**Tension (name it):** Margin and reliability pull toward **fewer gig-delivered trips** in AV-fit zones; **political and community license** require a **worker-forward** story, not “invisible displacement.”

**Commitments (pilot → scale):**

- **Published transition bundle:** priority hiring into **fleet technician, robot operator / remote assist, QA auditor** roles; **paid** credentials; optional **earnings bridge** in first markets.  
- **Measure hours shifted**, not zero displacement.  
- **Precedents (illustrative):** Waymo public posture on **human ops** roles and training partnerships (e.g. **Waymo blog** workforce development; **Fortune** coverage Mar 2026 cited in extract); **Amazon** upskilling / apprenticeship narratives (**About Amazon**).

**No-go alignment:** If **transition uptake** or **labor escalation** crosses thresholds in §2, **freeze** geographic expansion until remediated.

---

## 6. Headline options

1. **“Six risks, six triggers — autonomy only scales on gates.”**  
2. **“Regulation is dual-track: PDD now, BVLOS still in flight.”**  
3. **“Liability follows control — platform, operator, OEM, store.”**

**Cliffhanger:** “The pilot isn’t green if **partners** and **workers** aren’t bought in.” → **M7**.

---

## 7. Visual spec (content-only)

- **Primary:** **6-row register** (condensed fonts or appendix continuation).  
- **Inset:** **2×2 liability** or **swimlane** (Platform | Operator | OEM | Retail).  
- **Map (optional):** **VA** highlight + **“PDD: state code”** callout — not a legal opinion, **product review** framing.

---

## 8. Appendix — link bucket (verify live)

- FAA package delivery (Part 135): `https://www.faa.gov/uas/advanced_operations/package_delivery_drone`  
- Federal Register **2025-14992**; **2026-01644** (reopening)  
- 14 CFR §107.31 (Cornell LII)  
- Va. Code **46.2-908.1:1**  
- Alexandria PDD; DDOT PDD; SF Public Works / ADD (program URLs as in Risk.txt)  
- Serve–Uber SEC exhibit; Waymo workforce blog; About Amazon upskilling  

---

## 9. VERIFY / QA hygiene

- [ ] Merge any **duplicate** regulatory paragraphs from old vs new Risk.txt comments — **one canonical** slide block.  
- [ ] Remove **placeholder** characters or mojibake if pasting from PDFs.  
- [ ] **Align** §2 triggers with **M8** metrics (NPS delta, on-time %, opt-out %).  
- [ ] Legal review disclaimer: deck = **strategy**, not **legal advice**.

---

## 10. Next module

**M7** — Pilot design (**S8-1 — S8-6**): `Paperclip extracted/Pilot.txt` + **`00_checklist_map.md`** (GMU, Starship + phase-gated Wing).
