# Plan 01 — Static Product Page

## Objective

Replace the hosted-demo/private-beta landing page with one responsive static
page that explains the local desktop product, shows a deferred walkthrough slot,
links to the existing macOS release, and invites feedback by email.

## Files

Modify:

- `index.html`

Create:

- `assets/sample-scout-walkthrough-poster.svg`

Deferred assets, supplied later by the owner:

- `assets/sample-scout-walkthrough.mp4`
- `assets/sample-scout-walkthrough.en.vtt`

Do not add a package manager, framework, generated bundle, analytics script, or
backend configuration.

## Required page structure

1. A compact navigation row with the Sample Scout name and **macOS technical
   preview** status.
2. A producer-focused hero using the existing "Find the sound in your head"
   positioning.
3. Primary action: **Watch the demo**, linking to the walkthrough section.
4. Secondary action: **Download for macOS**, opening the existing release page:
   `https://github.com/Jamez43/Sample-Scout-Demo/releases/tag/v0.1.0-beta.1`.
5. A walkthrough section with a branded coming-soon poster.
6. A three-step explanation: select a local library, index it locally, search in
   natural language and preview matches.
7. Producer benefits: natural-language discovery, fast previewing, and local
   privacy.
8. A concise technical explanation: compatible CLAP audio/text embeddings,
   local audio indexing, similarity ranking, and no hosted sample upload.
9. A visible compatibility note: Apple silicon, macOS 26+, approximately 261
   MiB download, roughly 600 MB model download on first use, ad-hoc signed and
   not notarized.
10. A feedback action using
    `mailto:jameswyllie42@gmail.com?subject=Sample%20Scout%20feedback`.

## Walkthrough placeholder

The initial page must remain intentional before the final recording exists.
Show the SVG poster and a short "Desktop walkthrough coming soon" message. Keep
the final MP4 and WebVTT paths fixed in the markup so the owner can add those two
files later without restructuring the page.

Use the smallest browser-native behavior needed to reveal the video only when a
playable source loads; otherwise retain the poster. Do not create a fake product
video or reuse the old hosted-backend recording.

The final recording should be 45–60 seconds and show:

1. Selecting a local sample folder.
2. Indexing the folder.
3. Entering a natural-language query.
4. Previewing a returned sample.

Encode it as H.264/AAC with fast-start metadata and keep it below 20 MiB. The
Cloudflare Pages per-asset ceiling is 25 MiB.

## Copy constraints

Remove active marketing references to:

- A live demo or hosted search.
- Private beta access or invitations.
- Registration, accounts, or uploads.
- Windows, Linux, Intel Mac, or unsupported macOS compatibility.
- Apple notarization.

Do not claim the application is completely offline: the CLAP model downloads on
first use. It is accurate to say sample indexing, search, and playback happen
locally and sample audio is not uploaded to a hosted search service.

## Accessibility and responsive behavior

- Use semantic landmarks and one `h1`.
- Keep heading levels ordered.
- Provide visible keyboard focus for every link and control.
- Ensure buttons are links when they navigate.
- Give the poster meaningful alternative text.
- Include a caption track path for the future video.
- Preserve readable contrast and touch targets of at least 44 CSS pixels.
- Support `prefers-reduced-motion` and do not require animation.
- Keep the layout usable at 375 px, 768 px, and wide desktop widths.

## Acceptance criteria

- The page works when served as plain static files.
- It contains no runtime dependency or API request.
- The primary action reaches the walkthrough section.
- The download action opens the exact existing release in a new tab without
  using `window.open`.
- The placeholder looks complete when the MP4 is absent.
- Adding the MP4 and VTT at their fixed paths activates the video without a page
  redesign.
- The email action opens a message addressed to the supplied address with the
  requested subject.
- Keyboard navigation, focus, responsive layout, and reduced-motion behavior
  pass manual checks.
