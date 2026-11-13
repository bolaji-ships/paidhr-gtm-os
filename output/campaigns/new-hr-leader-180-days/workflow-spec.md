# Workflow Spec: New HR Leader, First 6 Months

**Status:** STRUCTURE-REVISED 2026-11-12 (window 180 days, 10 to 1,000 employees, global HRIS gate removed) · copy approved 2026-11-11 needs re-check for 200 to 1,000 employee companies (see Copy, Re-check after 2026-11-12 changes) · C1, C2 only; C3 to C6 on hold · not sendable until facts.md approval, sender consent and suppression lists

Signal matrix reference: SG8 / W7 in `context/icp/signal-matrix.md` (scored 12/20 there; buying reason INFERRED, sg Signal 4).
Methodology: `knowledge-base/playbooks/workflow-anatomy.md`, `knowledge-base/playbooks/signal-matrix-framework.md`.
Source tags: co = company.md, cu = customers.md, cv = customer-videos.md, cmp = competitors.md, mk = market.md, sg = signals.md, vo = voice.md (all in `context/docs/research/`); fx = `context/messaging/facts.md`. **INFERRED** = our reading, not sourced.

---

## 1. Mother Intent (Trigger) [ENGINE]

**Companies in Nigeria, Kenya or Ghana where an HR or People leader joined from another company and started in the role within the last 180 days (6 months).**

- Catalog match: ⭐ "New leadership (past 90/180 days)", Leadership & People Movement, `workflow-anatomy.md`. Window set to 180 days by the user (2026-11-12; was 100 days from 2026-11-07). The catalog lists 90 or 180 days.
- Signal-led: the start date fires the send. Country and industry only route the narrative.

## 2. Inclusion / Exclusion [ICP]

### Include

**ICP box**
| Filter | Value | Source |
|---|---|---|
| Company HQ country | Nigeria, Kenya or Ghana | icp.md Layer 1 (Nigeria first; Kenya, Ghana secondary); user decision 2026-11-07 |
| Employees | 10 to 1,000 | User decision 2026-11-12 (was 10 to 199). Floor: switch point 10 to 15 (sg Part A). Above 200 is S4 in signal-matrix.md (medium-low priority) and outside the observed base, "mostly under 200" (co §4) |
| Industry | Any, except exclusions below | signal-matrix.md |

