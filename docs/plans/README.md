# Static Site Implementation Plans

These plans replace Sample Scout's hosted live-demo pitch with a producer-focused,
static product site. The downloadable macOS application remains on the existing
GitHub Release; the private application repository, backend, and model code are
out of scope.

## Decisions already made

- Deploy one static page from this repository to Cloudflare Pages.
- Keep `https://samplescout.xyz` as the canonical URL.
- Optimize the page for music producers.
- Use **Watch the demo** as the primary action.
- Use **Download for macOS** as the secondary action and open the existing
  GitHub Release page.
- Call the product a **macOS technical preview**.
- State the supported target plainly: Apple silicon and macOS 26 or newer.
- Put detailed installation, Gatekeeper, checksum, and first-run model-download
  instructions on GitHub Releases rather than the homepage.
- Provide feedback through `jameswyllie42@gmail.com`.
- Do not add analytics, cookies, forms, accounts, a backend, or a frontend
  framework.
- Preserve the current dark-and-lime visual identity.

## Execution order

1. [01-static-product-page.md](01-static-product-page.md)
2. [02-public-documentation.md](02-public-documentation.md)
3. [03-quality-and-deployment.md](03-quality-and-deployment.md)

Plans 01 and 02 may be implemented in parallel because they touch separate
files. Plan 03 begins after both diffs are integrated.

## Scope boundary

Only files in this `Sample-Scout-Demo` repository may change. Do not modify the
parent private repository, create a new release, upload binaries, change DNS,
deploy Cloudflare Pages, commit, or push during implementation. Those remain
manual approval steps.

## Launch prerequisites

Before production deployment, manually confirm:

- The existing GitHub Release is public while signed out.
- It contains the macOS ZIP and matching SHA-256 checksum.
- Its notes describe Apple silicon, macOS 26+, Gatekeeper, the roughly 600 MB
  first-run model download, local processing, and troubleshooting.
- The ZIP installs and runs on a clean compatible Mac.
- Cloudflare Pages has access to this repository and `samplescout.xyz`.

## Definition of done

Implementation is ready for manual review when all three plans' acceptance
criteria pass, the working tree contains only intended public-site changes, and
the implementer provides the diff, verification output, screenshots, and known
risks without publishing anything.
