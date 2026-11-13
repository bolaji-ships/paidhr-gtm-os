# PaidHR Signal Matrix

**Status: WORK IN PROGRESS, v0.1 (2026-11-07).** Built by Claude from research only. Not validated with PaidHR sales or leadership. Every cell is a hypothesis to test in a strategy session.

Method: `knowledge-base/playbooks/signal-matrix-framework.md` and the Mother Intent Catalog in `knowledge-base/playbooks/workflow-anatomy.md`.

Sources: `context/icp/icp.md`, `context/icp/personas.md`, `context/docs/research/`. Source tags as in `icp.md`: co = company.md, cu = customers.md, cv = customer-videos.md, cmp = competitors.md, mk = market.md, sg = signals.md, vo = voice.md (section numbers after the tag). fx = `context/messaging/facts.md`.

**INFERRED** = our reading, not supported directly by the research. Everything else carries a source tag.

---

## 0. What we are selling, to whom

| Item | Summary | Source |
|---|---|---|
| Product | Single product: full-suite HRMS (HR, payroll, statutory remittance, time and attendance, performance) plus employee financial products (EWA, wallet, loan marketplace) on web, app, WhatsApp and USSD | co §1, §2, §15d |
| Core pain | Payroll and statutory remittances (PAYE, pension) done by hand, in spreadsheets, or across 4 to 6 tools | sg Part A; cv Video 1, 2 |
| Who buys today | Mostly under 200 employees; logistics, retail, manufacturing, banking; earlier financial services, construction and engineering, consulting; a few large accounts (TSL, Oando, Flutterwave) | cu §1, §2; co §4 |
| Market | Nigeria first. Kenya, South Africa, Ghana secondary; customer volume there unknown | mk §0; icp.md open questions |
| Plans | Standard 20 to 100 employees; Enterprise 100+; Custom. No published prices | co §3 |
| Switch point | "Most startups switch when they reach 10 to 15 employees." | sg Part A |
| Competitors | SeamlessHR (mid to enterprise), Workpay, SoftSUITE, Bujeti, Salario, Paypaxe, Deel / Deel Local Payroll | cmp Summary table |

Because PaidHR is a single product, Matrix 1 has no product columns. The angle changes per cell instead (framework Step 4).

---

## Matrix 1: Segments x Personas

### How the segments are cut

Rows are cut on what changes fit, urgency and reachability for PaidHR: headcount band (the plan tiers and the 10 to 15 switch point), whether the company is VC-backed (data richness, founder-led buying), and workforce type (the deskless angle behind WhatsApp/USSD).

**Assignment rule, so each company lands in one row only.** Apply in order:
1. Fewer than 3 employees: not a fit (below the pension threshold; mk §3.1). Exclude.
2. 200+ employees: **S4**.
3. 3 to 19 employees and no venture funding: **S5**.
4. Venture-funded (any round on Africa: The Big Deal, Crunchbase or a Nairametrics/Techpoint roundup) and 10 to 199 employees: **S1**.
5. 20 to 199 employees, industry with mostly site, shift or field staff (logistics, transport, retail, FMCG, manufacturing, construction and engineering, agro-processing, healthcare providers): **S2**.
6. 20 to 199 employees, office-based industry (financial services, consulting and professional services, education, media): **S3**.

Every row: HQ or payroll in Nigeria (v1 scope). Exclude companies that already run a global HRIS (job posts naming Workday or SAP), PaidHR partners (e.g. FairMoney MFB, co §12) and recruiters posting for unnamed clients (sg Part C).

The cut-offs at 10, 20 and 200 come from sources: the switch point (sg Part A), the Standard plan floor (co §3) and "mostly under 200 employees" (co §4). Using them as segment edges is **INFERRED**.

### The grid

Persona columns follow `personas.md`: **HR lead** (champion), **Founder / CEO / MD** (economic buyer), **Finance lead** (influencer). ★ marks the persona to lead with in each segment (**INFERRED**). Angles use buyer words where the research has them.

