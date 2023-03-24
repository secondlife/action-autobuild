# action-autobuild

Build and package an autobuild project.

Example:
```yaml
name: Build

on:
  pull_request:
  tag:
    branches: [main]
    tags: [v*]

jobs:
  build:
    strategy:
      matrix:
        os: [windows-2019, macos-11, ubuntu-latest]
    runs-on: ${{ matrix.os }}
    steps:
      - uses: secondlife/action-autobuild@v3
        with:
          autobuild-version: 3.9.0 # PyPI version or git ref
```

For a full list of available action inputs see [action.yaml](action.yaml).
