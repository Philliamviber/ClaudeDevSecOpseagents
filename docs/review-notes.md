# Review Notes

## What this repo contains

This is a **documentation-only** repository. There is no application code to review. The two primary artifacts are:

1. `README.md` — an HTML-formatted cheat sheet describing 18 Claude Code subagents. Intended to be opened in a browser or a GitHub-rendered README view.

2. `changereview1.1.md` — an internal security audit document. This is marked "do NOT publish" and should be kept gitignored or local-only. See below.

## The HTML README

The README is written as a self-contained HTML file (not GitHub-flavored markdown). This is intentional — it uses custom CSS for syntax highlighting, colored cards, and a sticky navigation bar that would not render correctly as plain markdown.

**Implications for reviewers:**
- Raw markdown renderers (VS Code Preview, some CI tools) will show the HTML source, not the rendered output.
- To read the cheat sheet correctly: open `README.md` in a browser (File → Open in browser), or push to GitHub where the HTML is rendered inline.
- Any edits must maintain valid HTML. Use a browser developer tools check after editing.

**What to verify before publishing:**
- All 18 agents are listed accurately.
- The "authorized only" warnings on `osint-redteamer` and `ad-redteamer` are present and prominent.
- The HTML is valid and renders correctly in Chrome/Firefox/Safari.
- No local file paths, usernames, or internal URLs are embedded in the HTML.

## The `changereview1.1.md` audit document

This file is a security audit of a local path-disclosure scan plan. It was generated as part of a pre-publication review process and contains:
- The name of the audited document (a local path: `c:\data\markdownplan.md`).
- A list of repository names and path conventions from the audit scope.

**This file should not be committed to a public repository.** Confirm it is in `.gitignore`. If it needs to be preserved for audit trail purposes, store it in a separate non-public location.

## Pre-publication review for this repo

Before publishing `Claudedevsecopsagents` publicly:

- [ ] Verify `changereview1.1.md` is in `.gitignore` or excluded from the publish scope.
- [ ] Scan the repo with the checklist in `docs/review-checklist.md` (or see `githubactionsguidance` for the full pre-publication workflow).
- [ ] Check the HTML in `README.md` for any embedded local paths or personal information.
- [ ] Verify all agent descriptions are accurate against the actual Claude Code agent system prompts (if available).
- [ ] Check that the "authorized only" warnings for `osint-redteamer` and `ad-redteamer` are accurate and sufficient for public consumption.

## Assumptions

- Readers have Claude Code installed and have access to a Claude Code multi-agent setup.
- The 18 agents described in the cheat sheet exist as configured subagents in the Claude Code environment.
- "Authorization-gated" behavior for the red team agents is enforced by the agent system prompts, not by this documentation alone. This doc describes expected behavior — it does not enforce it.

## Risks to review before use

- **Red team agents require explicit authorization.** The cheat sheet describes this prominently, but documentation does not prevent misuse. Confirm that the underlying agent system prompts for `osint-redteamer` and `ad-redteamer` enforce authorization checks.
- **Agent capabilities may change** as Claude Code evolves. The cheat sheet may become inaccurate if the underlying agent definitions are updated. Assign ownership for keeping the cheat sheet current.
- **The HTML cheat sheet is not versioned** (no version number or "last updated" date beyond the footer). Consider adding a date/version badge.