| Segment | HR lead | Founder / CEO / MD | Finance lead |
|---|---|---|---|
| **S1. VC-backed startups, 10 to 199** | Often the first HR hire, inheriting payroll from the founder (**INFERRED**). Angle: payslip requests and remittance receipts off your desk from day one; staff self-serve instead of "every single time... they always reach out to me" (cv Video 2). | ★ Angle: get back the hour you set aside every payday "just to manually make payments" and to chase tax and pension remittances (cv Video 1). Switch before "15+ hires, everything breaks at once" (sg Part A). Proof: Famasi (fx). | Angle: a clean payroll record every month. "Many businesses cannot produce a clean payroll record for a given month" (sg Part A). Investor or audit reporting as the reason is **INFERRED**. |
| **S2. Deskless-heavy SMEs, 20 to 199** | ★ Angle: drivers, pickers, site and shift staff get payslips, leave and earned wages on WhatsApp or USSD, "without downloading an app or logging into a portal" (co §15d), so requests stop landing on HR. | Angle: one payroll run for office and site staff, with PAYE and pension remitted and receipts to show (sg Part A; cv Video 2). EWA at "Zero cost to your company" (co §3) as a retention lever; the retention link is unattributed press (cu §3), so treat it as **INFERRED**. | Angle: pension must be remitted for "every worker on its payroll", casual staff included (mk §3.1), within 7 working days of payday. Payroll financing "when cash flow gets tight" via the Zitra partnership (co §15d). |
| **S3. Office-based SMEs, 20 to 199** | ★ Angle: the 2026 tax law changed what payroll has to calculate: rent relief with documents, bonuses and 13th month in the PAYE base, PAYE on gratuity (mk §1.3, §1.4). PaidHR is "Fully updated for Nigeria's new tax law" (mk §0). | Angle: the employer carries the PAYE liability; failure to deduct "attracts a 40% administrative penalty" (mk §1.5). "The compliance template has been flipped" (mk §1.5, LIRS adviser). | Co-buyer. Angle: "Instead of juggling spreadsheets and bank uploads", remittances go "directly to the right bodies" (sg Part A); no "month end surprises" (sg Part A). |
| **S4. Mid-market and enterprise, 200+** | ★ HR Director, Head of People, HRBP. Angle: one platform instead of "4-6 separate tools for HR, each with its own login" (sg Part A), with reach to deskless staff (co §15d). Fit at this size is **INFERRED**: no customer proof is cleared for copy at 100+ employees (fx proof caveats). | Not the buyer at this size (**INFERRED**). Skip. | CFO, Head of Finance. Angle: PenCom's new system "auto-calculates penalties", and late payers "will not be able to get your pension plan certificate" until they pay (mk §3.2). Must not imply the prospect is a defaulter (fx banned angles). |
| **S5. Small formalising businesses, 3 to 19** | Usually no HR lead (**INFERRED**). Skip. | ★ The only buyer. Angle: pension becomes mandatory at 3 employees, with an employer code and remittance within 7 working days (mk §3.1). "It works when you have three to five people. It starts to shake at ten." (sg Part A). | Often an outside accountant (**INFERRED**). Possible channel play: PaidHR's payroll-bureau offer, "Launch your own Payroll business today!" (co §3, quoted from the pricing page). |

**Employees** are not a buying column but they are a pull channel in every segment: app, EWA and "Refer your Employer" (vo §6; cu §5a; **INFERRED** as influence).

### Segment definitions and examples

Company examples come only from the research files. No new searches were run for this version. Where a company's headcount or industry is not in the research, its segment placement is **INFERRED** until enriched. Current customers are listed as **lookalike seeds** for targeting only: they are not prospects, and only Famasi and Heroshe may be named in copy (fx).

