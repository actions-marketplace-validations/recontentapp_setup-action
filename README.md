# GitHub Action

## About
This action sets up the Recontent CLI, [`recontent`](https://github.com/recontentapp/cli), on GitHub's hosted Actions runners.

This action can be run on `ubuntu-latest`, `windows-latest`, and `macos-latest` GitHub Actions runners, and will install and expose a specified version of the `recontent` CLI on the runner environment.

## Usage

Setup the `recontent` CLI:

```yaml
steps:
- uses: recontentapp/setup-recontent@v1
```

A specific version of the `recontent` CLI can be installed:

```yaml
steps:
- uses: recontentapp/setup-recontent@v1
  with:
    version:
      0.1.1
```

## Inputs
The actions supports the following inputs:

- `version`: The version of `recontent` to install, defaulting to `0.1.1`
