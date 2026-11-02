# AI Agent Orchestration Prompt

Copy the prompt below into an AI coding agent with access to this workspace.

```text
Implement the approved Sample Scout static-site plans in:

/Users/jamez_43/Desktop/Sample-Scout/Sample-Scout-Demo

Read these files completely before editing:

- docs/plans/README.md
- docs/plans/01-static-product-page.md
- docs/plans/02-public-documentation.md
- docs/plans/03-quality-and-deployment.md

Treat those plans as the source of truth. Inspect the repository and git status
first, preserve unrelated work, and keep every change inside the
Sample-Scout-Demo repository.

Use subagents as follows:

1. Assign one implementation subagent Plan 01 only: index.html and the
   walkthrough poster/placeholder behavior.
2. Assign a second implementation subagent Plan 02 only: README.md,
   docs/architecture.md, and docs/releases.md.
3. Integrate their work, resolve overlap without discarding either agent's
   valid changes, and run Plan 03's checks yourself.
4. After implementation is complete, assign a fresh independent review
   subagent that did not author the changes. Give it all three plans and the
   full diff. Tell it to report findings only, ordered by severity, with exact
   file and line references. It must check truthfulness, accessibility,
   responsive behavior, privacy claims, link safety, unnecessary complexity,
   and scope violations.
5. Validate every review finding. Fix valid findings, reject incorrect ones
   with evidence, and rerun all checks.

Constraints:

- Do not modify the parent private Sample-Scout repository.
- Do not add a framework, package manager, backend, API, analytics, forms,
  accounts, cookies, or build step.
- Do not reuse the old hosted-demo video.
- Do not create or modify a GitHub Release.
- Do not commit, push, deploy Cloudflare Pages, change DNS, or send email.
- Do not invent the final walkthrough recording. Implement the planned
  placeholder and fixed future asset paths.
- Keep the existing dark-and-lime identity and prefer the smallest complete
  diff.

Before returning control, provide a manual-review package containing:

- A concise outcome summary organized by plan.
- git status and diff statistics.
- Clickable absolute paths to every changed file.
- Verification commands and results.
- Desktop and mobile screenshots.
- The independent review findings and how each was handled.
- Remaining owner-supplied prerequisites and risks.
- Exact deployment steps to perform only after manual approval.

Stop after presenting that package. Wait for my manual review; do not publish
anything.
```
