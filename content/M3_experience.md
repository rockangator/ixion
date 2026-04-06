# M3 — Experience evolution (customer + shopper + retailer)

**Scope:** Checklist **S4-1**, **S4-2**, **S4-3**, **S4-6**.  
**Sources:** `Paperclip extracted/CX.txt` (revised CX package, INS-3 — post–QA compression + trust links in extract are cited there; **this file** does not re-host full exception/trust sections → **M4**).  
**Fragmentary:** `Paperclip generated/cx-deliverables-part*.md` (tables truncated in repo — **CX.txt** is canonical for blueprint rows).  
**Deferred to M4:** S4-4 exceptions, S4-5 trust patterns, S5 mock brief (cross-reference).

---

## 1. Checklist coverage

| ID | Addressed |
|----|-----------|
| S4-1 | §3 customer column + §5 journey summary |
| S4-2 | §4 shopper column |
| S4-3 | §6 retailer column |
| S4-6 | §7 tradeoffs (honest PM framing) |

---

## 2. Core argument (draft)

Autonomous last mile changes **three** experiences at once—not only the customer app. **Customers** need **mode choice**, **honest ETAs**, and a **machine handoff** they can complete without a stranger. **Shoppers** stop “hand to driver” and instead **load + scan** into a **dock chain-of-custody**. **Retail partners** gain **staging lanes, packaging rules, and incident economics**—the B2B surface Instacart lives on. The blueprint below makes **handoffs explicit** (H1–H11) so product, ops, and legal can align before pixel work (**M4**).

---

## 3. Customer journey — what changes (S4-1)

| Phase | Today (human courier) | Future (autonomous-eligible) |
|-------|------------------------|------------------------------|
| **Setup / checkout** | Slot + broad ETA | **Autonomy-eligible** slot when basket + zone match; **delivery mode** + **ETA range** visible before pay (**H1** eligibility → UI). |
| **Order accepted** | “Shopper assigned” | “**Picker + autonomous vehicle reserved**” — two resources, one promise. |
| **Pick + substitute** | Chat-based subs | Async sub approval with **no-delay** framing; picker picks to **AV packaging spec**. |
| **Load + dispatch** | Wait for “driver on the way” | **“Vehicle loading”** + **dock lock ETA** — customer sees **custody moving** to machine. |
| **In transit** | Map + single ETA | **Mode chip** (robot / drone / human), **route**, **ETA band + confidence** — telemetry-owned, not driver-tapped. |
| **Arrival + handoff** | Meet courier / leave-at-door | **Arrival countdown** + **unlock / PIN / secure retrieval** — explicit **machine-to-customer** exchange (**H9**). |
| **Post-delivery** | Rate + support | **Proof** (photo / bin event) + **mode-specific feedback**; **proactive recovery** if incident (**H11**). |

**Pilot anchor (GMU):** Copy and flows assume **geofenced** orders; out-of-fence stays **human** (see **M2**).

---

## 4. Shopper / picker journey — what changes (S4-2)

| Phase | Today | Future |
|-------|--------|--------|
| **Assignment** | Batch + route for driving | **Pick task + dock lane** — no driving; **monitor exceptions only**. |
| **Picking** | Standard bagging | **Tamper-evident + weight / volume** constraints for robot pod / drone payload (**H5** packaging gate). |
| **Handoff** | Hand bags to courier | **Load pod → scan seal** — **two-step custody**: picker → **dock marshal** → vehicle (**H6–H7**). |
| **In transit** | Active driving + status pings | **Exception alerts** (stuck, link loss, failed unlock); optional **paid nearby assist** rules (marketplace policy). |
| **Completion** | Photo POD to customer | **Mission complete** in app; **reverse logistics** only if return-to-store / re-shop (**H11**). |

**PM point:** Shopper work **shifts up** the stack—**accuracy, load quality, and exception handling** matter more than miles driven.

---

## 5. Retail partner journey — what changes (S4-3)

| Phase | Today | Future |
|-------|--------|--------|
| **Catalog / capacity** | Inventory + slots to marketplace | **Autonomy eligibility** by **SKU / zone / time** (what can ride in AV vs not) (**H1**). |
| **Order accepted** | Confirms availability | Confirms **staging-lane capacity** + **autonomy queue** slot. |
| **Picking support** | OOS policy | **Autonomy-compliant packaging** on hand; **dock** staffing window. |
| **Dispatch** | Assist store exit | **Seal verification** + **release from dock** — explicit **launch approval**. |
| **In transit** | Often none | **Fleet lane health** on partner dashboard (optional v1); **incident** = SLA + **custody / shrink** attribution. |
| **Failed handoff** | Refunds | **Relaunch / retrieve** workflows; **return-to-store** manifest; **fees per contract**. |

