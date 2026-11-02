# Plan 03 — Quality, Review, and Deployment Handoff

## Objective

Verify the integrated static-site change and prepare a manual deployment
handoff. This plan does not authorize committing, pushing, changing DNS,
editing the GitHub Release, or deploying Cloudflare Pages.

## Preconditions

- Plans 01 and 02 are implemented and integrated.
- The working tree was inspected before implementation so unrelated user work
  is preserved.
- The existing release URL is final.

## Automated checks

Run from the `Sample-Scout-Demo` repository:

```bash
git diff --check
git status --short
rg -n -i "try the live demo|private beta|request access|invited tester|distributed directly|hosted search" --glob '*.html' --glob '*.md'
python3 -m http.server 8000
```

Use the local server only long enough to inspect the site, then stop it. Do not
add a permanent test runner for these few static checks.

If the final video is present, verify its byte size is below Cloudflare Pages'
25 MiB asset limit and preferably below the 20 MiB project target. Confirm the
MP4 has H.264 video, AAC audio, and fast-start metadata, and that the WebVTT file
is valid and synchronized.

## Browser review

Capture desktop and mobile screenshots and verify:

- 375 px, 768 px, and wide desktop layouts.
- Keyboard-only navigation and visible focus.
- Primary and secondary CTA order.
- Placeholder behavior when the MP4 is absent.
- Playback, seeking, audio, and captions when the MP4 is present.
- Release link destination.
- Email address and prefilled subject.
- No horizontal scrolling, clipped copy, or unreadable contrast.
- Reduced-motion preference does not trigger unnecessary movement.

## Independent review

After implementation, a reviewer who did not author the changes must inspect
the complete diff against all plans. The reviewer should report findings only,
ranked by severity, with file and line references. Review at least:

- Product truthfulness and stale hosted-demo claims.
- Unsupported platform promises.
- Accessibility and semantic HTML.
- Responsive behavior.
- External-link safety.
- Privacy claims.
- Unnecessary dependencies, abstractions, JavaScript, or generated files.
- Scope violations outside this public repository.

Validated findings are fixed before the final verification run.

## Cloudflare Pages handoff

After manual code approval, configure:

- Repository: `Jamez43/Sample-Scout-Demo`
- Production branch: `main`
- Framework preset: none
- Build command: none
- Output directory: repository root
- Custom domain: `samplescout.xyz`

Production verification after deployment:

- HTTPS is valid.
- The apex domain resolves and loads from an external network.
- The production page matches the reviewed commit.
- GitHub Release and email links work.
- The canonical URL is `https://samplescout.xyz/`.
- The previous Cloudflare deployment can be selected for rollback.

## Manual review package

Return all of the following before any commit or deployment:

- Summary of changes by plan.
- `git status --short` and diff statistics.
- Clickable links to every changed file.
- Commands run and their results.
- Desktop and mobile screenshots.
- Independent-review findings and their disposition.
- Deferred items, especially the final MP4/VTT and external release checks.
- Exact post-approval deployment steps.

## Acceptance criteria

- All plan criteria pass or are explicitly marked as owner-supplied launch
  prerequisites.
- The independent reviewer has no unresolved high- or medium-severity findings.
- No commit, push, release mutation, DNS change, or Cloudflare deployment has
  occurred.
- The owner receives enough evidence to review the implementation manually.
