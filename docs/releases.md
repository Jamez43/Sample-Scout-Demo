# Releases

Releases are published from this repository's [Releases page](../../releases).

## Current beta distribution

The initial desktop beta targets **Apple silicon Macs**. Download the ZIP asset from the latest release, unzip it, and open Sample Scout. The first launch may download the search model, so an internet connection is needed then.

## Before publishing a release

1. Build the desktop archive from the private application repository.
2. Create a GitHub release here using a version tag such as `v0.1.0-beta.1`.
3. Upload the ZIP and its SHA-256 checksum as release assets.
4. Include supported hardware, known limitations, installation steps, and feedback instructions in the release notes.

Do not commit desktop archives, customer libraries, environment files, production configuration, or application source code to this repository.