#### S1. VC-backed startups, 10 to 199 employees. Priority: HIGH
- **Target definition:** Nigeria-HQ, venture-funded (any round), 10 to 199 employees on LinkedIn or Apollo, any industry; mostly office or remote staff.
- **Why:** Both customer videos are small venture-backed teams (Famasi, pre-seed; Heroshe, 11-50 band) (cv). Press-named customers Busha, Risevest and Bamboo are fintechs of similar size (cu §2). The founder runs payroll until the team grows (cv Video 1).
- **Lookalike seeds:** Famasi, Heroshe, Busha, Risevest, Bamboo (cu §2; cv).
- **Prospect examples from research (placement INFERRED):**
  - ChipMango: $1.9m seed, Sep 2026 (sg Signal 3)
  - Trade Lenda: $200k, Sep 2026 (sg Signal 3)
  - AirSmat: $200k, Sep 2026 (sg Signal 3)
  - Ororo Waste: $1m, Sep 2026 (sg Signal 3)
  - Raven: Head of People and Culture appointed Dec 2025, from a search summary (sg Signal 4)
  - Obiex: expanding to Ghana and South Africa, Feb 2026 (sg Signal 5)
  - Finwerd: HR Operations Analyst posting, 2026-11-04 (sg Part C)
  - Fiscal 12: People Operations analyst posting, 2026-10-30 (sg Part C)
  - Funding status for Finwerd and Fiscal 12 is not in research.
- **Clay filters to find more:** Country = Nigeria; employees 10 to 199; has a funding round in the Africa: The Big Deal or Crunchbase data; exclude Workday or SAP in job posts.

#### S2. Deskless-heavy SMEs, 20 to 199 employees. Priority: HIGH
- **Target definition:** Nigeria-HQ, 20 to 199 employees, in logistics and transport, retail and FMCG, manufacturing, construction and engineering, agro-processing, or healthcare providers. Mixed office and site, shift or field staff.
- **Why:** This is the core customer base: "most of which are in the logistics, retail, and manufacturing sectors" (cu §2). PaidHR's newest launch, WhatsApp/USSD access for staff without the app, is aimed at these workers (co §15d).
- **Lookalike seeds:** Transport Services Limited (first customer), MAX (cu §2). TSL's headcount is disputed (201-500 to 2,000), so it may belong in S4 (cu §2).
- **Prospect examples from research (placement INFERRED):**
  - Viju Industries (Nigeria) Limited: HR Manager posted twice, Edo State (sg Part C)
  - Trevi Group: HR Manager and HR Coordinator (sg Part C)
  - Sunda International: recruitment managers, Lagos and Sagamu (sg Part C)
  - Ultimum Limited: People Business Partner, Aba (sg Part C)
  - Drive45: logistics, $3m debt, Sep 2026 (sg Signal 3)
  - ThriveAgric: $3.9m debt, Aug 2026 (sg Signal 3)
  - Reddington Hospital: Group Head of HR, date not verified (sg Signal 4). May belong in S4.
- **Clay filters to find more:** Country = Nigeria; employees 20 to 199; LinkedIn industry in Truck Transportation, Logistics and Supply Chain, Retail, Manufacturing, Food and Beverage, Construction, Hospitals and Health Care, Farming.

#### S3. Office-based SMEs, 20 to 199 employees. Priority: MEDIUM
- **Target definition:** Nigeria-HQ, 20 to 199 employees, not venture-funded. Financial services (MFBs, insurance, asset managers), consulting and professional services, education, media.
- **Why:** In 2023 the largest clients were in "financial services, construction and engineering, and consulting" (cu §2). Office staff make these companies easy to reach on LinkedIn (**INFERRED**). The tax-law angle fits salaried staff with rent relief, bonuses and gratuity (mk §1.3, §1.4).
- **Lookalike seeds:** None cleared. Nikky Taurus's industry is unknown (cu §2).
- **Prospect examples from research (placement INFERRED):** FITC Nigeria: new Head of People & Culture, Nov 2025, from a search summary (sg Signal 4). Industry and size not in research for the following, so their segment is open until enriched:
  - Xftech: HR Manager, Lagos (sg Part C)
  - The Concept Group: Senior HRBP (sg Part C)
  - StreSERT Integrated: Head People and Culture (sg Part C)
  - FAMAD PLC: Head of HR and Admin (sg Part C)
- **Clay filters to find more:** Country = Nigeria; employees 20 to 199; LinkedIn industry in Financial Services, Banking, Insurance, Investment Management, Business Consulting, Accounting, Legal Services, Education, Media; no funding round.

