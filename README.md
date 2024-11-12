## Sideko SDK Updates Github Action

### Getting Started Example
```yaml
jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: sideko-inc/sdk-release
        with:
          release-type: patch
          sdk-repos: |-
            sideko-inc/sideko-ts
          github-token: ${{ secrets.SDK_GITHUB_PAT }}
          sideko-api-key: ${{ secrets.SIDEKO_SERVICE_ACCOUNT_KEY }}
```