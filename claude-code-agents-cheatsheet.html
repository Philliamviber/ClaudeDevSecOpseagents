<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Claude Code Agent Bench · SDLC Cheat Sheet</title>
<style>
  :root{
    --bg:#0d1117; --panel:#161b22; --panel2:#1c2330; --line:#2d3440;
    --ink:#e6edf3; --muted:#9aa7b4; --faint:#6e7b8a;
    --sec:#f97583;   /* security  */
    --dev:#58a6ff;   /* dev/sdlc  */
    --doc:#56d364;   /* docs      */
    --plan:#d2a8ff;  /* planning  */
    --accent:#ffb454;
    --code:#0a0e14;
    --radius:14px;
    font-synthesis:none;
  }
  *{box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{
    margin:0; background:radial-gradient(1200px 800px at 80% -10%,#1b2433 0,var(--bg) 55%);
    color:var(--ink);
    font:15px/1.55 -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
    padding-bottom:80px;
  }
  a{color:var(--dev);text-decoration:none}
  code,kbd{font-family:"SFMono-Regular",ui-monospace,"Cascadia Code","Consolas",monospace}
  .wrap{max-width:1180px;margin:0 auto;padding:0 22px}

  /* ---------- header ---------- */
  header.hero{
    padding:54px 22px 38px;
    border-bottom:1px solid var(--line);
    background:linear-gradient(180deg,rgba(210,168,255,.08),transparent);
  }
  .hero .wrap{max-width:1180px;margin:0 auto;padding:0}
  .eyebrow{letter-spacing:.18em;text-transform:uppercase;font-size:12px;color:var(--accent);font-weight:700}
  h1{margin:.25em 0 .15em;font-size:38px;line-height:1.1;letter-spacing:-.02em}
  .sub{color:var(--muted);font-size:17px;max-width:760px}
  .pills{margin-top:20px;display:flex;flex-wrap:wrap;gap:10px}
  .pill{font-size:13px;padding:6px 13px;border-radius:999px;border:1px solid var(--line);background:var(--panel);color:var(--muted)}
  .pill b{color:var(--ink)}
  .legend{display:inline-flex;align-items:center;gap:7px}
  .dot{width:10px;height:10px;border-radius:50%}

  /* ---------- nav ---------- */
  nav.toc{position:sticky;top:0;z-index:20;background:rgba(13,17,23,.85);backdrop-filter:blur(8px);
    border-bottom:1px solid var(--line)}
  nav.toc .wrap{display:flex;gap:6px;flex-wrap:wrap;padding:10px 22px}
  nav.toc a{font-size:13px;color:var(--muted);padding:6px 12px;border-radius:8px}
  nav.toc a:hover{background:var(--panel2);color:var(--ink)}

  section{padding:46px 0 8px}
  h2{font-size:25px;margin:0 0 6px;letter-spacing:-.01em;display:flex;align-items:center;gap:11px}
  h2 .num{font-size:13px;color:var(--faint);font-weight:600;border:1px solid var(--line);border-radius:7px;padding:2px 8px}
  .lead{color:var(--muted);max-width:780px;margin:0 0 26px}

  /* ---------- category band ---------- */
  .catband{display:flex;align-items:center;gap:10px;margin:34px 0 16px;font-weight:700;font-size:15px}
  .catband .bar{width:4px;height:20px;border-radius:3px}
  .catband .count{font-weight:500;color:var(--faint);font-size:13px}

  /* ---------- agent grid ---------- */
  .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(330px,1fr));gap:16px}
  .card{
    background:linear-gradient(180deg,var(--panel),var(--panel2));
    border:1px solid var(--line);border-radius:var(--radius);padding:18px 18px 16px;
    position:relative;overflow:hidden;transition:transform .12s ease,border-color .12s ease;
  }
  .card:hover{transform:translateY(-2px);border-color:var(--cardc,#3a4452)}
  .card::before{content:"";position:absolute;left:0;top:0;bottom:0;width:4px;background:var(--cardc,#3a4452)}
  .card h3{margin:0 0 2px;font-size:15px;font-family:"SFMono-Regular",ui-monospace,monospace;color:var(--cardc,#fff)}
  .card .role{font-size:11px;text-transform:uppercase;letter-spacing:.08em;color:var(--faint);font-weight:700;margin-bottom:9px}
  .card p{margin:0 0 10px;font-size:13.5px;color:var(--ink)}
  .card .trig{font-size:12.5px;color:var(--muted);border-top:1px dashed var(--line);padding-top:9px}
  .card .trig b{color:var(--ink);font-weight:600}
  .badge{display:inline-block;font-size:10.5px;font-weight:700;letter-spacing:.04em;padding:2px 7px;border-radius:5px;margin-left:6px;vertical-align:middle}
  .b-doer{background:rgba(86,211,100,.15);color:#56d364;border:1px solid rgba(86,211,100,.3)}
  .b-read{background:rgba(88,166,255,.15);color:#58a6ff;border:1px solid rgba(88,166,255,.3)}
  .b-author{background:rgba(255,180,84,.15);color:#ffb454;border:1px solid rgba(255,180,84,.3)}

  /* ---------- syntax / code blocks ---------- */
  pre{background:var(--code);border:1px solid var(--line);border-radius:12px;padding:16px 18px;overflow:auto;
    font-size:13px;line-height:1.6;margin:0 0 16px}
  pre code{color:#c9d6e2}
  .tok-c{color:#56d364}      /* comment */
  .tok-a{color:#d2a8ff;font-weight:600}  /* agent name */
  .tok-k{color:#ffb454}      /* keyword */
  .tok-s{color:#79c0ff}      /* string */
  .inline{background:var(--panel2);border:1px solid var(--line);border-radius:5px;padding:1px 6px;font-size:12.5px;color:var(--accent)}

  .two{display:grid;grid-template-columns:1fr 1fr;gap:18px}
  @media(max-width:820px){.two{grid-template-columns:1fr}}
  .note{background:var(--panel);border:1px solid var(--line);border-left:3px solid var(--accent);
    border-radius:10px;padding:14px 16px;font-size:13.5px;color:var(--muted)}
  .note b{color:var(--ink)}

  /* ---------- workflow / pipeline ---------- */
  .flow{display:flex;flex-direction:column;gap:0;margin:8px 0 6px}
  .step{display:flex;gap:14px;align-items:flex-start;position:relative;padding:0 0 22px 0}
  .step:last-child{padding-bottom:0}
  .step .rail{display:flex;flex-direction:column;align-items:center}
  .step .node{width:30px;height:30px;border-radius:50%;display:grid;place-items:center;font-weight:700;font-size:13px;
    flex:none;background:var(--panel2);border:2px solid var(--stepc,#3a4452);color:var(--stepc,#fff)}
  .step .line{width:2px;flex:1;background:var(--line);margin:3px 0}
  .step:last-child .line{display:none}
  .step .body{padding-top:2px}
  .step .body .ph{font-size:11px;text-transform:uppercase;letter-spacing:.08em;color:var(--faint);font-weight:700}
  .step .body .ag{font-family:"SFMono-Regular",ui-monospace,monospace;color:var(--stepc,#fff);font-weight:600;font-size:14px}
  .step .body p{margin:3px 0 0;font-size:13px;color:var(--muted)}

  /* ---------- cheat sheet table ---------- */
  .tablewrap{border:1px solid var(--line);border-radius:12px;overflow:hidden}
  table{border-collapse:collapse;width:100%;font-size:13px}
  th,td{text-align:left;padding:10px 13px;border-bottom:1px solid var(--line);vertical-align:top}
  thead th{background:var(--panel2);color:var(--muted);font-size:11px;text-transform:uppercase;letter-spacing:.07em;position:sticky;top:0}
  tbody tr:hover{background:rgba(88,166,255,.05)}
  td.ag{font-family:"SFMono-Regular",ui-monospace,monospace;white-space:nowrap;font-weight:600}
  td.say{color:var(--muted);font-style:italic}
  .tag{font-size:10.5px;font-weight:700;padding:2px 7px;border-radius:5px;white-space:nowrap}

  footer{margin-top:50px;border-top:1px solid var(--line);padding:24px 0;color:var(--faint);font-size:12.5px;text-align:center}
  .kbd{background:var(--panel2);border:1px solid var(--line);border-bottom-width:2px;border-radius:5px;padding:1px 6px;font-size:12px}
  .anchor{position:relative;top:-58px}
</style>
</head>
<body>

<header class="hero">
  <div class="wrap">
    <div class="eyebrow">Claude Code · Subagent Playbook</div>
    <h1>Running an SDLC with a Bench of Agents</h1>
    <p class="sub">You have <b>16 specialist subagents</b> on call. This sheet shows what each one is for, the exact words that summon it, and how to chain several inside a single prompt so one request drives a whole feature from idea → ship.</p>
    <div class="pills">
      <span class="pill"><span class="legend"><span class="dot" style="background:var(--plan)"></span> <b>Planning</b></span></span>
      <span class="pill"><span class="legend"><span class="dot" style="background:var(--dev)"></span> <b>Dev / SDLC</b> · 7</span></span>
      <span class="pill"><span class="legend"><span class="dot" style="background:var(--sec)"></span> <b>Security</b> · 6</span></span>
      <span class="pill"><span class="legend"><span class="dot" style="background:var(--doc)"></span> <b>Docs</b> · 3</span></span>
    </div>
  </div>
</header>

<nav class="toc">
  <div class="wrap">
    <a href="#how">How it works</a>
    <a href="#dev">Dev / SDLC agents</a>
    <a href="#sec">Security agents</a>
    <a href="#docs">Docs agents</a>
    <a href="#syntax">Invocation syntax</a>
    <a href="#workflow">Full SDLC flow</a>
    <a href="#cheat">Cheat sheet</a>
    <a href="#rules">Rules of thumb</a>
  </div>
</nav>

<div class="wrap">

<!-- ============ HOW IT WORKS ============ -->
<section id="how"><span class="anchor"></span>
  <h2><span class="num">01</span> The mental model</h2>
  <p class="lead">You don't manage 16 agents by hand. You talk to your <b>main conversation</b>, and it dispatches work to specialists. Two ways that happens:</p>
  <div class="two">
    <div class="card" style="--cardc:var(--plan)">
      <h3>tech-lead = the planner</h3>
      <div class="role">Delegation model</div>
      <p>For anything needing more than one specialist, <code class="inline">tech-lead</code> produces an ordered <b>DELEGATION PLAN</b> — who does what, in what order. It plans only; it does <b>not</b> execute. Your main conversation then runs the plan, handing each step to the right agent.</p>
      <p class="trig"><b>Reach for it first</b> on "build feature X", "break this down", "who should do what?"</p>
    </div>
    <div class="card" style="--cardc:var(--dev)">
      <h3>Direct dispatch</h3>
      <div class="role">Auto / explicit</div>
      <p>For single-specialist work, just describe the task — Claude auto-routes to the matching agent — or name one explicitly to be sure. Multiple independent agents can even run in <b>parallel</b> within one turn.</p>
      <p class="trig"><b>Two kinds of agents:</b> <span class="badge b-doer">DOER</span> writes code / runs commands · <span class="badge b-read">READ-ONLY</span> reports findings · <span class="badge b-author">AUTHOR</span> writes docs only.</p>
    </div>
  </div>
  <div class="note" style="margin-top:18px">
    <b>The golden rule of multi-agent SDLC:</b> match the <i>verb</i> to the <i>lane</i>. "Plan" → tech-lead. "Define" → requirements-analyst. "Build" → implementer. "Why's it broken?" → debugger. "Is it good?" → code-reviewer. "Test it" → test-engineer. Naming the right verb is how you get the right agent without thinking about it.
  </div>
</section>

<!-- ============ DEV / SDLC ============ -->
<section id="dev"><span class="anchor"></span>
  <h2><span class="num">02</span> Dev &amp; SDLC agents <span class="badge b-read" style="background:rgba(88,166,255,.12)">7</span></h2>
  <p class="lead">The core build loop — from a fuzzy idea to reviewed, tested, shipped code.</p>

  <div class="grid">
    <div class="card" style="--cardc:var(--plan)">
      <h3>tech-lead <span class="badge b-read">READ-ONLY</span></h3>
      <div class="role">Plan &amp; delegate</div>
      <p>Breaks multi-step work into an ordered plan mapped to specialists. Produces the DELEGATION PLAN — does not execute it.</p>
      <p class="trig"><b>Say:</b> "plan this feature", "break this down", "who should do what for X", "design the workflow to build Y"</p>
    </div>
    <div class="card" style="--cardc:var(--dev)">
      <h3>requirements-analyst <span class="badge b-author">AUTHOR</span></h3>
      <div class="role">Define before building</div>
      <p>Turns a vague idea into clear, testable requirements, user stories, and acceptance criteria. Writes a doc — no code.</p>
      <p class="trig"><b>Say:</b> "what exactly should this do?", "write user stories for X", "define acceptance criteria", "scope this feature"</p>
    </div>
    <div class="card" style="--cardc:var(--dev)">
      <h3>implementer <span class="badge b-doer">DOER</span></h3>
      <div class="role">Build the feature</div>
      <p>Writes new feature code from a clear spec, then runs the build/tests to confirm it works.</p>
      <p class="trig"><b>Say:</b> "implement X", "build this feature", "add an endpoint/component that does Y"</p>
    </div>
    <div class="card" style="--cardc:var(--dev)">
      <h3>debugger <span class="badge b-doer">DOER</span></h3>
      <div class="role">Find &amp; fix root cause</div>
      <p>Investigates an error, failing test, crash, or wrong output and applies a minimal fix.</p>
      <p class="trig"><b>Say:</b> "this throws X", "why is this test failing?", "debug this", "it returns the wrong value"</p>
    </div>
    <div class="card" style="--cardc:var(--dev)">
      <h3>test-engineer <span class="badge b-doer">DOER</span></h3>
      <div class="role">Write &amp; run tests</div>
      <p>Unit, integration, edge-case, regression tests. Writes the files and runs the suite to confirm they pass.</p>
      <p class="trig"><b>Say:</b> "write tests for X", "add coverage", "what cases am I missing?", "add a regression test for this bug"</p>
    </div>
    <div class="card" style="--cardc:var(--dev)">
      <h3>code-reviewer <span class="badge b-read">READ-ONLY</span></h3>
      <div class="role">Quality gate</div>
      <p>Reviews a diff for correctness bugs and quality before it ships. Reports findings — does <b>not</b> edit code.</p>
      <p class="trig"><b>Say:</b> "review my changes", "look over this diff", "is this code okay?"</p>
    </div>
    <div class="card" style="--cardc:var(--dev)">
      <h3>devops-engineer <span class="badge b-doer">DOER</span></h3>
      <div class="role">Build, CI/CD, deploy</div>
      <p>Pipelines (GitHub Actions), Dockerfiles/compose, release config, env management, deploy scripts.</p>
      <p class="trig"><b>Say:</b> "set up CI", "write a Dockerfile", "automate the release", "deploy this"</p>
    </div>
  </div>
</section>

<!-- ============ SECURITY ============ -->
<section id="sec"><span class="anchor"></span>
  <h2><span class="num">03</span> Security agents <span class="badge" style="background:rgba(249,117,131,.12);color:var(--sec)">6</span></h2>
  <p class="lead">Bake security into the SDLC — design-time, build-time, and incident-time.</p>

  <div class="grid">
    <div class="card" style="--cardc:var(--sec)">
      <h3>security-architect <span class="badge b-author">ADVISORY</span></h3>
      <div class="role">Secure-by-design</div>
      <p>Chooses security controls, reviews architecture for weaknesses, writes security ADRs and trade-off analyses. No commands, no code edits.</p>
      <p class="trig"><b>Say:</b> "is this auth design sound?", "what controls does this service need?", "write a security ADR"</p>
    </div>
    <div class="card" style="--cardc:var(--sec)">
      <h3>threat-modeler <span class="badge b-author">ADVISORY</span></h3>
      <div class="role">What could go wrong</div>
      <p>STRIDE/PASTA analysis, data-flow diagrams, attack trees, abuse cases. Outputs Mermaid diagrams + threat tables.</p>
      <p class="trig"><b>Say:</b> "threat model this design", "what are the attack paths?", "build a threat report for X"</p>
    </div>
    <div class="card" style="--cardc:var(--sec)">
      <h3>iam-engineer <span class="badge b-author">AUTHOR</span></h3>
      <div class="role">Identity &amp; access</div>
      <p>AuthN (OIDC/SAML/OAuth2/passkeys), authZ models (RBAC/ABAC/ReBAC), least-privilege, session/token handling, zero-trust.</p>
      <p class="trig"><b>Say:</b> "design login for X", "is this OAuth flow correct?", "set up roles/permissions", "review these IAM policies"</p>
    </div>
    <div class="card" style="--cardc:var(--sec)">
      <h3>cloud-security-engineer <span class="badge b-doer">DOER</span></h3>
      <div class="role">Cloud &amp; container posture</div>
      <p>AWS/Azure/GCP config review, K8s/container hardening, Terraform/CloudFormation security, CIS benchmarking. May run read-only scanners &amp; write hardened configs.</p>
      <p class="trig"><b>Say:</b> "review this Terraform", "harden this K8s manifest", "is this S3 config safe?"</p>
    </div>
    <div class="card" style="--cardc:var(--sec)">
      <h3>detection-engineer <span class="badge b-doer">DOER</span></h3>
      <div class="role">Detections &amp; hunting</div>
      <p>SIEM analytics (KQL, Sigma), threat-hunting queries, false-positive reduction, MITRE ATT&amp;CK coverage. Writes detection-as-code.</p>
      <p class="trig"><b>Say:</b> "write a Sigma rule for X", "detect this technique", "hunt for Y", "what's our ATT&amp;CK coverage?"</p>
    </div>
    <div class="card" style="--cardc:var(--sec)">
      <h3>incident-responder <span class="badge b-doer">DOER</span></h3>
      <div class="role">During / after a breach</div>
      <p>Triage, scoping, containment, eradication, recovery, post-incident review (NIST 800-61 / PICERL). Analyzes locally; gives runbook guidance for live actions.</p>
      <p class="trig"><b>Say:</b> "I think we've been breached", "help me investigate this alert/IOC", "write the incident timeline"</p>
    </div>
  </div>
</section>

<!-- ============ DOCS ============ -->
<section id="docs"><span class="anchor"></span>
  <h2><span class="num">04</span> Docs agents <span class="badge" style="background:rgba(86,211,100,.12);color:var(--doc)">3</span></h2>
  <p class="lead">Three lanes — don't mix them up. New front-door doc, new narrative writing, or keeping existing docs true over time.</p>

  <div class="grid">
    <div class="card" style="--cardc:var(--doc)">
      <h3>readme-specialist <span class="badge b-author">AUTHOR</span></h3>
      <div class="role">Front-door / landing docs</div>
      <p>Outstanding READMEs with markdown craft — badges, quickstart, diagrams. Authoring only.</p>
      <p class="trig"><b>Say:</b> "write a README", "make the README great", "add badges/quickstart"</p>
    </div>
    <div class="card" style="--cardc:var(--doc)">
      <h3>tech-writer <span class="badge b-author">AUTHOR</span></h3>
      <div class="role">Narrative guides &amp; ADRs</div>
      <p>Setup/usage guides, API reference, code comments, Architecture Decision Records. New writing, not code.</p>
      <p class="trig"><b>Say:</b> "document this", "explain how this works in the docs", "write an ADR"</p>
    </div>
    <div class="card" style="--cardc:var(--doc)">
      <h3>docs-maintainer <span class="badge b-doer">DOER</span></h3>
      <div class="role">Keep docs true</div>
      <p>The "document-as-you-go" enforcer — keeps docs accurate as code changes, writes release notes/changelogs, audits docs.</p>
      <p class="trig"><b>Say:</b> "update the docs for this change", "are the docs still accurate?", "write the changelog"</p>
    </div>
  </div>
</section>

<!-- ============ SYNTAX ============ -->
<section id="syntax"><span class="anchor"></span>
  <h2><span class="num">05</span> How to invoke them</h2>
  <p class="lead">There's no special command syntax — you write plain English and either let Claude route, or name the agent. Here's the spectrum, from least to most explicit.</p>

  <div class="two">
    <div>
      <h3 style="font-size:15px;margin:0 0 8px;color:var(--dev)">① Let it auto-route (simplest)</h3>
      <pre><code><span class="tok-c"># Just describe the task with a clear verb.</span>
<span class="tok-c"># Claude picks the matching specialist.</span>

Write unit tests for the new
payments module and run them.

<span class="tok-c"># → routes to test-engineer automatically</span></code></pre>

      <h3 style="font-size:15px;margin:0 0 8px;color:var(--dev)">② Name the agent (explicit &amp; safe)</h3>
      <pre><code>Use the <span class="tok-a">debugger</span> agent to find why
<span class="tok-s">checkout_test</span> is failing, then have
<span class="tok-a">code-reviewer</span> check the fix.</code></pre>
    </div>
    <div>
      <h3 style="font-size:15px;margin:0 0 8px;color:var(--plan)">③ Plan-first for big work</h3>
      <pre><code>Have <span class="tok-a">tech-lead</span> plan how to add
OAuth login, then run the plan.

<span class="tok-c"># tech-lead returns a DELEGATION PLAN;</span>
<span class="tok-c"># the main agent executes each step.</span></code></pre>

      <h3 style="font-size:15px;margin:0 0 8px;color:var(--doc)">④ Chain several in one prompt</h3>
      <pre><code><span class="tok-a">requirements-analyst</span> → define it,
<span class="tok-a">implementer</span> → build it,
<span class="tok-a">test-engineer</span> → test it,
<span class="tok-a">code-reviewer</span> → review it,
<span class="tok-a">docs-maintainer</span> → update docs.

<span class="tok-c"># State the order; Claude sequences them.</span></code></pre>
    </div>
  </div>

  <div class="note">
    <b>Parallel vs. sequential.</b> Independent agents (e.g. <code class="inline">threat-modeler</code> + <code class="inline">readme-specialist</code> on different files) can run at once — just ask for both. Dependent ones (<code class="inline">implementer</code> then <code class="inline">code-reviewer</code>) must be sequential, because the second needs the first's output. When in doubt, say the order out loud: "first… then…".
  </div>
</section>

<!-- ============ WORKFLOW ============ -->
<section id="workflow"><span class="anchor"></span>
  <h2><span class="num">06</span> A full feature, one prompt</h2>
  <p class="lead">This is the pattern to get comfortable with. A single prompt like the one below drives the whole pipeline — Claude hands each phase to the right specialist in turn.</p>

  <pre style="margin-bottom:26px"><code><span class="tok-c"># Paste a prompt shaped like this:</span>

"I want to add <span class="tok-s">passwordless email login</span>. Have <span class="tok-a">tech-lead</span> plan it,
then run the plan: <span class="tok-a">requirements-analyst</span> to define acceptance criteria,
<span class="tok-a">iam-engineer</span> to design the auth flow, <span class="tok-a">implementer</span> to build it,
<span class="tok-a">test-engineer</span> for tests, <span class="tok-a">code-reviewer</span> + <span class="tok-a">security-architect</span> to review,
and <span class="tok-a">docs-maintainer</span> to update the docs."</code></pre>

  <div class="flow">
    <div class="step" style="--stepc:var(--plan)"><div class="rail"><div class="node">0</div><div class="line"></div></div>
      <div class="body"><div class="ph">Plan</div><div class="ag">tech-lead</div>
      <p>Breaks the request into an ordered delegation plan and assigns each step below.</p></div></div>

    <div class="step" style="--stepc:var(--dev)"><div class="rail"><div class="node">1</div><div class="line"></div></div>
      <div class="body"><div class="ph">Define</div><div class="ag">requirements-analyst</div>
      <p>Writes testable requirements &amp; acceptance criteria so everyone builds the same thing.</p></div></div>

    <div class="step" style="--stepc:var(--sec)"><div class="rail"><div class="node">2</div><div class="line"></div></div>
      <div class="body"><div class="ph">Design (security)</div><div class="ag">iam-engineer · security-architect</div>
      <p>Designs the auth flow and the controls around it before a line of code is written.</p></div></div>

    <div class="step" style="--stepc:var(--dev)"><div class="rail"><div class="node">3</div><div class="line"></div></div>
      <div class="body"><div class="ph">Build</div><div class="ag">implementer</div>
      <p>Writes the feature code from the spec and confirms the build passes.</p></div></div>

    <div class="step" style="--stepc:var(--dev)"><div class="rail"><div class="node">4</div><div class="line"></div></div>
      <div class="body"><div class="ph">Test</div><div class="ag">test-engineer</div>
      <p>Adds unit + edge-case + regression tests and runs the suite green.</p></div></div>

    <div class="step" style="--stepc:var(--dev)"><div class="rail"><div class="node">5</div><div class="line"></div></div>
      <div class="body"><div class="ph">Review (parallel)</div><div class="ag">code-reviewer + security-architect</div>
      <p>Correctness review and security review run together; findings go back to <code class="inline">debugger</code>/<code class="inline">implementer</code> to fix.</p></div></div>

    <div class="step" style="--stepc:var(--dev)"><div class="rail"><div class="node">6</div><div class="line"></div></div>
      <div class="body"><div class="ph">Ship</div><div class="ag">devops-engineer</div>
      <p>Wires up CI and the release/deploy path (when you're ready to ship).</p></div></div>

    <div class="step" style="--stepc:var(--doc)"><div class="rail"><div class="node">7</div><div class="line"></div></div>
      <div class="body"><div class="ph">Document</div><div class="ag">docs-maintainer</div>
      <p>Updates docs &amp; changelog so the written record matches the new reality.</p></div></div>
  </div>
</section>

<!-- ============ CHEAT SHEET ============ -->
<section id="cheat"><span class="anchor"></span>
  <h2><span class="num">07</span> The cheat sheet</h2>
  <p class="lead">Keep this table open. Find the verb in your head, read across to the agent and the words that trigger it.</p>

  <div class="tablewrap">
  <table>
    <thead><tr><th>When you want to…</th><th>Agent</th><th>Type</th><th>Say something like…</th></tr></thead>
    <tbody>
      <tr><td>Plan multi-step work &amp; assign it</td><td class="ag" style="color:var(--plan)">tech-lead</td><td><span class="tag b-read">read</span></td><td class="say">"plan this feature", "who should do what?"</td></tr>
      <tr><td>Pin down what to build</td><td class="ag" style="color:var(--dev)">requirements-analyst</td><td><span class="tag b-author">author</span></td><td class="say">"define acceptance criteria for X"</td></tr>
      <tr><td>Build a new feature</td><td class="ag" style="color:var(--dev)">implementer</td><td><span class="tag b-doer">doer</span></td><td class="say">"implement X", "add an endpoint that…"</td></tr>
      <tr><td>Fix something broken</td><td class="ag" style="color:var(--dev)">debugger</td><td><span class="tag b-doer">doer</span></td><td class="say">"why is this test failing?", "debug this"</td></tr>
      <tr><td>Add / improve tests</td><td class="ag" style="color:var(--dev)">test-engineer</td><td><span class="tag b-doer">doer</span></td><td class="say">"write tests for X", "what cases am I missing?"</td></tr>
      <tr><td>Review a diff for bugs/quality</td><td class="ag" style="color:var(--dev)">code-reviewer</td><td><span class="tag b-read">read</span></td><td class="say">"review my changes", "is this code okay?"</td></tr>
      <tr><td>CI / Docker / deploy</td><td class="ag" style="color:var(--dev)">devops-engineer</td><td><span class="tag b-doer">doer</span></td><td class="say">"set up CI", "write a Dockerfile"</td></tr>
      <tr><td>Decide security controls / design</td><td class="ag" style="color:var(--sec)">security-architect</td><td><span class="tag b-author">advise</span></td><td class="say">"is this auth design sound?"</td></tr>
      <tr><td>Find attack paths (STRIDE)</td><td class="ag" style="color:var(--sec)">threat-modeler</td><td><span class="tag b-author">advise</span></td><td class="say">"threat model this design"</td></tr>
      <tr><td>Login / roles / tokens</td><td class="ag" style="color:var(--sec)">iam-engineer</td><td><span class="tag b-author">author</span></td><td class="say">"design login for X", "set up RBAC"</td></tr>
      <tr><td>Cloud / K8s / Terraform safety</td><td class="ag" style="color:var(--sec)">cloud-security-engineer</td><td><span class="tag b-doer">doer</span></td><td class="say">"review this Terraform", "harden this manifest"</td></tr>
      <tr><td>SIEM rules / threat hunting</td><td class="ag" style="color:var(--sec)">detection-engineer</td><td><span class="tag b-doer">doer</span></td><td class="say">"write a Sigma rule", "hunt for Y"</td></tr>
      <tr><td>Respond to a breach</td><td class="ag" style="color:var(--sec)">incident-responder</td><td><span class="tag b-doer">doer</span></td><td class="say">"help me investigate this alert/IOC"</td></tr>
      <tr><td>Write / polish a README</td><td class="ag" style="color:var(--doc)">readme-specialist</td><td><span class="tag b-author">author</span></td><td class="say">"make the README great"</td></tr>
      <tr><td>Guides, API docs, ADRs</td><td class="ag" style="color:var(--doc)">tech-writer</td><td><span class="tag b-author">author</span></td><td class="say">"document this", "write an ADR"</td></tr>
      <tr><td>Keep docs accurate over time</td><td class="ag" style="color:var(--doc)">docs-maintainer</td><td><span class="tag b-doer">doer</span></td><td class="say">"update the docs for this change"</td></tr>
    </tbody>
  </table>
  </div>
</section>

<!-- ============ RULES ============ -->
<section id="rules"><span class="anchor"></span>
  <h2><span class="num">08</span> Rules of thumb</h2>
  <div class="grid">
    <div class="card" style="--cardc:var(--accent)">
      <h3 style="font-family:inherit;color:var(--accent)">Match the verb to the lane</h3>
      <p>Plan / define / build / debug / test / review / document — each verb has a home. Pick the verb first; the agent follows.</p>
    </div>
    <div class="card" style="--cardc:var(--accent)">
      <h3 style="font-family:inherit;color:var(--accent)">Know who can touch code</h3>
      <p><span class="badge b-doer">DOER</span> writes &amp; runs. <span class="badge b-read">READ-ONLY</span> reports but won't edit. <span class="badge b-author">AUTHOR</span> writes docs only. Don't ask a reviewer to fix — route the fix to <code class="inline">debugger</code>.</p>
    </div>
    <div class="card" style="--cardc:var(--accent)">
      <h3 style="font-family:inherit;color:var(--accent)">Plan-first when it spans lanes</h3>
      <p>More than one specialist? Start with <code class="inline">tech-lead</code>. One specialist? Skip the plan and go direct.</p>
    </div>
    <div class="card" style="--cardc:var(--accent)">
      <h3 style="font-family:inherit;color:var(--accent)">State the order explicitly</h3>
      <p>"First X, then Y" sequences dependent agents. Asking for two unrelated things lets them run in parallel.</p>
    </div>
    <div class="card" style="--cardc:var(--accent)">
      <h3 style="font-family:inherit;color:var(--accent)">Don't mix the doc lanes</h3>
      <p>New README → <code class="inline">readme-specialist</code>. New guide/ADR → <code class="inline">tech-writer</code>. Keep existing docs true → <code class="inline">docs-maintainer</code>.</p>
    </div>
    <div class="card" style="--cardc:var(--accent)">
      <h3 style="font-family:inherit;color:var(--accent)">Shift security left</h3>
      <p>Pull in <code class="inline">threat-modeler</code> / <code class="inline">security-architect</code> at <i>design</i> time, not after shipping. Cheaper to fix on paper.</p>
    </div>
  </div>
</section>

</div>

<footer>
  Claude Code · 16-agent SDLC bench cheat sheet · generated 2026-06-14 · keep me open while you practice
</footer>

</body>
</html>