#### S4. Mid-market and enterprise, 200+ employees. Priority: MEDIUM-LOW
- **Target definition:** Nigeria-HQ or Nigeria payroll, 200+ employees, any industry, no global HRIS in place.
- **Why medium-low:** PaidHR has named enterprise customers (Oando, Flutterwave, TSL; cu §2), but none is cleared for copy (fx). SeamlessHR leads this tier (cmp Summary table), and larger firms are more likely to run Workday or SAP (sg Part C; **INFERRED**).
- **Lookalike seeds:** Oando, Flutterwave, TSL (cu §2).
- **Prospect examples from research (placement INFERRED):**
  - Ardova Plc: Senior Total Rewards Analyst (sg Part C)
  - Moniepoint Group: Lead, Contracts & HR Administration (sg Part C)
  - Moove: $250m Series C (sg Signal 3)
  - Jumia: $50m (sg Signal 3)
  - Dangote Industries: Plant HRBP (sg Part C); an incumbent HRIS is **INFERRED** and should be checked
  - Bristow Group: HR Operations Specialist (sg Part C); multinational, incumbent HRIS **INFERRED**
- **Exclude:** Vertu Agent (Workday Administrator posting) and FairMoney (PaidHR loan partner) (sg Part C).

#### S5. Small formalising businesses, 3 to 19 employees. Priority: LOW
- **Target definition:** Nigeria (Lagos first), 3 to 19 employees, no venture funding.
- **Why low:**
  - Below the Standard plan floor of 20 (co §3).
  - PaidHR's own blog says manual methods work at "three to five people" (sg Part A).
  - Weak data footprint (**INFERRED**).
  - The LSETF programme already gives 100 businesses a free year (co §3), and whether it is still open is unknown.
- **Prospect examples:** None in research. LSETF cohort names are not public (cu §2).
- **Clay filters to find more:** Country = Nigeria; employees 3 to 19; Lagos; no funding. Expect thin coverage.

**Parked segment:** Kenya and Ghana SMEs. Kenya has a strong compliance trigger: NSSF Year 4 with "Update payroll software/systems" advice (mk §6), and WhatsApp/USSD is live there (co §15d). Customer volume in these markets is unknown (icp.md). Revisit once PaidHR confirms it wants outbound there.

---

## Phase 2: Segment scores and priority

| Segment | Signal density | Product fit | Reachability | Priority | One-line reason |
|---|---|---|---|---|---|
| S1 VC-backed, 10 to 199 | High | High | High | **HIGH** | Both video customers sit here; funding, hiring and headcount data are rich for tech firms (sg Signal 3, Part C; cv) |
| S2 Deskless, 20 to 199 | Medium | High | Medium | **HIGH** | Core customer industries, plus the newest launch (WhatsApp/USSD) is built for them (cu §2; co §15d). LinkedIn coverage of site staff is weaker (**INFERRED**) |
| S3 Office-based, 20 to 199 | Medium | Medium | High | **MEDIUM** | Past largest clientele (cu §2) and a clean tax-law angle, but no cleared proof points |
| S4 200+ | High | Medium | Medium | **MEDIUM-LOW** | They post HR roles often (sg Part C), but incumbents and SeamlessHR are strong here, and no proof is cleared for copy |
| S5 3 to 19 | Low | Low | Low | **LOW** | Below plan floor, thin data |

Scores are **INFERRED** judgments drawn from the evidence cited. Recommended order: S1 and S2 first, S3 second. Hold S4 and S5 until PaidHR confirms appetite.

---

## Matrix 2: Signals

### Scoring the four tests

These are the four tests in `workflow-anatomy.md`, "Choosing a Mother Intent". Each is scored 1 to 5, for a total out of 20.

