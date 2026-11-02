# Sample Scout

Sample Scout helps music producers find sounds in their own sample libraries with natural-language search. It is a downloadable **macOS technical preview**; this repository contains the public product site and documentation, not the proprietary application source.

## Get the app

- [Get the demo from the existing GitHub Release](https://github.com/Jamez43/Sample-Scout-Demo/releases/tag/v0.1.0-beta.1)
- [Watch the desktop walkthrough](https://samplescout.xyz/#walkthrough) (recording coming soon)

The preview supports **Apple silicon Macs running macOS 26 or newer**. The app download is approximately **261 MiB**. On first use it downloads roughly **600 MB of model files**, so an internet connection is required for that download. Sample indexing, search, and playback happen locally; sample audio is not uploaded to a search service. No account is required.

The app is ad-hoc signed and not notarized. macOS Gatekeeper may show a warning when opening it; follow the installation instructions in the release notes.

## How it works

Choose a local sample folder, let Sample Scout index it on your Mac, then search in natural language and preview matching files. See the [architecture overview](docs/architecture.md) for details.

## Feedback and support

For problems, questions, or feedback, email [jameswyllie42@gmail.com](mailto:jameswyllie42@gmail.com?subject=Sample%20Scout%20feedback).

## Distribution and rights

The downloadable application is proprietary software. This repository does not grant a license to reproduce, modify, or redistribute Sample Scout or its source code. See the release notes and in-app notices for applicable terms.
