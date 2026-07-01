# Invocation Guide

This guide translates the cheat sheet in `README.md` into a practical reference for writing prompts that invoke the right agent.

## The four invocation patterns

### Pattern 1 — Auto-route (let Claude pick)

Write a clear task description with a strong verb. Claude routes to the matching agent automatically.

```
Write unit tests for the new payments module and run them.
```
→ Routes to `test-engineer` automatically.

```
This function throws a TypeError on null input. Fix it.
```
→ Routes to `debugger` automatically.

**When to use:** Single-specialist tasks with a clear verb. Fastest to write.

---

### Pattern 2 — Explicit naming (name the agent)

Name the agent when you want to be sure — especially useful for security agents (where an "advisory" vs "doer" distinction matters).

```
Use the code-reviewer to look at my changes to auth.ts and report findings.
```

```
Have the security-architect review this login flow design and write a security ADR.
```

**When to use:** When you need a specific agent type (especially READ-ONLY vs DOER), or when auto-routing might pick the wrong specialist.

---

### Pattern 3 — Plan first (`tech-lead`)

For tasks that span more than one specialist, start with `tech-lead` to produce a delegation plan. Then run the plan.

```
Have tech-lead plan how to add OAuth login to this app, then run the plan.
```

`tech-lead` returns an ordered DELEGATION PLAN listing who does what and in what order. Your main conversation then executes each step.

**When to use:** Any feature that needs design + implementation + testing + documentation = multiple specialists.

---

### Pattern 4 — Chain agents in one prompt

List the sequence of agents and what each should do. Claude executes them in order.

```
requirements-analyst → define the acceptance criteria for password reset,
implementer → build the reset flow,
test-engineer → write tests for it,
code-reviewer + security-architect → review in parallel,
docs-maintainer → update the docs.
```

**When to use:** Known workflows where you already know the full pipeline. More explicit than Pattern 3 but skips the planning step.

---

## Sequential vs parallel

- **Sequential (dependent):** One agent's output feeds the next. Use "first... then..." or list them in order.
- **Parallel (independent):** Agents working on different things at the same time. Ask for both in the same request without sequencing language.

```
# Sequential — implementer output is needed before code-reviewer can work
Have the implementer build X, then have the code-reviewer check it.

# Parallel — threat-modeler and readme-specialist work on different artifacts
Have threat-modeler model this design and readme-specialist update the README.
```

---

## The red team agents — authorization required

`osint-redteamer` and `ad-redteamer` are offensive security agents. They operate only inside an explicitly authorized and scoped engagement (pentest, CTF, or lab environment). They stay passive until you confirm scope.

Always include scope and authorization in the prompt:

```
We are doing an authorized pentest for Acme Corp. Scope: acme-corp.com and
all subdomains. Timeframe: June 20–27. Use osint-redteamer to map the
external attack surface.
```

Do not invoke these agents without confirming authorization in the prompt.

---

## Common task → agent mapping

| Task | Agent | Pattern |
|---|---|---|
| Break a feature into steps | `tech-lead` | Plan first |
| Define what to build | `requirements-analyst` | Direct or chained |
| Build a feature | `implementer` | Direct |
| Fix a failing test | `debugger` | Direct |
| Add test coverage | `test-engineer` | Direct |
| Review a PR diff | `code-reviewer` | Direct (READ-ONLY) |
| Write a Dockerfile | `devops-engineer` | Direct |
| Set up GitHub Actions CI | `devops-engineer` | Direct |
| Review auth design | `security-architect` | Explicit naming |
| STRIDE threat model | `threat-modeler` | Explicit naming |
| Design RBAC roles | `iam-engineer` | Explicit naming |
| Review Terraform | `cloud-security-engineer` | Explicit naming |
| Write Sigma rule | `detection-engineer` | Direct |
| Investigate a breach | `incident-responder` | Direct |
| Map attack surface (authorized) | `osint-redteamer` | Explicit naming + scope |
| BloodHound path analysis (authorized) | `ad-redteamer` | Explicit naming + scope |
| Write a README | `readme-specialist` | Direct |
| Write setup guide / ADR | `tech-writer` | Direct |
| Update docs after a change | `docs-maintainer` | Direct |

---

## Full SDLC pipeline example

This prompt drives a complete feature from idea to documented code:

```
I want to add passwordless email login. Have tech-lead plan it, then run the plan:
requirements-analyst to define acceptance criteria, iam-engineer to design the auth
flow, implementer to build it, test-engineer for tests, code-reviewer +
security-architect to review in parallel, and docs-maintainer to update the docs.
```

**Why this works:**
1. `tech-lead` produces the DELEGATION PLAN (sequencing, who does what).
2. The main conversation executes each step in order.
3. `code-reviewer` and `security-architect` run in parallel on the finished code.
4. `docs-maintainer` closes the loop by updating the written record.

The security agents (`iam-engineer`, `security-architect`) run at design time and review time — catching issues before and after implementation, not only after.