| Test | 5 means | 3 means | 1 means |
|---|---|---|---|
| **Reason**: clear buying reason | Research shows the event creates payroll or HR software need (PaidHR or a legal source) | Plausible but **INFERRED** | Weak or no link |
| **Volume**: enough volume | Hundreds of companies a month | Dozens a month | A handful a quarter, or unknown |
| **Data**: data you can get | Already pulled in research with a named tool | Source exists, not yet pulled at company level | Needs manual research or data PaidHR hasn't shared |
| **Story**: natural story | Fits in the first line of an email without diagnosing the prospect | Usable with care | Awkward or hits a banned angle (fx) |

Volume numbers are only stated where research has them. Clay credit costs per action are **unknown**: measure them on a one-row test with `/calculate-costs` before scaling. treg prices are from sg Part C.

### Signal list

| # | Signal (observable event) | Mother intent | Type | Segments | Data source | Detection tool | Reason | Volume | Data | Story | Total | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| SG1 | Posted an HR or People leader role in the last 30 days (Head of HR, HR Manager, Head of People, HR and Admin Manager) | Hiring specific roles | Universal | S1 to S4 | LinkedIn Jobs public search (sg Part C); Jobberman, MyJobMag (sg Signal 2) | treg `crawl4ai.linkedin.search.jobs`, about $0.00045 per call, run 2026-11-07 (sg Part C). Clay "Find Jobs" as an alternative; Nigeria coverage untested | 3 | 3 | 5 | 4 | **15** | VERIFIED (reason INFERRED) |
| SG2 | Posted a payroll or HR operations role in the last 30 days (Payroll Officer or Associate, HR Ops, People Ops, Total Rewards) | Hiring specific roles | Universal | S1 to S4 | LinkedIn Jobs (sg Part C) | treg `crawl4ai.linkedin.search.jobs`, same build as SG1 with different keywords | 3 | 3 | 5 | 4 | **15** | VERIFIED (reason INFERRED) |
| SG3 | Hiring velocity: 3+ distinct open roles in 30 days, any function | Hypergrowth (hiring velocity) | Universal | S1, S2, S3 | LinkedIn Jobs; Jobberman (sg Signal 2) | treg `crawl4ai.linkedin.search.jobs`, broad queries grouped by company. Capped at 40 results per call, so many calls are needed (sg Part C) | 4 | 4 | 3 | 4 | **15** | VERIFIED (PARTIAL) |
| SG4 | Deskless hiring surge: 3+ posts in 30 days for driver, rider, warehouse, factory, store, field sales or nurse roles | Hypergrowth (hiring velocity), deskless keyword set | Universal (SG3 build with S2 keywords) | S2 | LinkedIn Jobs; Jobberman, MyJobMag | treg `crawl4ai.linkedin.search.jobs`; Jobberman and MyJobMag via the local `crawl4ai` skill (untested) | 3 | 3 | 3 | 5 | **14** | VERIFIED (PARTIAL) |
| SG5 | Headcount crossed 15 or 20 since last month's snapshot | Hypergrowth (headcount) | Universal | S1, S2, S3, S5 | LinkedIn company page employee count (sg Signal 1; co §15a) | treg `harvestapi.linkedin.company.profile` (used in co §15a, cv); Clay "Enrich Company". Monthly snapshot of a seed list | 5 | 2 | 2 | 4 | **13** | VERIFIED (PARTIAL) |
| SG6 | Funding round announced in the last 60 days | Companies fundraising | Niche-specific | S1 (S4 for large rounds) | Nairametrics monthly funding roundups, Africa: The Big Deal, Techpoint (sg Signal 3) | Local `crawl4ai` skill on roundup URLs, then Clay "Use AI" to pull company, round and date. Crunchbase via Clay as backup (coverage untested) | 2 | 2 | 4 | 4 | **12** | VERIFIED |
| SG7 | Nigerian company expanding to Ghana, Kenya or South Africa: news, or job posts in Accra, Nairobi or Johannesburg | Hiring offshore | Niche-specific | S1 | Launch Base Africa, Techpoint, TechAfricaNews; LinkedIn Jobs by location (sg Signal 5) | treg `crawl4ai.linkedin.search.jobs` with location set to the new market, joined to a Nigeria-HQ company list | 3 | 2 | 3 | 4 | **12** | VERIFIED (PARTIAL) |
| SG8 | New HR or People leader started in the last 90 days | New leadership | Universal | S1 to S4 | LinkedIn profile start dates; Techeconomy appointments page (sg Signal 4) | Clay "Find People" filtered on title and start date (untested for Nigeria) | 3 | 2 | 3 | 4 | **12** | VERIFIED (PARTIAL) |
| SG9 | Annual PAYE return window: employer returns due 31 Jan 2027 | Regulatory change (calendar) | Universal, overlay only | All | DLA Piper: employer files "by 31 January" (mk §1.4); LIRS deadline coverage (sg Signal 6) | No tool needed; it's a date rule in the sequencer. Optional `crawl4ai` watch on LIRS/NRS news for extensions (mk §1.4) | 4 | 5 | 5 | 4 | **18** | VERIFIED (COMPOUND) |
| SG10 | Pending rule change enacted: higher employer pension rate (PRA review) or new minimum wage | Regulatory change | Universal, overlay only | All | Nairametrics, PenCom releases, NLC statements (mk §2, §3.2) | Local `crawl4ai` watch on PenCom news and Nairametrics (untested) | 4 | 5 | 2 | 4 | **15** | PARKED until enacted; dates unknown (mk §9) |
| SG11 | Sector named in a regulator crackdown (e.g. PenCom/ICPC on electricity-sector employers; PenCom/NLC in Lagos from 1 Jun 2026) | Regulatory change (enforcement) | Niche-specific (per sector) | S2, S4 | Nairametrics, ThisDay, PenCom releases (sg Signal 7) | Local `crawl4ai` on news, then manual sector-to-list mapping | 4 | 2 | 2 | 2 | **10** | VERIFIED (COMPOUND), as a narrative overlay only |
| SG12 | Lookalike of named customers | Lookalike of customers | Universal | S1 to S4 | Seeds: Famasi, Heroshe, TSL, MAX, Busha, Risevest, Bamboo, Flutterwave, Oando (cu §2; cv) | Clay lookalike or company search (untested) | 2 | 4 | 3 | 2 | **11** | VERIFIED (COMPOUND). Static, no timing: use as the base list for SG5 and SG9 |
| SG13 | A PaidHR HR admin moved to a new employer | Champion / user migration | Universal | S1 to S4 | PaidHR's list of HR admins at customers (not in research) | Clay people enrichment or treg `harvestapi` profile lookups | 4 | 1 | 1 | 5 | **11** | PARKED until PaidHR shares the list. Volume unknown, scored 1. Reason **INFERRED** |
| SG14 | Business joined an SME formalisation or grant cohort (LSETF, iDICE) | Niche-specific play | Niche-specific | S5 | LSETF announcements; iDICE cohort lists (sg Signal 11) | Local `crawl4ai` on announcement pages | 3 | 1 | 2 | 3 | **9** | VERIFIED (PARTIAL) |
| SG15 | Retail or clinic chain added locations in a new Nigerian state | Niche-specific play (physical world) | Niche-specific | S2 | Google Places location counts (**INFERRED**; not in research). Multi-state PAYE filing by employee residence is also **INFERRED** (sg Signal 5) | Google Places API via Clay HTTP (untested) | 3 | 2 | 2 | 4 | **11** | PARKED: no source tested |

