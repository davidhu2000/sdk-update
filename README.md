<p align="center">
  <a href="https://sideko.dev">
    <img src="https://storage.googleapis.com/sideko.appspot.com/public_assets/website_assets/logo-symbol.svg" height="96">
    <h3 align="center">Sideko, Inc.</h3>
  </a>
</p>

<p align="center">
  Your API Ecosystem, On Autopilot
</p>

<p align="center">
  <a href="https://sideko.dev"><strong>Website</strong></a> |
  <a href="https://docs.sideko.dev"><strong>Docs</strong></a>
</p>
<br/>

# SDK Update Action

Easily update Sideko SDKs with this action. This action is designed only for updates,
if you do not yet have a Sideko generated SDK, install the [`sideko`](https://github.com/Sideko-Inc/sideko) CLI and run `sideko sdk init` to get started!

## Quick Start

```yaml
jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: sideko-inc/sdk-update
        with:
          repo: your-org/client-py
          language: python
          sdk-version: patch
          github-token: ${{ secrets.SDK_GITHUB_TOKEN }}
          sideko-api-key: ${{ secrets.SIDEKO_SERVICE_ACCOUNT_KEY }}
```

## Inputs

| Name                 | Description                                                                                                                                                                                | Required | Default              |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------: | -------------------- |
| `repo`               | SDK repository to update (e.g. your-org/client-py)                                                                                                                                         |    ✅    |                      |
| `language`           | Programming language of the repository, see [docs for permitted values](https://docs.sideko.dev/references/sideko/generate-sdk)                                                            |    ✅    |                      |
| `sdk-version`        | Exact version to set the SDK (e.g. `1.4.2`) or a release version for automatic version incrementing, see [docs for permitted values](https://docs.sideko.dev/references/sideko/update-sdk) |    ✅    |                      |
| `github-token`       | GitHub token with appropriate access to the SDK repository, see below for details.                                                                                                         |    ✅    |                      |
| `sideko-api-key`     | Sideko API key with appropriate access to the API project, see below for details.                                                                                                          |    ✅    |                      |
| `sideko-config-path` | Path to your SDK config file in the current repository.                                                                                                                                    |    ❌    | sdk-config.yaml      |
| `api-version`        | Version of the API in the Sideko project to generate from.                                                                                                                                 |    ❌    | latest               |
| `pr-title-template`  | Template for PR title. Use {type} for release type.                                                                                                                                        |    ❌    | SDK release ({type}) |
| `pr-auto-merge`      | Automatically merge the created PR into the SDK repository.                                                                                                                                |    ❌    | false                |
| `pr-base-branch`     | Base branch to create SDK update PR against.                                                                                                                                               |    ❌    | main                 |
| `pr-description`     | Description content (markdown) to include in SDK PR.                                                                                                                                       |    ❌    |                      |
| `branch-prefix`      | Prefix for the created branch names.                                                                                                                                                       |    ❌    | sdk-release          |