**PM point:** Retailers experience autonomy as **dock real estate + rules + money**—must be **designed**, not assumed.

---

## 6. Service blueprint — stages × actors (synthesized from CX.txt)

**Handoffs:** **H1–H11** as in INS-3 revised thread.

| Stage | Customer (future) | Shopper (future) | Retail (future) | Handoffs |
|-------|-------------------|------------------|-----------------|----------|
| **1. Order setup** | Mode + ETA range at checkout | — | Publishes **eligibility** by basket/zone/time | **H1** Eligibility engine → checkout UI |
| **2. Order accepted** | “Picker + AV reserved” | Accepts pick + **dock lane** | Confirms **staging** capacity | **H2** Allocator → picker; **H3** Allocator → vehicle |
| **3. Pick + substitute** | Timer-based sub approval | Pick to **AV packaging spec** | Tamper-evident materials | **H4** Sub flow; **H5** **Packaging compliance gate** |
| **4. Load + dispatch** | “Vehicle loading” + lock ETA | Load pod, **scan seal** | Verify seal, **release dock** | **H6** Picker → marshal; **H7** Marshal → robot/drone |
| **5. In transit** | Mode chip, band, live route | Exception monitor only | Lane health (ops) | **H8** Telemetry → tracking service |
| **6. Arrival + handoff** | Countdown + **unlock** | Remote assist if incident | Retrieve / relaunch if fail | **H9** AV → customer; **H10** Exception → remote ops |
| **7. Post-delivery** | Proof + mode feedback | Reverse logistics task | Inventory + **custody logs** | **H11** Incident → compensation / support |

*(Stage naming aligned to CX.txt “Order setup → Post-delivery”; minor labels merged for slide density.)*

---

## 7. Drawbacks & tradeoffs — honest (S4-6)

| Tradeoff | Implication |
|----------|-------------|
| **Payload / compartment** | Robot/drone **cannot** absorb arbitrary Costco runs; **human retain** for heavy weekly shops (**M2**). |
| **Time vs car** | Short-hop robot may lose vs **optimized car courier** on some legs—**position as reliability + cost + availability**, not always “fastest.” |
| **Weather / terrain** | Rain/snow/ice and bad sidewalks **degrade** AV SLA → **fallback** volume must be planned (**M6/M7**). |
| **Trust cold-start** | First autonomous trip has **higher anxiety**; **mode education** + **recovery** quality matter more than marketing (**M4**). |
| **Alcohol / restricted SKUs** | **ID / compliance** often keeps **human** lane—don’t oversell autonomous catalog in pilot. |
| **Operational load at store** | Dock, marshal time, and **incident** handling are **real costs**—partners must **opt in** with clear economics. |

---

## 8. Headline options

1. **“Three-sided fulfillment: customer, shopper, retailer all change.”**  
2. **“From handoff-to-driver to custody-to-machine.”**  
3. **“Experience isn’t the map — it’s eligibility, chain-of-custody, and recovery.”**

**Cliffhanger:** “When the robot stops moving, the product is **exception UX**—see **M4**.”

---

## 9. Visual spec (content-only)

- **Primary:** **Swimlane** or **7-row × 3-column** table (Customer | Shopper | Retail) for **future state** only; **H1/H5/H7/H9** called out as **icons** on handoff cells.  
- **Optional inset:** One **before/after** arrow for **“hand to courier” → “scan to dock”**.  
- **Avoid** here: full decision trees and mock frames → **M4**.

---

## 10. Bridge to M4 (exceptions, trust, mocks)

- **S4-4** Robot stuck / drone link / not home → **`M4`**, § exception trees + summary matrix.  
- **S4-5** Mode clarity, ETA bands, recovery copy → **`M4`**, § trust + precedents (Waymo, Lyft/Uber help, Amazon tracking).  
- **S5-1 — S5-3** Mock specs → **`M4`**, aligned with numbered screen list in CX.txt; **fleet dashboard** from your prep → **M4** or **M7** mock row.

---

## 11. Appendix — precedent URLs (for M4 reuse; trust section lives in extract)

From **CX.txt** revised package (INS-3): Waymo One / Austin, Lyft scheduled rides help, Uber Reserve/elite, Amazon track / shipping insights. **Paste into deck footnotes when M4 finalizes copy.**

---

## 12. VERIFY / open items

- [ ] Confirm **7 stages** fit target slide density (may **collapse** to 5 for PDF: merge setup+accepted, pick+load).  
- [ ] Align **H#** labels with any **Narrative Architect** slide map (rename only if needed for consistency).  
- [ ] Retail **dashboard** depth: **pilot MVP** vs **vision** — flag for **M7** scope.

---

## 13. Next module

**M4** — Trust, exceptions, mock designer brief (**S4-4**, **S4-5**, **S5-1 — S5-3** + fleet / ops mock spec).
