# python-release
GitHub action workflow for creating Python semver release using poetry

## Usage

### Install Specific Group

```yaml
name: Release

on:
  push:
    tags:
      - 'v*.*.*'

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Create Release
        uses: RSGInc/python-release@v1
        with:
          token: ${{ secrets.PAT }}
          tag: ${{ github.ref_name }}
          python-version: 3.9
```
