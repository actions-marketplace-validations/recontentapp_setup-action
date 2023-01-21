# GitHub Action

## About
This action sets up the Recontent CLI, [`recontent`](https://github.com/recontentapp/cli), on GitHub's hosted Actions runners.

This action can be run on `ubuntu-latest`, `windows-latest`, and `macos-latest` GitHub Actions runners, and will install and expose a specified version of the `recontent` CLI on the runner environment.

## Usage

```yaml
jobs:
  pull-phrases:
    runs-on: ubuntu-latest
    steps:
      - name: Set up Recontent CLI
        uses: recontentapp/setup-action@v1

      - name: Pull translations
        env:
          RECONTENT_API_KEY: dummy-api-key
        run: recontent export phrases -p <project_id> -f "{{.LanguageLocale}}.{{.FormatExtension}}" 
```

A specific version of the `recontent` CLI can be installed:

```yaml
jobs:
  pull-phrases:
    runs-on: ubuntu-latest
    steps:
      - name: Set up Recontent CLI
        uses: recontentapp/setup-action@v1
        with:
          version:
            0.1.3

      - name: Pull translations
        env:
          RECONTENT_API_KEY: dummy-api-key
        run: recontent export phrases -p <project_id> -f "{{.LanguageLocale}}.{{.FormatExtension}}" 
```

## Inputs
The actions supports the following inputs:

- `version`: The version of `recontent` to install, defaulting to `0.1.3`