**Basis for the Reason scores:**
- SG3: "As headcount grows, the volume of calculations, deductions, and remittances becomes difficult to manage accurately" (sg Signal 2).
- SG5: "Most startups switch when they reach 10 to 15 employees" (sg Part A).
- SG9: statutory deadline (mk §1.4). The Dec to Jan buying window is **INFERRED**.
- SG1, SG2, SG6, SG8: the research explicitly says the link to a purchase is **INFERRED** (sg Signal 3, Signal 4, Part C).

### Killed signals

| Signal | Why killed | Source |
|---|---|---|
| Payroll errors or pension complaints on Glassdoor or X | No company-level examples found, and outreach built on it diagnoses the prospect, which is banned | sg Signal 9; fx banned angles; framework guardrails |
| "Advanced Excel for payroll" in job descriptions as a mother intent | No examples found; the link is **INFERRED**. Kept instead as a secondary enrichment on SG1 and SG2 (a Clay "Use AI" classifier on the job text) | sg Signal 8 |
| Technographics (detecting SeamlessHR, Bento or other payroll tools) | BuiltWith can't see backend payroll tools, and naming Bento is banned. Workday or SAP in job posts is used only as an exclusion filter | framework "Signals that usually don't work"; fx; sg Part C |
| E-invoicing enforcement for medium taxpayers (₦1bn to ₦5bn turnover) | Turnover isn't observable, and the link to payroll is **INFERRED** | mk §1.7 |
| CAC registrations or headcount from CAC | No public bulk or headcount access | sg Signal 1, Gaps |
| Website visitor de-anonymisation (RB2B) | Individual-level data is US-only | workflow-anatomy.md catalog |

