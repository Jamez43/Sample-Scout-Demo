# Plan 02 — Public Documentation Alignment

## Objective

Make the public repository describe the same static-site and desktop-preview
experience as the landing page. Remove stale live-demo, invitation, and private
distribution claims without exposing private application source.

## Files

Modify:

- `README.md`
- `docs/architecture.md`
- `docs/releases.md`

Do not modify GitHub Release state from this plan. Inspect it read-only and
report any mismatch for manual correction.

## README changes

- Describe Sample Scout as a downloadable macOS technical preview.
- Replace the live-demo link with links to the walkthrough section/site and the
  existing GitHub Release.
- Remove private-beta and invited-tester language.
- State the supported platform and first-run model requirement.
- Explain that audio stays local and that no account is required.
- Direct problems and feedback to `jameswyllie42@gmail.com`.
- Preserve the proprietary-source boundary.

## Architecture changes

Keep the existing local-search diagram and sharpen its public explanation:

- Audio files are selected from the producer's Mac.
- Audio embeddings and metadata are stored locally.
- Text queries are embedded in a compatible CLAP space.
- Local similarity ranking returns matching file paths.
- Playback reads the original local file.
- Only model files are downloaded; sample audio is not uploaded to a hosted
  search backend.

Do not document the retired hosted Flask deployment as part of the public
product architecture.

## Release guide changes

- Describe the existing GitHub Release as the download destination.
- Remove instructions to create another release unless clearly labeled as a
  future maintainer procedure.
- List the public artifact checks: ZIP, checksum, size, supported platform,
  Gatekeeper instructions, first-run model download, privacy, and support email.
- State that application binaries belong in GitHub Releases, not Git history.
- Keep private source, credentials, local databases, customer files, and model
  caches out of this repository.

## Consistency check

After editing, search active public content for these stale phrases and inspect
every match:

```text
Try the live demo
private beta
request access
invited tester
distributed directly
hosted search
```

Historical wording may remain only when explicitly described as historical and
cannot be mistaken for the current offer.

## Acceptance criteria

- The homepage and all three documents agree on status, platform, distribution,
  privacy, and feedback.
- No document promises a hosted backend.
- No document claims public application source is present.
- The existing release is linked consistently.
- Installation limitations are candid and producer-readable.
- No binary, credential, private source, or generated model asset is added.
