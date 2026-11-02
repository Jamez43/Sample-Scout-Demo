# Releases

The existing [Sample Scout v0.1.0-beta.1 GitHub Release](https://github.com/Jamez43/Sample-Scout-Demo/releases/tag/v0.1.0-beta.1) is the download destination for the macOS technical preview. The application is proprietary and its binaries belong in GitHub Releases, not Git history.

## Installation notes

The preview supports **Apple silicon Macs running macOS 26 or newer**. The app download is approximately **261 MiB**. It is ad-hoc signed and not notarized, so macOS Gatekeeper may warn when you open it. Review the release's installation instructions before proceeding. On first use, the app downloads roughly **600 MB of model files** and needs an internet connection for that step. Sample indexing, search, and playback happen locally; sample audio is not uploaded to a search service.

## Public artifact checks

Before directing users to a release, confirm that its public page contains:

- The macOS ZIP and a matching SHA-256 checksum.
- The artifact size and supported platform (Apple silicon, macOS 26 or newer).
- Clear Gatekeeper instructions that disclose the ad-hoc signature and lack of notarization.
- The first-run model download size and internet requirement.
- A clear explanation that sample audio stays local, plus the support address [jameswyllie42@gmail.com](mailto:jameswyllie42@gmail.com?subject=Sample%20Scout%20feedback).

## Future maintainer procedure

When preparing a future app version, build its archive from the private application repository, publish it as a GitHub Release, and upload the ZIP and matching checksum there. Include supported hardware, limitations, installation steps, first-run model download, privacy, and support details in the notes. This procedure does not change the existing release.

Keep private source, credentials, local databases, customer files, model caches, and application binaries out of this repository and Git history.
