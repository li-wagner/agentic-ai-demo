# Agentic AI Demo: Inactive Device Investigation

A demo for the IT Ops agentic AI training. Two AI agents investigate
inactive devices across four data sources and propose actions. A human
reviews and decides.

> ⚠️ All data in this repository is fictional. Northwind Corp and its people
> are invented for training purposes. This is a personal sandbox, not a
> company system.

## The agents

| Agent | Model | Role | Access |
|---|---|---|---|
| device-investigator | Sonnet | Cross-references data, proposes actions | Reads data, writes the plan |
| action-reviewer | Opus | Independently checks the plan | Read-only |

## Guardrails

- **Instructions:** CLAUDE.md and the agent files define what each agent may do
- **Deny rules:** `.claude/settings.json` blocks file edits to data and instructions, and common shell writes. This is a convention and a speed bump, not a security boundary
- **CI check:** a pull request that changes `data/`, `CLAUDE.md` or `.claude/` fails. This is the enforcement
- **Branch protection:** nothing reaches `main` without a pull request
- **Human in the loop:** agents propose, a human decides and acts

## Key takeaway

The agents find it. A human decides. A human still clicks wipe.
