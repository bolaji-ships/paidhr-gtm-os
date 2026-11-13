# PaidHR GTM Context OS

## Company
PaidHR (formerly Pade HCM), Lagos: one HRMS for HR, payroll, statutory remittance, performance and employee financial wellness, for growing businesses in Nigeria, Kenya, South Africa and Ghana. Sources: `context/docs/research/company.md` §1, §4.

## How this folder works
- `.claude/skills/`: reusable Claude skills for this GTM team. Read when a task matches a skill.
- `context/icp/`: ideal customer profiles and buyer personas. Read before any targeting, list building or copy.
  - `icp.md` (five-layer ICP, not-a-fit), `personas.md` (champion, economic buyer, influencer)
- `context/positioning/`: market category, differentiators, competitors. Read before any messaging or competitive work.
  - `value-proposition.md`, `positioning.md`, `competitors.md` (battlecard)
- `context/messaging/`: value props, proof points, objection handling. Read before writing any copy.
  - `messaging.md` (core message, pillars, persona angles), `facts.md` (usable proof, banned claims, sender: check before every send)
- `context/brand-kit/`: voice, tone, visual guidelines, logos. Read before producing any customer-facing asset.
  - `brand.md` (tone and key phrases from PaidHR's own copy)
- `context/docs/`: `case-studies.md` (every customer story found). Read before using social proof.
- `context/docs/research/`: raw research with sources. Read when you need to verify or cite a company fact.
- `inspiration/`: swipe file of examples worth learning from (ads, emails, posts, pages), with a note on why each works. Read before creating new copy or creative.
- `knowledge-base/playbooks/`: repeatable GTM processes and workflow specs. Read before running or designing a workflow.
- `knowledge-base/learnings/`: what worked, what didn't, and why. Read before planning a new campaign or test.
- `meetings/`: meeting notes and call transcripts. Read when you need context on decisions or customer conversations.
- `output/campaigns/`: finished campaign assets and copy, one folder per campaign. Read to reuse or iterate on past work.
- `output/outbound/`: outbound sequences, cold emails and LinkedIn messages. Read before writing or iterating on outbound copy.
- `output/social/`: organic social posts and content calendars. Read before drafting social content.
- `output/paid-ads/`: ad copy, creative briefs and campaign setups. Read before writing or iterating on paid ads.
- `tools/`: scripts, integrations and tool configs. Read before automating or connecting a system.
- `weekly-priorities/`: one file per ISO week (`YYYY-Www.md`). Read at the start of every session.
- `work-log/`: one file per ISO week, timestamped entries of every change. Read to see recent work; append after every change.

## Rules
1. Cite a source (URL or file path) for every company fact.
2. Never invent numbers. If a figure is unknown, write "unknown" and flag it.
3. No em dashes in any copy.
4. Ask before sending or publishing anything.
5. Log every change in this week's work log (`work-log/YYYY-Www.md`) with a timestamp.

## Tools
- **treg.to** (tool catalog, pay per call): run only via `tools/treg <command>`. Binary and login live in `.treg/` (gitignored); never use the global `treg` or `~/.treg`. Usage: `.claude/skills/treg/SKILL.md`. Ask before paid calls.