### Universal vs niche-specific

Of 15 live or parked signals:
- **10 are universal:** SG1, SG2, SG3, SG4, SG5, SG8, SG9, SG10, SG12, SG13.
- **5 are niche-specific:** SG6, SG7, SG11, SG14, SG15.

**The compounding point:** SG1, SG2, SG3, SG4 and SG7 are one build, a treg LinkedIn job search. Only the keywords and location change. One Clay table can feed four segments, and the angle changes per segment, not the infrastructure.

### Segment x signal plays

What each signal looks like per segment. "-" = does not apply.

| Signal | S1 VC-backed 10 to 199 | S2 Deskless 20 to 199 | S3 Office 20 to 199 | S4 200+ | S5 3 to 19 |
|---|---|---|---|---|---|
| SG1 HR leader hire | First HR hire: route to "inheriting payroll from the founder" | HR Manager at a plant or depot: route to WhatsApp/USSD for site staff | HR Manager: route to the 2026 tax-law angle | HR Director or HRBP: route to tool consolidation | - |
| SG2 Payroll/HR ops hire | People Ops hire at a startup | Payroll officer at a multi-site business | Payroll or HR officer | Total rewards or payroll associate; check for an incumbent HRIS | - |
| SG3 Hiring velocity | Any 3+ roles | (use SG4) | Any 3+ roles | - | - |
| SG4 Deskless surge | - | Drivers, riders, warehouse, factory, store, nurses | - | Optional, same keywords | - |
| SG5 Headcount crossing | Crossing 15 | Crossing 20 | Crossing 20 | - | Crossing 10 |
| SG6 Funding | Primary niche signal | Debt rounds only (e.g. Drive45, ThriveAgric; sg Signal 3) | - | Large rounds (Moove, Jumia) | - |
| SG7 Expansion | Primary | - | - | Optional | - |
| SG8 New HR leader | Yes | Yes | Yes | Yes | - |
| SG9 31 Jan returns | Overlay | Overlay | Overlay | Overlay | Overlay |
| SG10 Rule change | Overlay when enacted | Overlay (pension for casual staff) | Overlay | Overlay | Overlay |
| SG11 Sector crackdown | - | Overlay for the named sector | - | Overlay for the named sector | - |
| SG12 Lookalike | Famasi, Heroshe, Busha, Risevest, Bamboo | TSL, MAX | - | Oando, Flutterwave | - |
| SG13 Champion moved | Yes | Yes | Yes | Yes | - |
| SG14 Cohort lists | - | - | - | - | Primary |
| SG15 New-state locations | - | Retail and clinic chains | - | - | - |

---

## Build first: top signals

Ranked on the four-test score, then on reach across the S1 and S2 priority segments, then on timing. This is a recommendation to validate with PaidHR.

