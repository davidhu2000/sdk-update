## Sideko SDK Updates Github Action

### Getting Started Example
```yaml
jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: sideko-inc/sdk-release
        with:
          release-type: ${{ inputs.release-type }}
          sdk-repos: |-
            your-org/cli
            your-org/client-ts
            your-org/client-py
            your-org/client-rb
            your-org/client-go
            your-org/client-java
            your-org/client-rs
          github-token: ${{ secrets.SDK_GITHUB_TOKEN }}
          sideko-api-key: ${{ secrets.SIDEKO_SERVICE_ACCOUNT_KEY }}
```