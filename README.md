## Sideko SDK Updates Github Action

Example Usage
```yaml
- name: Update SDKs
  uses: sideko/sdk-update-action@v1
  with:
    release-type: 'minor'
    sdk-repos: |
      [
        "myorg/typescript-sdk",
        "myorg/python-sdk",
        "myorg/go-sdk",
        "myorg/java-sdk"
        "myorg/ruby-sdk"
        "myorg/rust-sdk"
      ]
    github-token: ${{ secrets.SDK_PAT }}
    sideko-api-key: ${{ secrets.SIDEKO_API_KEY }}
    auto-merge: true
```