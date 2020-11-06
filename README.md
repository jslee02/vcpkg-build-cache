# vcpkg-build-cache

[![CI](https://github.com/jslee02/vcpkg-build-cache/workflows/CI/badge.svg)](https://github.com/jslee02/vcpkg-build-cache/actions)

## Overview

This repository publishes archives of prebuilt [vcpkg] pakcages.

To download the archives,

```shell
# Install wget if not already
choco install -y wget

# Download the archive (see to check available <tag>: https://github.com/jslee02/vcpkg-build-cache/releases)
wget -q https://github.com/jslee02/vcpkg-build-cache/releases/download/<tag>/vcpkg-build-cache.zip

# Extract the vcpkg files
unzip -qq vcpkg-build-cache.zip -d <path>
```

## Release Process

1. Get a vcpkg commit or tag that you want to use from [vcpkg] (e.g., `70f192e`).
1. Update [`VCPKG_VERSION`](https://github.com/jslee02/vcpkg-build-cache/blob/79251526f14823681888d3f012d10fceea291b8e/.github/workflows/ci.yml#L15) in `ci.yaml` to the vcpkg commit or tag
1. Push the change to this repository
1. Create a tag for the change in the pattern of `vcpkg-<vcpkg_commit_or_tag>` (e.g., `vcpkg-70f192e`)
1. Create a release from the tag, then GitHub Actions will publish a new vcpkg archive that can be found in the Assets section in the [Release page](https://github.com/jslee02/vcpkg-build-cache/releases).

[vcpkg]: https://github.com/microsoft/vcpkg
