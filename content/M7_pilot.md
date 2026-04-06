# M7 — Pilot design (where, how, MVP, stack)

**Scope:** Checklist **S8-1 — S8-6**. Learning questions **S8-7** → see `**M8_metrics.md`**.  
**Canonical pilot story:** `**00_checklist_map.md`** — **GMU / Fairfax**; **sidewalk primary**; **aerial ≤20%** of trips in limited-beta phase until gates pass.  
**Sources:** `Paperclip extracted/Pilot.txt` — **Apr 2, 2026** ASCII-safe blocks (`0ff0c8dd` + citations comment) + earlier **Mar 26** structure (where aligned).  
**Conflict note:** `Pilot.txt` also contains **UCSB** variant — **do not use** for this deck; **GMU only**.

---

## 1. Checklist coverage


| ID   | Addressed                      |
| ---- | ------------------------------ |
| S8-1 | §2 hypothesis                  |
| S8-2 | §3 location + geofence         |
| S8-3 | §4 vendors + stack             |
| S8-4 | §3 merchant/MFC + §4 scope     |
| S8-5 | §5 phases 0–30 / 30–60 / 60–90 |
| S8-6 | §4 MVP in/out                  |


---

## 2. Pilot hypothesis (S8-1)

**Single sentence (deck):**  
We believe **campus-eligible** grocery users (students/staff) will complete **≥70%** of **robot-eligible** orders via **autonomous ground or aerial** delivery, with **on-time** arrival within the **promised window**, at **≥450** **completed** pilot deliveries over **90 days** — validating **unit-level demand** and **operational feasibility** in a **controlled ODD** (Waymo-style readiness gating) and unlocking **Phase 2**: **adjacent housing + second retail node** under an **expanded geofence**.

*(Verbal backup: “Robot-eligible” = basket/SKU/zone rules in **M2**; not 100% of all Instacart orders.)*

---

## 3. Where — named site + ODD (S8-2, S8-4)

**Primary:** **George Mason University (GMU), Fairfax, VA** — **main campus core**: residential + dining + **Johnson Center** retail adjacency.


| Criterion                  | Rationale                                                                                                                                                                            |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Density + peaks**        | Classes + dining → repeatable demand (**Lime/UNC**, **Bird/UCSB** campus-first logic — without switching site to UCSB).                                                              |
| **ODD discipline**         | Geofence **minimizes** unsignalized **road crossings**; **sidewalk**-heavy; **aerial** uses **site-controlled** landing/loading where possible (**Waymo Phoenix**-style narrow ODD). |
| **Infrastructure**         | Mature paths; **Starship** university playbook (**GMU** cited as early US university deployment in vendor narrative — **VERIFY** current press page).                                |
| **Permits**                | **Campus-first** counterpart: **MOU** with institution, **risk**, **campus police/safety** — Fairfax County engagement **incremental**, not day-one blocker for **on-campus** ODD.   |
| **Merchant cohort (S8-4)** | **One anchor retailer** + **single MFC / staging lane** for measurement clarity (avoid multi-retailer confounds in v1).                                                              |


**Alternatives (subtext only):** hospitals, corporate parks, entertainment districts → **Phase 2** ODDs (**M2**).

---

## 4. Vendors & stack — partner, don’t build (S8-3)


| Layer                      | Choice                                                           | Rationale                                                                                                                                                                          |
| -------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sidewalk robots**        | **Starship Technologies**                                        | **25+** university deployments; **GMU** in vendor milestone narrative; dispatch, charging, campus UX **off-the-shelf**.                                                            |
| **Aerial (phase-gated)**   | **Wing**                                                         | **Christiansburg, VA** commercial precedent; **Queensland** ops for international maturity signal; complements robots for **longer / non-walkable** legs inside approved airspace. |
| **Autonomy validation**    | **NVIDIA Isaac** (Sim / digital twin)                            | Validate widenings **before** ODD expansion without owning full AV stack.                                                                                                          |
| **Fleet orchestration**    | **ROS 2**-based layer + **vendor APIs**                          | Mission assign, health, **intervention queue**, **incident** hooks; **multi-vendor** without rewriting core autonomy.                                                              |
| **Enterprise integration** | **Instacart** order router + **partner adapter** + **event bus** | ETA, handoff, exception state (**M3/M4** H-points).                                                                                                                                |


