# GBA Blockchain Maturity Model (BMM) Plugin

A Claude Code plugin that acts as a blockchain maturity readiness consultant, helping you assess your solution against the [Government Blockchain Association's Blockchain Maturity Model](https://www.gbaglobal.org/).

## What it does

Walks you through a structured 6-phase consultation:

1. **Context** — Understands your solution, domain, stakeholder role, and goal
2. **Evidence inventory** — Maps your existing artifacts to BMM level requirements
3. **Integrity check** — Tests whether the solution meets the bedrock principles of decentralization and distribution
4. **Element walkthrough** — Scores each of the 11 elements, explains evidence standards, and gives actionable gap-closing recommendations
5. **Readiness assessment** — Produces a maturity scorecard, overall rating, top risks, and next steps
6. **Formal assessment prep** — Walks through BAP engagement, team composition rules, conflict requirements, and a pre-assessment checklist

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and working (`claude` command runs in your terminal)

## Install

Clone the repo from GitHub:

```sh
git clone https://github.com/blockchain-working-group/gba-bmm-skill.git
```

Then choose one of the install methods below.

### Option A: Global slash command (recommended)

Makes `/gba-bmm` available in every Claude Code session, across all projects:

```sh
mkdir -p ~/.claude/commands
cp gba-bmm-skill/gba-bmm.md ~/.claude/commands/gba-bmm.md
```

### Option B: Project-level slash command

Makes `/gba-bmm` available only when working inside a specific project:

```sh
cd your-project
mkdir -p .claude/commands
cp /path/to/gba-bmm-skill/gba-bmm.md .claude/commands/gba-bmm.md
```

### Option C: Plugin mode

Loads the full plugin structure for a single session:

```sh
claude --plugin-dir ./gba-bmm-skill
```

The skill will be available as `/gba-bmm:bmm-readiness` for that session.

### Verify installation

Launch Claude Code and type:

```
/gba-bmm
```

If the skill loads, it will ask about your blockchain solution.
If nothing happens, verify the file is in place:

```sh
ls ~/.claude/commands/gba-bmm.md
```

### Update

Pull the latest version and re-copy:

```sh
cd gba-bmm-skill
git pull
cp gba-bmm.md ~/.claude/commands/gba-bmm.md
```

### Uninstall

```sh
# Global
rm ~/.claude/commands/gba-bmm.md

# Project-level
rm .claude/commands/gba-bmm.md
```

## Use

Invoke the skill and describe your solution or goal:

```
/gba-bmm we have a supply chain tracking solution on Hyperledger Fabric preparing for a GBA assessment
```

Or invoke it without arguments and the skill will walk you through the intake questions:

```
/gba-bmm
```

The consultation follows 6 phases:
context, evidence inventory, integrity check, element walkthrough, readiness scorecard, and formal assessment prep.

## Plugin Structure

```
gba-bmm-skill/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── skills/
│   └── bmm-readiness/
│       └── SKILL.md             # Main skill prompt
├── gba-bmm.md                   # Legacy slash command format
└── README.md
```

## Who this is for

- **Solution providers** preparing for a GBA BMM assessment
- **Investors** evaluating blockchain solution maturity
- **Acquisition professionals** benchmarking proposals against a common standard
- **Government program offices** conducting internal readiness reviews

## The 11 Elements

| Element | What it assesses |
|---------|-----------------|
| Distribution | Node hosting concentration risk |
| Governance | Management of assets, nodes, protocols, smart contracts |
| Identity Management | Access controls, KYC/AML, anonymity (domain-sensitive) |
| Interoperability | Cross-chain and legacy system integration |
| Performance | Throughput, latency, finality, cost |
| Privacy | PII protection, encryption, GDPR compliance |
| Reliability | Fork resolution, error handling, fraud controls |
| Resilience | Fault tolerance, continuity of operations |
| Security | End-to-end controls across the full stack |
| Infrastructure Sustainability | Lifecycle resource availability |
| Synchronization | Consensus mechanisms, finality |

## Important

This plugin is a preparation coach, not a formal assessment.
Only GBA Authorized Assessment Partners (BAPs) conduct official BMM assessments.
See the [GBA Blockchain Maturity Model](https://gbaglobal.org/blockchain-maturity-model/) for the formal program.

## Source

Based on the [GBA Blockchain Maturity Model](https://gbaglobal.org/blockchain-maturity-model/) Overview document (January 14, 2023, Approved).
The BMM is developed and maintained by the Government Blockchain Association.