1. **SG1 + SG2: Hiring HR, People or Payroll roles (one build).** It's the only company-level signal already pulled end to end: a live, cheap treg call returned named Nigerian employers in the last 30 days (sg Part C). It covers S1 to S4, and the role in the job post routes the persona and angle. Weakness: the buying reason is **INFERRED**. Run a small test before scaling, and add the Excel-in-job-description classifier as a secondary enrichment.
2. **SG3 + SG4: Hiring velocity, with general and deskless keyword sets.** Same build as #1, so there's almost no added infrastructure cost. It has the strongest sourced reason among the hiring signals: growing headcount makes payroll "difficult to manage accurately" (sg Signal 2). The deskless keyword set reaches S2, the core customer base, with the WhatsApp/USSD story (cu §2; co §15d).
3. **SG9: 31 January 2027 annual PAYE returns, as a timed overlay.** This isn't a lead source. It's the reason to reach out now, layered on lists from #1, #2 and SG12 lookalikes. It scores highest (18/20), it's time-boxed, and today is 2026-11-07, so build in November and send in December and January. Copy must not quote a monthly PAYE deadline, because sources conflict (fx banned angles; mk §1.4).
4. **SG5: Headcount crossing 15 or 20.** It has the strongest buying reason in the matrix, PaidHR's own switch point (sg Part A), but needs monthly snapshots before it produces deltas. Start the snapshots now on the accounts surfaced by #1, #2 and SG12, so the first crossings show up around December.

**Conditional #5: SG13 champion migration.** If PaidHR shares its list of HR admins, this is usually the highest-converting play (**INFERRED**), and it costs little to run.

---

## Matrix 3: Workflow tracker

Pre-filled with one row per validated or parked signal. Add the remaining framework columns (Campaign Status, Persona, Industry, Company Size, Enrichments 1 to 5, # Iteration, Changelog, Steps, Total Emails, Progress, Bounce) as campaigns launch.

| W # | Status | Workflow name | Mother intent | Segments | Channel | Launch date | Clay URL | Copy URL | Total leads |
|---|---|---|---|---|---|---|---|---|---|
| W1 | Planned | Hiring HR, People or Payroll roles (SG1 + SG2) | Hiring specific roles | S1 to S4 | | | | | |
| W2 | Planned | Hiring velocity, general and deskless (SG3 + SG4) | Hypergrowth (hiring velocity) | S1, S2, S3 | | | | | |
| W3 | Planned | 31 Jan PAYE returns overlay (SG9) | Regulatory change (calendar) | All | | | | | |
| W4 | Planned | Headcount crossing 15/20 (SG5) | Hypergrowth (headcount) | S1, S2, S3, S5 | | | | | |
| W5 | Planned | Recently funded startups (SG6) | Companies fundraising | S1 | | | | | |
| W6 | Planned | Expanding to Ghana, Kenya, SA (SG7) | Hiring offshore | S1 | | | | | |
| W7 | Planned | New HR leader, first 90 days (SG8) | New leadership | S1 to S4 | | | | | |
| W8 | Planned | Customer lookalikes (SG12) | Lookalike of customers | S1 to S4 | | | | | |
| W9 | Planned | SME cohort lists (SG14) | Niche-specific play | S5 | | | | | |
| W10 | Parked | Pension or minimum wage change (SG10) | Regulatory change | All | | | | | |
| W11 | Parked | Champion migration (SG13) | Champion / user migration | S1 to S4 | | | | | |
| W12 | Parked | Sector crackdown overlay (SG11) | Regulatory change (enforcement) | S2, S4 | | | | | |
| W13 | Parked | New-state locations (SG15) | Niche-specific play | S2 | | | | | |

---

## Open questions for PaidHR

1. Is the switch point (10 to 15 staff) or the Standard plan floor (20) the real minimum for outbound? This decides whether S5 exists at all (sg Part A; co §3).
2. Does PaidHR want outbound into 200+ accounts (S4), and can any enterprise customer be named?
3. Can PaidHR share a list of HR admins at customers (for SG13) and a list of current customers to suppress?
4. Kenya and Ghana: is outbound wanted there yet (parked segment)?
5. Win rate, deal size and sales cycle by segment: unknown (icp.md). These would replace the INFERRED priority scores.
6. Is the LSETF free cohort still open, and can it be offered in S5 copy (co §3)?

## Next steps
- Validate segment cut-offs and the top-four ranking with PaidHR.
- Enrich the research-sourced example companies (headcount, industry) to confirm their segment. This needs paid treg or Clay calls, so ask first.
- Run `/build-workflow-spec` on W1.