**Trigger definition**
- Current title contains any of: Head of HR, Head of Human Resources, HR Manager, Human Resources Manager, HR & Admin Manager, Head of People, Head of People & Culture, People Lead, People Operations Manager, People Operations Lead, HR Director, Director of Human Resources, Chief People Officer, CHRO, HR Lead.
- Current title contains none of: Assistant, Intern, Officer, Executive, Coordinator, Recruit, Talent, Learning, L&D, Payroll (junior or specialist roles that don't own the HR stack; INFERRED).
- Current role started 0 to 180 days before the run date.
- Joined from outside: the previous position's company is different from the current company. Internal promotions are excluded, because the user's wording is "joined the company" (the catalog also lists promotion as a separate intent).
- The person is located in the same country as the company HQ.

**Recipient:** the new HR or People leader, i.e. the HR lead (champion) persona in `context/icp/personas.md` §1. Founder and finance lead are not contacted in v1.

### Exclude
| Who | Why | How matched |
|---|---|---|
| PaidHR customers named in research: Famasi, Heroshe, Transport Services Limited, Oando, Flutterwave, Risevest, MAX, Dantata, Bamboo, Busha, Nikky Taurus | Customers (cu §2; cv) | Domain or name blocklist, plus `{{customer_suppression_list}}` from PaidHR (not in research) |
| PaidHR partners and investors: FairMoney MFB, YALO, FUNDiT, Sync Capital, Yield MFB, Raenest, RemoFirst, Zitra, LSETF, Accion | Not prospects (co §12; cmp Reference) | Name blocklist |
| Competitors: SeamlessHR, Workpay, SoftSUITE (Soft Alliance), SystemSpecs (HumanManager), Bujeti, Salario, Paypaxe, Xceed365HR, Deel, Remote, Oyster, Cadana, Bento Africa, Payroll.ke (Pluspeople Kenya), FaidiHR, PayRollGH | Competitors (cmp Summary table, §23, §24) | Name blocklist |
| Recruiters, staffing firms, HR consultancies | Hire HR people for clients, don't run their own payroll at scale (sg Part C) | LinkedIn industry = Staffing and Recruiting, or Human Resources Services |
| NGOs, multilaterals, government bodies | Likely on global HRIS (sg Part C note; INFERRED) | LinkedIn industry = Non-profit Organizations, International Affairs, Government Administration |
| New leaders whose previous employer is a PaidHR customer | That's champion migration (SG13); the catalog says not to combine it with other intents | Previous company on the customer list: route to a parked SG13 list |
| Contacted in the last 90 days or in active pipeline | No double-touching | `{{crm_suppression_list}}` from PaidHR (no CRM in research) |

## 3. Sources [ENGINE]

| Purpose | Source | Tool | Status |
|---|---|---|---|
| Trigger: HR leaders with a start date in the last 180 days | LinkedIn people data | Clay "Find People" with country, title keywords and start-date filters | NG/KE/GH coverage untested. Alternative: a treg people-search tool (none tested in research yet) |
| Person detail: current title, start date, previous employer | LinkedIn profile | Clay "Enrich Person", or treg `harvestapi` LinkedIn profile (used in research; cv) | treg path tested |
| Company detail: headcount, industry, HQ country, domain | LinkedIn company page | Clay "Enrich Company", or treg `harvestapi.linkedin.company.profile` (co §15a) | treg path tested |
| Existing HR team count | LinkedIn people at the company with HR titles | Clay "Find People" at the company domain | Untested |
| Work email | Email waterfall | `tools/rex/templates/waterfall-work-email.json` in Clay | Provider and cost unknown |
| Country facts for copy | Nigeria mk §1 to §3; Kenya mk §6; Ghana mk §8 | none needed (research files) | Ghana thin |

**Before the build:** run one trigger search per country to count volume (10 to 1,000 employees, 180 days, three countries). This is a paid Clay or treg call: ask first.

## 4. Signals table [ENGINE]

| # | Signal | Role | How it's read | Output |
|---|---|---|---|---|
| 1 | New HR leader who joined from another company | trigger | Current title matches the include list AND doesn't match the exclude list (keyword match) AND days since the current role started is 180 or fewer AND the previous employer's domain is different from the current company's domain | `is_new_hr_leader` (true/false) |
| 2 | Company HQ country | router | Company HQ country equals Nigeria, Kenya or Ghana (exact match) | `country`: NG / KE / GH |
| 3 | Deskless-heavy industry | router | Company LinkedIn industry is one of: Truck Transportation; Transportation, Logistics, Supply Chain and Storage; Retail; Manufacturing; Food and Beverage Manufacturing; Construction; Hospitals and Health Care; Farming (exact match; mapping to the S2 segment is INFERRED) | `deskless_industry` (true/false) |
| 4 | First HR hire | context-clause (never routes) | Count of other people at the company whose titles contain HR, Human Resources or People, not counting the new leader. Groups: 0 = first HR hire; 1 or more = joining an existing HR team | `first_hr_hire` (true/false) |
| 5 | Previous employer | context-clause (never routes) | Company name of the person's previous position (field read) | `previous_company` (text) |

Routing axes: country (3) × deskless industry (2) = 6 cells.

Left out on purpose:
- Funding status: wouldn't change the angle for an HR leader.
- Hiring velocity: needs a job pull per company; it's a separate build (W2).
- Headcount band: it's a filter, not a router.
- Days in role: doesn't change the angle.
- Global HRIS check (Workday, SuccessFactors, Oracle HCM in job posts): removed by the user 2026-11-12. icp.md lists a global HRIS as not a fit, so expect some sends to companies already on one.

## 5. Routing matrix with angles [ENGINE]

Fires in every cell: `is_new_hr_leader` = true.

What every cell assumes (INFERRED): a leader in their first six months in the role is mapping how things run today, including payroll, statutory deductions and staff requests, and setting their first priorities. No source ties this to a software purchase (sg Signal 4).

| Cell | Deterministic read | What it tells us (inferred situation) | The angle it earns |
|---|---|---|---|
| C1. Nigeria, mostly site or shift staff | `country` = NG AND `deskless_industry` = true | A new HR leader at a Nigerian company with drivers, site, warehouse or shift staff is mapping payroll and remittances across office and field workers. Nigerian law requires pension for "every worker on its payroll", casual staff included, within 7 working days of payday (mk §3.1). Since 1 Jan 2026, PAYE has run on new bands (mk §1.2). Field staff often can't reach a portal (INFERRED); WhatsApp/USSD access is built for workers without the app (co §15d). | Their review should cover the workers who never sit at a desk. One run covers payroll, PAYE and pension for every worker on the payroll, site and casual staff included. Field staff get payslips, leave and earned wages on WhatsApp or USSD with no app. Proof: Heroshe, a Nigerian logistics team, on remittances with receipts and payslip self-service (cv Video 2; fx). |
| C2. Nigeria, office-based | `country` = NG AND `deskless_industry` = false | A new HR leader at a Nigerian office-based company is taking over a payroll that had to change on 1 Jan 2026. The changes: rent relief backed by documents in place of CRA, bonuses and 13th-month pay added to the PAYE base, and PAYE due on gratuity before payout (mk §1.3, §1.4). They are probably checking whether payroll applies these. The employer carries the PAYE liability (mk §1.4). | Their first payroll review falls in the first year of the new tax law. PaidHR is "Fully updated for Nigeria's new tax law, effective 1 January 2026", and files PAYE and pension straight to the right bodies, so they start with remittances on record instead of rebuilding them by hand. Proof: "₦934M PAYE and ₦754M pension remitted in 2025 with zero defaults and zero delays" (fx), and Famasi (fx). |
| C3. Kenya, mostly site or shift staff | `country` = KE AND `deskless_industry` = true | A new HR leader at a Kenyan company with field or site staff is checking statutory deductions across a large hourly workforce. NSSF Year 4 limits have applied since February 2026 payroll: lower limit KShs 9,000, upper limit KShs 108,000. Contributions are due by the 9th, with a 5% penalty compounded each month. NSSF discrepancies are "often used as a primary red flag" for a full KRA payroll audit (mk §6). | Year 4 NSSF limits applied for every worker, filed by the 9th, and field staff reach payslips and earned wages on WhatsApp or USSD, which is live in Kenya (fx). Proof: `{{kenya_proof}}`, none in research. |
| C4. Kenya, office-based | `country` = KE AND `deskless_industry` = false | A new HR leader at a Kenyan office-based company is in the first year of NSSF Year 4. The upper limit rose from KShs 72,000 to 108,000, and the maximum employee contribution from KShs 4,320 to 6,480 (mk §6). That change mostly hits salaried staff earning above the old limit (INFERRED from the sourced limits). | Their first payroll review falls in the year the NSSF upper limit moved, the change that touches salaried staff most. PaidHR applies the new limits and files by the 9th. Proof: `{{kenya_proof}}`, none in research. |
| C5. Ghana, mostly site or shift staff | `country` = GH AND `deskless_industry` = true | A new HR leader at a Ghanaian company with site or shift staff. The 2026 daily minimum wage is reported at GH¢21.77, up from GH¢19.97 (mk §8, search summary only), which touches hourly site pay. WhatsApp/USSD access is live in Ghana (fx). | Site workers paid at the 2026 minimum-wage rate, reachable on WhatsApp or USSD with no app. The minimum-wage figure needs a primary source first. Proof: `{{ghana_proof}}`, none in research. |
| C6. Ghana, office-based | `country` = GH AND `deskless_industry` = false | A new HR leader at a Ghanaian office-based company. New PAYE rates are reported from 1 Sep 2026 (mk §8, search summary only; the band table was not found), so their first six months overlap the first months of the new rates. | Their first payroll review overlaps the first months of Ghana's new PAYE rates. This needs a primary source for the rates and confirmation that PaidHR handles Ghana PAYE (not found). Proof: `{{ghana_proof}}`, none in research. |

### Lines that never route
| Variable | When true | When false |
|---|---|---|
| `first_hr_hire` | They're building the HR function from scratch. Payroll probably sat with the founder or finance until now (INFERRED; at Famasi the founder ran payroll, cv Video 1). | They're joining an existing team and its current tools. |
| `previous_company` | In every cell, because the trigger requires an outside hire. Copy can say where they came from, never what tools they used there. | n/a |

**Timing rule (Nigeria cells only):** if the send date falls between 1 Nov and 31 Jan, add the annual PAYE return due 31 January (mk §1.4). Outside those dates, leave it out.

**Branch coverage:** all 6 cells have first name, company name, current title, start date, previous company, country, workforce type and `first_hr_hire`. No angle depends on `first_hr_hire`. No cell needs data that doesn't exist in it.

**Niche-native test:** each angle ties a new outside hire in their first six months to a statutory change specific to that country and to the workforce type. C5 and C6 pass only weakly, because their country facts rest on search summaries.

### Which cells can launch
| Cells | Status | What unblocks them |
|---|---|---|
| C1, C2 (Nigeria) | Launch in v1 | Nothing. Every fact is in facts.md or a public law source. |
| C3, C4 (Kenya) | Hold: build, don't send | PaidHR confirms it runs Kenyan payroll with NSSF Year 4, SHIF and Housing Levy (not in research; a third-party review says its compliance expertise "centers on Nigeria", cu §5). A Kenyan proof point. Kenya facts added to facts.md. |
| C5, C6 (Ghana) | Hold: build, don't send | Ghana figures verified from a primary source (both are search summaries now). PaidHR confirms it runs Ghana payroll. A Ghanaian proof point. |

## 6. Variables contract [ENGINE]

Copy may use only these. If a variable isn't listed, copy can't say it.

| Variable | Source field | Exists in branches |
|---|---|---|
| `{{first_name}}` | Person first name (Clay Find People / Enrich Person) | All |
| `{{company_name}}` | Company name, legal suffix (Ltd, Limited, PLC) stripped by formula | All |
| `{{current_title}}` | Person current title | All |
| `{{start_month}}` | Month name of the current role's start date (formula on start date) | All |
| `{{previous_company}}` | Company name of the person's previous position | All |
| `{{country_name}}` | Lookup: NG = Nigeria, KE = Kenya, GH = Ghana | All |
| `{{industry_plain}}` | Lookup from LinkedIn industry to plain words (e.g. "Truck Transportation" = "logistics"); lookup table to be written at build | All |
| `{{first_hr_hire}}` | Signal 4 (true/false); copy needs a version for each value | All (both values) |
| `{{annual_return_window}}` | True if send date is 1 Nov to 31 Jan AND `country` = NG | C1, C2 only |
| `{{proof_name}}` | Static per cell: C1 = Heroshe, C2 = Famasi; C3, C4 = `{{kenya_proof}}`; C5, C6 = `{{ghana_proof}}` (none in research) | All (C3 to C6 unfilled) |
| `{{sender_name}}`, `{{sender_title}}` | Seye Bandele; Co-founder and CEO, PaidHR (fx Sender identity; user decision 2026-11-11) | All |
| `{{cta}}` | Not found in research (fx CTA ladder); PaidHR to decide | All (unfilled) |

Never available to copy:
- A raw headcount or HR-team count.
- Any tool used at the previous employer.
- Any claim that the prospect's company has missed a remittance or been penalised (fx banned angles).
- Monthly PAYE deadlines (sources conflict; mk §1.4).

## 7. Cadence & channel [ENGINE]

- **Periodicity:** always-on, run monthly. That's the playbook rate for leadership changes (`workflow-anatomy.md` Periodicity Matrix), and a 180-day window means every new leader is caught several times over; dedupe keeps it to one entry. Send only if days in role is still 180 or fewer on the send date.
- **Dedupe:** one entry per person (key: LinkedIn profile URL). After contact, suppress the company for 90 days. A new HR leader at the same company later can re-enter.
- **Channel:** email only (user decision 2026-11-07 during copy; LinkedIn dropped). Sender: Seye Bandele, Co-founder and CEO (user decision 2026-11-11). Three emails, day 0, 3 and 10, one thread.
- **Send gates:** C1 and C2 send. C3 to C6 collect in their own views with no sends until their blockers clear (Section 5).

---

## Definition of done
- [x] Mother intent: one sentence, signal-led, matched to the catalog
- [x] Inclusion: ICP box + trigger definition + recipient, tagged [ICP]
- [x] Exclusion: who's out and why
- [x] Sources: trigger + every enrichment
- [x] Signals table: every read deterministic, every role declared
- [x] Count clusters declared (Signal 4: 0 / 1 or more; context-clause only)
- [x] Routing matrix with every angle filled
- [x] Branch coverage checked
- [x] Variables contract: every variable mapped to its source field
- [x] Engine/ICP markers on every section
- [x] Cadence & channel declared

## Open items for PaidHR
1. Customer and CRM suppression lists.
2. Kenya and Ghana payroll support, plus a proof point for each (unblocks C3 to C6).
3. Confirm Seye Bandele agrees to send (sender set 2026-11-11); CTA written in copy.
4. OK to run the paid volume check per country (Section 3).

---

## Copy

Campaign: New HR Leader, First 6 Months, Nigeria, v1. Channel: email only (user decision 2026-11-07). Sequence: Email 1 day 0, Email 2 day 3, Email 3 day 10, one thread. Cells written: C1, C2. C3 to C6 on hold, no copy.
Facts: `context/messaging/facts.md` (all claims still PENDING PaidHR approval: drafts only, not for sending until approved).

### Email 1 (approved 2026-11-07)

**Subject (static):** {payroll at {{company_name}}|your first payroll review|{{company_name}} payroll question}

**Greeting:** {{first_name}},

**Line 1 (dynamic, routes on first_hr_hire; exhaustive, no fallback)**
+ first_hr_hire = true: You joined {{company_name}} from {{previous_company}} as its first HR hire, as far as I can tell, so you're likely still mapping how payroll works there.
+ first_hr_hire = false: You joined the HR team at {{company_name}} from {{previous_company}} in {{start_month}}, so you're probably still getting to know how payroll runs there.

**Line 2 (dynamic, routes on cell; exhaustive for Nigeria)**
+ C1 (deskless_industry = true): With {{industry_plain}} teams usually on sites and shifts, that includes people who rarely sit at a desk, casual staff too.
+ C2 (deskless_industry = false): And the 2026 tax rules changed how rent relief, bonuses and gratuity go through payroll.

**Line 3: value (dynamic, routes on cell)**
+ C1: PaidHR runs payroll, PAYE and pension for every one of them, and site staff get payslips, leave and earned wages on WhatsApp or USSD, no app needed.
+ C2: PaidHR is fully updated for Nigeria's new tax law, effective 1 January 2026, and remits PAYE and pension for you.

**Line 4: social proof (dynamic, routes on cell)**
+ C1: Heroshe, a cross-border shipping business, moved its statutory remittances onto PaidHR and got a receipt for each payment.
+ C2: Across its customers, that came to ₦934M PAYE and ₦754M pension remitted in 2025 with zero defaults and zero delays.

**CTA (static):** {Is payroll part of what you're reviewing first?|Is payroll on the list for your first few months?|Where does payroll sit on your list right now?}

**Sign-off (static):** {Best,|Thanks,} {{sender_name}}

Fact trace: C1 L3 WhatsApp/USSD (fx Deskless access; co §15d). C1 L4 Heroshe (fx authorized, past tense: current status unknown). C2 L2 (fx Market fact, 2026 rules). C2 L3 (fx Tax law; fx Variant B). C2 L4 (fx Remittance record, exact phrasing).

### Email 2 (approved 2026-11-11; day 3, same thread, subject "Re: <Email 1 subject>")

**Greeting:** {{first_name}},

**Line 1 (dynamic, routes on annual_return_window; exhaustive, no fallback)**
+ annual_return_window = true (send date 1 Nov to 31 Jan): Employer annual PAYE returns are due by 31 January, so the year's payroll records will be needed soon.
+ annual_return_window = false: Pension deductions have to reach each employee's pension account within 7 working days of payday, every month.

**Line 2: value (static):** {With PaidHR|On PaidHR}, PAYE and pension remittances run without spreadsheets or chasing receipts.

**Line 3: social proof (dynamic, routes on cell; swapped vs Email 1 so each lead gets new proof)**
+ C1: Across its customers, that came to ₦934M PAYE and ₦754M pension remitted in 2025 with zero defaults and zero delays.
+ C2: Famasi's CEO used to make tax and pension remittances by hand and then follow up to confirm them, until the team moved payroll to PaidHR.

**CTA (static):** {Would a short walkthrough of one payroll month be useful?|Worth a short walkthrough of one payroll month in PaidHR?}

**Sign-off (static):** {Best,|Thanks,} {{sender_name}}

Fact trace: L1 true (fx Market fact, 31 Jan annual returns; PaidHR filing annual returns NOT claimed). L1 false (fx Market fact, 7 working days). L2 (fx Variant B). C1 L3 (fx Remittance record, exact phrasing). C2 L3 (fx Famasi; paraphrase of cu §4 quote, past tense, no time figure per fx "keep fuzzy").

### Email 3 (approved 2026-11-11; day 10, same thread)

**Greeting:** {{first_name}},

**Line 1: new value (static):** {One last note from me|Last note from me}: PaidHR also lets {your team|your staff} draw on wages they've already earned before payday, at zero cost to your company.

**CTA, referral (static):** {If payroll sits with finance or the founder at {{company_name}}, who should I speak to?|If someone else owns payroll at {{company_name}}, who would be the right person to talk to?}

**Sign-off (static):** {Best,|Thanks,} {{sender_name}}

Fact trace: L1 (fx EWA cost, "Zero cost to your company").

### Review notes (2026-11-11)
- Email 1 Line 1 names the move outright ("You joined X from Y"), which bends Iron Law 1. Kept by approval; first thing to A/B test if replies are low.
- Email 3's referral CTA hints payroll may sit elsewhere; passes the insult test as a question.

### Re-check after 2026-11-12 changes (open)
- Headcount now reaches 1,000. Heroshe (C1, Email 1) and Famasi (C2, Email 2) are small teams, and fx says not to imply results for 100+ employee companies. Those proof lines need a different version for companies of 200 or more.
- Email 3 CTA names "the founder", which fits small companies better than 200 to 1,000 employee ones.
- Window now 180 days: Email 1 CTA variant "your first few months" still fits; no other line names a time window.
