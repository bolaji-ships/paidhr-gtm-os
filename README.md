# PaidHR GTM Context OS

A go-to-market workspace for [PaidHR](https://www.paidhr.com/), built to be used with [Claude Code](https://claude.com/claude-code). It keeps PaidHR's ICP, positioning, messaging, research and campaign work in one folder, so every piece of targeting or copy starts from the same sourced context.

PaidHR (formerly Pade HCM) is a Lagos-based HRMS for HR, payroll, statutory remittance, performance and employee financial wellness, for growing businesses in Nigeria, Kenya, South Africa and Ghana (source: `context/docs/research/company.md` §1, §4).

Built on [gtm-starter-kit](https://github.com/bolaji-ships/gtm-starter-kit).

## What's inside

| Folder | What it holds |
|---|---|
| `context/icp/` | Five-layer ICP, buyer personas, and the signal matrix (segments, personas, buying signals) |
| `context/positioning/` | Value proposition, positioning and competitor battlecard |
| `context/messaging/` | Core message and pillars; `facts.md` is the only source of names, numbers and claims allowed in copy |
| `context/brand-kit/` | Tone and key phrases from PaidHR's own copy |
| `context/docs/` | Case studies and raw research, with sources |
| `knowledge-base/playbooks/` | Signal matrix method, workflow anatomy, copy frameworks, copy rules and banned words, Clay guides |
| `output/campaigns/` | Campaign ideas and workflow specs, one folder per campaign |
| `.claude/skills/` | Claude Code skills for signal matrices, workflow specs, campaign copy, Clay builds and QA |
| `tools/` | Scripts and integrations (Rex for Clay, crawl4ai, agent-browser, treg wrapper) |
| `weekly-priorities/`, `work-log/` | One file per ISO week: what to focus on, and a timestamped log of every change |

`CLAUDE.md` explains how the folders fit together and the rules Claude follows here.

## How work flows

1. **Signal matrix** (`/signal-matrix`): segments, personas, and the buying signals worth building.
2. **Workflow spec** (`/build-workflow-spec`): one signal turned into targeting, exclusions, routing and an angle per cell.
3. **Copy** (`/campaign-copy`): emails written only from an approved spec and from `facts.md`.

First workflow: [New HR Leader, First 6 Months](output/campaigns/new-hr-leader-180-days/workflow-spec.md), for companies whose new HR or People leader joined within the last 180 days.

## Rules

- Every company fact cites a source.
- No invented numbers. Unknown figures are marked "unknown".
- No em dashes in copy.
- Nothing is sent or published without approval.
- Every change is logged in the week's work log.

## Status

Work in progress. Claims in `facts.md` are sourced from public research but not yet approved by PaidHR, and no campaign has been sent.

## Setup

1. Clone the repo and open it in Claude Code.
2. Secrets stay out of git: `.env`, `.treg/` and `clay-session.json` are ignored. See `.claude/skills/inbox-placement-test/.env.example` and `tools/rex/COOKIE_SETUP.md` for what each tool needs.
3. Optional: the Whisper transcriber is not included. Clone [whisper-transcriber-suite](https://github.com/Milomilo777/whisper-transcriber-suite) into `tools/whisper-transcriber-suite/` if you need it.

## Credits

Third-party code and content are listed in [THIRD-PARTY.md](THIRD-PARTY.md).
