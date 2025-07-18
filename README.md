# setup-openfoam

[![CI](https://github.com/gerlero/setup-openfoam/actions/workflows/ci.yml/badge.svg)](https://github.com/gerlero/setup-openfoam/actions/workflows/ci.yml)
[![Release](https://github.com/gerlero/setup-openfoam/actions/workflows/release.yml/badge.svg)](https://github.com/gerlero/setup-openfoam/actions/workflows/release.yml)
![OpenFOAM](https://img.shields.io/badge/openfoam-.com%20|%20.org-informational)

Installs and activates a specific version of OpenFOAM in the GitHub Actions environment.

## Usage

```yaml
steps:
- uses: actions/checkout@v4
- uses: gerlero/setup-openfoam@v1
  with:
    openfoam-version: 2506
- run: blockMesh
- run: icoFoam
```

### Testing multiple OpenFOAM versions

```yaml
strategy:
  matrix:
    openfoam-version: [12, 13, 2412, 2506]  # Add other versions here if needed
  fail-fast: true
steps:
- uses: actions/checkout@v4
- name: Set up OpenFOAM
  uses: gerlero/setup-openfoam@v1
  with:
    openfoam-version: ${{ matrix.openfoam-version }}
- run: blockMesh
- run: icoFoam
```

## Inputs

### `openfoam-version`

**Required**. OpenFOAM version number (read below for the available versions).

### `cache`

Whether to cache the OpenFOAM installation between runs. Default: `true`.

## Available OpenFOAM versions by runner OS

- **`ubuntu-24.04`**: 2506, 2412, 2406, 2312, 2306, 2212 (openfoam.com), 13, 12, 11 (openfoam.org)

- **`ubuntu-22.04`**: 2506, 2412, 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com), 13, 12, 11, 10, 9 (openfoam.org)

- **`ubuntu-24.04-arm`**: 2506, 2412, 2406, 2312, 2306, 2212 (openfoam.com), 13, 12, 11 (openfoam.org)

- **`ubuntu-22.04-arm`**: 2506, 2412, 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2006 (openfoam.com), 13, 12, 11 (openfoam.org)

- **`macos-15`**, **`macos-14`**, **`macos-13`**: 2506, 2412, 2406, 2312, 2306, 2212, 2206, 2112 (via [OpenFOAM.app](https://github.com/gerlero/openfoam-app))

- [Docker `container`](https://docs.github.com/en/actions/writing-workflows/choosing-where-your-workflow-runs/running-jobs-in-a-container) based on:

  - `ubuntu:24.04`: 2506, 2412, 2406, 2312, 2306, 2212 (openfoam.com), 13, 12, 11 (openfoam.org)

  - `ubuntu:22.04`: 2506, 2412, 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com), 13, 12, 11, 10, 9 (openfoam.org)

  - `ubuntu:20.04`: 2506, 2412, 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com), 12, 11, 10, 9, 8, 7 (openfoam.org)

  - `debian:bookworm`: 2312, 2212, 2206, 2112, 2106, 2006 (openfoam.com)

  - `debian:bullseye`: 2312, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com)

- Windows: not supported

## Related actions

- [`gerlero/apt-install`](https://github.com/gerlero/apt-install): GitHub Action to install and cache APT packages.
- [`gerlero/add-apt-repository`](https://github.com/gerlero/add-apt-repository): GitHub Action to add a new APT repository for installing packages.
- [`gerlero/brew-install`](https://github.com/gerlero/brew-install): GitHub Action to install and cache Homebrew packages.
