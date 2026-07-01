# Claudedevsecopsagents — Project Overview

## What this repository is

This repository contains two things:

1. **`README.md` — the SDLC Agent Bench cheat sheet** (rendered as an HTML page). This is a reference document describing 18 specialist Claude Code subagents organized into three categories: Dev/SDLC (7), Security (8), and Docs (3). It explains how to invoke each agent, how to chain them, and how to run a full SDLC feature pipeline in a single prompt.

2. **`changereview1.1.md` — a security audit** of a local path-disclosure scan plan. This is an internal review document and should not be published (see the note in that file).

## The 18 agents at a glance

### Dev / SDLC agents

| Agent | Type | What it does |
|---|---|---|
| `tech-lead` | READ-ONLY | Plans multi-step work and produces a DELEGATION PLAN — does not execute |
| `requirements-analyst` | AUTHOR | Turns a vague idea into testable requirements, user stories, acceptance criteria |
| `implementer` | DOER | Writes feature code from a spec, runs build/tests to confirm |
| `debugger` | DOER | Investigates failures and applies minimal fixes |
| `test-engineer` | DOER | Writes and runs unit, integration, and edge-case tests |
| `code-reviewer` | READ-ONLY | Reviews a diff for correctness and quality — does not edit code |
| `devops-engineer` | DOER | CI/CD pipelines, Dockerfiles, release config, deploy scripts |

### Security agents

| Agent | Type | What it does |
|---|---|---|
| `security-architect` | ADVISORY | Secure-by-design controls, security ADRs, architecture review |
| `threat-modeler` | ADVISORY | STRIDE/PASTA analysis, attack trees, threat tables |
| `iam-engineer` | AUTHOR | AuthN/authZ design (OIDC, RBAC, ABAC, passkeys, zero-trust) |
| `cloud-security-engineer` | DOER | AWS/Azure/GCP config review, K8s hardening, Terraform security |
| `detection-engineer` | DOER | SIEM analytics (KQL, Sigma), threat hunting, MITRE ATT&CK coverage |
| `incident-responder` | DOER | Triage, containment, eradication, recovery, post-incident review |
| `osint-redteamer` | DOER | Passive OSINT on authorized targets — recon, attack surface |
| `ad-redteamer` | DOER | Authorized AD + Entra ID pentest (BloodHound, Kerberoasting, lateral movement) |

### Docs agents

| Agent | Type | What it does |
|---|---|---|
| `readme-specialist` | AUTHOR | Landing-page READMEs with badges, quickstart, diagrams |
| `tech-writer` | AUTHOR | Setup/usage guides, API reference, ADRs, code comments |
| `docs-maintainer` | DOER | Keeps existing docs accurate as code changes; writes changelogs |

## Agent types explained

- **DOER** — writes code, runs commands, makes changes to the codebase.
- **READ-ONLY** — inspects and reports findings but does not edit anything.
- **AUTHOR** — writes documentation or advisory content; no code or command execution.
- **ADVISORY** — provides recommendations and analysis; no code or command execution.

## How agents are invoked

You do not use a special command syntax. You write plain English in a Claude Code conversation and either:
1. **Let Claude auto-route** — describe the task with a clear verb and Claude picks the matching agent.
2. **Name the agent explicitly** — say "use the `implementer` to build X" for certainty.
3. **Chain agents in one prompt** — list the sequence and Claude executes each step in order.
4. **Plan first with `tech-lead`** — for multi-specialist work, start with a DELEGATION PLAN.

See `docs/invocation-guide.md` for detailed examples and patterns.

## The golden rule

Match the **verb** to the **lane**:
- **Plan** → `tech-lead`
- **Define** → `requirements-analyst`
- **Build** → `implementer`
- **Fix** → `debugger`
- **Test** → `test-engineer`
- **Review** → `code-reviewer`
- **Document** → `tech-writer` or `docs-maintainer`
- **Secure** → `security-architect` or `threat-modeler`
- **Detect** → `detection-engineer`
- **Respond** → `incident-responder`
