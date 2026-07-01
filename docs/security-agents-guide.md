# Security Agents Guide

This guide covers the eight security agents in detail: when to use each one, the distinction between defensive and offensive agents, and how to integrate them into an SDLC workflow.

## Defensive vs offensive

The eight security agents divide into two groups:

**Defensive (first six):** Protect your system. Use at any time during the SDLC.

| Agent | When in the SDLC | Primary output |
|---|---|---|
| `security-architect` | Design, review | Security controls, ADRs, trade-off analysis |
| `threat-modeler` | Design | STRIDE/PASTA report, attack trees, Mermaid diagrams |
| `iam-engineer` | Design, implementation | AuthN/authZ design documents, policy configs |
| `cloud-security-engineer` | Implementation, review | Hardened configs, scan findings, remediation |
| `detection-engineer` | Post-implementation | SIEM rules (KQL, Sigma), hunting queries |
| `incident-responder` | During/after an incident | Triage notes, containment steps, post-incident report |

**Offensive (last two):** Test your system's defenses. Use only in authorized, scoped engagements.

| Agent | Scope | Primary output |
|---|---|---|
| `osint-redteamer` | Passive recon only | Attack surface map, exposed asset report |
| `ad-redteamer` | Active AD/Entra ID attacks (authorized) | Attack path report, lateral movement findings |

---

## Shift security left

The most cost-effective use of the security agents is at **design time** — before code is written.

```
Typical (costly):
  Design → Build → Test → [Security finds a design flaw] → Redesign → Rebuild

With security agents (cheaper):
  [security-architect + threat-modeler review design] → Build → [code-reviewer + security-architect review code] → Ship
```

Use `security-architect` and `threat-modeler` before the `implementer` runs. Use them again alongside `code-reviewer` in the review phase.

---

## `security-architect` — Secure-by-design

**Role:** Choose the right security controls for a design and write the rationale.  
**Type:** ADVISORY — gives recommendations, does not write code.

**Good prompts:**
```
Is this API authentication design sound? The plan is to use JWTs with 15-minute
expiry and refresh tokens stored in httpOnly cookies.

What controls does this payment processing service need? Write a security ADR
documenting the decisions.

Review this architecture for privilege escalation paths.
```

**Output:** Markdown advisory, security ADR, annotated architecture notes.

---

## `threat-modeler` — What could go wrong

**Role:** Systematic attack analysis using STRIDE or PASTA frameworks.  
**Type:** ADVISORY — produces analysis documents.

**Good prompts:**
```
Threat model this login flow design. Use STRIDE and produce a threat table
with risk ratings.

What are the attack paths if an attacker compromises the background job worker?

Build a threat report for the file upload feature including a data flow diagram.
```

**Output:** Threat table (STRIDE categories, risk ratings), Mermaid data-flow diagram, attack trees, abuse cases.

---

## `iam-engineer` — Identity and access

**Role:** Design authentication and authorization systems.  
**Type:** AUTHOR — writes design documents and policy configurations.

**Good prompts:**
```
Design the login system for a multi-tenant SaaS. Requirements: OIDC, MFA,
session management. Produce the auth flow document.

Is this OAuth2 implicit flow correct? Should we use PKCE?

Set up the RBAC roles for this admin API. Users are: viewer, editor, admin.
Write the role definitions.
```

**Output:** Auth flow design, RBAC/ABAC definitions, IAM policy documents, zero-trust architecture recommendations.

---

## `cloud-security-engineer` — Cloud and container posture

**Role:** Review and harden cloud configurations.  
**Type:** DOER — may run read-only scanners and write hardened configurations.

**Good prompts:**
```
Review this Terraform IAM policy for over-provisioned permissions.

Harden this Kubernetes deployment manifest to CIS benchmark level 2.

Is this S3 bucket configuration safe? Check for public access, encryption,
and logging.
```

**Output:** Hardened config files, review findings report, CIS benchmark compliance notes.

---

## `detection-engineer` — Detections and hunting

**Role:** Write detection-as-code and threat-hunting queries.  
**Type:** DOER — writes detection rules and queries.

**Good prompts:**
```
Write a Sigma rule to detect LSASS memory dump attempts (T1003.001).

Write a KQL query to hunt for suspicious OAuth application consent in Entra ID.

What's our MITRE ATT&CK coverage gap for the Initial Access tactic?
```

**Output:** Sigma rules, KQL/SPL detection queries, ATT&CK coverage map, false-positive reduction guidance.

---

## `incident-responder` — During and after a breach

**Role:** Guide through incident response using NIST 800-61 / PICERL phases.  
**Type:** DOER — analyzes locally and gives runbook guidance for live actions.

**Good prompts:**
```
I received an alert: a service account made 50 Entra ID role assignments in
2 minutes. Help me triage this. Is it a breach?

Help me scope the blast radius of this compromised API key.

Write the incident timeline and lessons-learned document for this breach.
```

**Output:** Triage analysis, containment runbook, eradication steps, recovery checklist, post-incident review.

---

## `osint-redteamer` — Recon (authorized only)

**Role:** Passive open-source intelligence on an authorized target.  
**Type:** DOER — uses OSINT techniques (no active exploitation).

**Authorization required:** Always include the explicit authorization statement and scope in the prompt.

**Good prompts:**
```
We have written authorization for a pentest of example.com (scope: *.example.com).
Map the external attack surface: subdomains, exposed services, leaked credentials.

Recon this domain for our engagement. Authorization: signed pentest contract
for acmecorp.com, valid June 20–30.
```

**Output:** Attack surface map, exposed asset inventory, leaked credential indicators, pretext research.

---

## `ad-redteamer` — Active Directory / Entra ID (authorized only)

**Role:** Active Directory and Entra ID penetration testing.  
**Type:** DOER — performs active attacks (within authorized scope).

**Authorization required.** This agent can analyze BloodHound exports, identify Kerberoasting/AS-REP roasting targets, map lateral movement paths, and guide privilege escalation to Domain Admin or Global Admin.

**Good prompts:**
```
We have authorization for a full red team on customer-corp.com. Analyze this
BloodHound export and find the shortest path to Domain Admin.

We have Entra ID access as a regular user. Find privilege escalation paths
to Global Admin. Authorization: signed pentest SoW for Contoso, June 2026.

Map on-prem to cloud pivot paths from this compromised workstation.
```

**Output:** Attack path report, exploitation sequence, privilege escalation steps, detection evasion notes.

> **Note:** The `ad-redteamer` stays passive and scoped until you confirm authorization. It will not proceed without an explicit scope statement.

---

## Integrating security agents into a PR workflow

A well-integrated security workflow uses agents at three points:

```
1. BEFORE CODING — design review
   tech-lead → security-architect + threat-modeler
   (Design must pass before implementer starts)

2. DURING IMPLEMENTATION — as needed
   cloud-security-engineer → review Terraform / K8s as it's written
   iam-engineer → validate auth implementation matches the design

3. AFTER CODING — review gate
   code-reviewer + security-architect
   (Both must pass before merge)

4. AFTER DEPLOYMENT — ongoing
   detection-engineer → write detections for new attack surface
   docs-maintainer → update threat model docs
```

The offensive agents (`osint-redteamer`, `ad-redteamer`) run as separate engagements outside the normal PR workflow.