**Alternate considered:** **Serve + Uber Eats** — strong **urban food**; for **grocery + campus density**, Starship **closer analog** to campus beachhead (**Pilot.txt**).

**Citations to carry (appendix):** Starship–GMU milestone; Wing Christiansburg; Wing Queensland; Isaac Sim overview; Waymo safety/ODD materials (high-level).

---

## 5. MVP — in scope / out of scope (S8-6)

### In scope (need-to-have)

- **Geofenced** eligibility + routing inside **campus ODD** + **SKU** rules (**M2** alcohol/temp).  
- **Customer:** place order, **live status**, **handoff PIN** / retrieval confirmation (**M4** mocks).  
- **Single MFC staging lane** + **mission assignment** (picker → dock → vehicle).  
- **Exception queue** + **remote assist** / **e-stop** per vendor; **incident logging**.  
- **Analytics:** on-time %, completion, **contact rate**, **NPS** sample.  
- **Human fallback** when SLA breach predicted (**M4** exceptions).

### Out of scope (explicit)

- **Citywide** scaling beyond v1 geofence.  
- **Full catalog autonomy** + **dynamic pricing** (confounds learning).  
- **Full shopper app redesign** (not the hypothesis).  
- **Multi-retailer** network effects in v1.  
- **Custom perception stack** (partners own core AV; Isaac = **validation**).

---

## 6. Timeline — 0–30–60–90 (S8-5)


| Phase                 | Days  | Milestone                                                            | Gate (numeric)                                                                                                               |
| --------------------- | ----- | -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Setup**             | 0–30  | Signed **MOU/SOW**; **geofence v1**; **single MFC** handoff live     | **≥10** end-to-end **dry-run** orders; **≥90%** success **without** manual rescue                                            |
| **Limited beta**      | 30–60 | **≤500** invited users; **robots primary**; **drones ≤20%** of trips | **≥100** **paid** pilot orders; **on-time ≥75%**; **contact rate ≤15%**                                                      |
| **Scale-in-geofence** | 60–90 | Open to **all eligible** campus users; tighten ops                   | **≥450** **cumulative** completed orders; **on-time ≥80%**; **0** **reportable** injuries                                    |
| **Day 90 decision**   | 90    | Phase 2 expansion vs hold                                            | **GO** if **all** day-90 thresholds met (**full list in M8**). **NO-GO** → hold geography; **30-day** root-cause containment |


**Aerial inclusion:** **≤20%** drone trips in **30–60** phase — satisfies **“pilot includes aerial”** without drone-first risk (**user lock**).

---

## 7. Mock spec — pilot control panel (**M4** overlap)

For **map/geofence** UI: **eligible addresses** shaded, **MFC** node, **robot/drone** route legend, **exception** pins — **one** slide or **composite** with fleet dashboard (**M4**).

---

## 8. Headline options

1. **“GMU v1: one geofence, one MFC, two modalities — gated.”**
2. **“Campus beachhead → prove ODD, then widen like Waymo.”**
3. **“MVP = eligibility + custody + exceptions + fallback — nothing else.”**

---

## 9. VERIFY

- **Starship × GMU** current status (press/FAQ).  
- **MOU** parties named correctly for interview (Instacart vs retailer vs university).  
- **Reconcile** phase **80%** on-time vs **M6** **95%** register — see **M8 crosswalk**.

---

## 10. Next

`**M8_metrics.md`** — **S8-7**, **S8-8**, **S9-1 — S9-6** + gate harmonization.