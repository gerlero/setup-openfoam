# setup-openfoam

[![CI](https://github.com/gerlero/setup-openfoam/actions/workflows/ci.yml/badge.svg)](https://github.com/gerlero/setup-openfoam/actions/workflows/ci.yml)
![OpenFOAM](https://img.shields.io/badge/openfoam-.com%20|%20.org-informational)

Installs and activates a specific version of OpenFOAM in the GitHub Actions environment.

## Usage

```yaml
steps:
- uses: actions/checkout@v4
- uses: gerlero/setup-openfoam@v1
  with:
    openfoam-version: 2406
- run: blockMesh
- run: icoFoam
```

## Available OpenFOAM versions by runner OS

- **`ubuntu-24.04`**: 2406, 2312 (openfoam.com), 12, 11 (openfoam.org)

- **`ubuntu-22.04`**: 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com), 12, 11, 10, 9 (openfoam.org)

- **`ubuntu-20.04`**: 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com), 12, 11, 10, 9, 8, 7 (openfoam.org)

- **`macos-14`**, **`macos-13`**, **`macos-12`**: 2406, 2312, 2306, 2212, 2206, 2112 (via [OpenFOAM.app](https://github.com/gerlero/openfoam-app))

- [Docker `container`](https://docs.github.com/en/actions/writing-workflows/choosing-where-your-workflow-runs/running-jobs-in-a-container) based on:

  - `ubuntu:24.04`: 2406, 2312 (openfoam.com), 12, 11 (openfoam.org)

  - `ubuntu:22.04`: 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com), 12, 11, 10, 9 (openfoam.org)

  - `ubuntu:20.04`: 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com), 12, 11, 10, 9, 8, 7 (openfoam.org)

  - `debian:bookworm`: 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2006 (openfoam.com)

  - `debian:bullseye`: 2406, 2312, 2306, 2212, 2206, 2112, 2106, 2012, 2006 (openfoam.com)

- Windows: not supported
