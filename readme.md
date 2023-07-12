# GitHub Actions Vercel

A collection of GitHub actions for Vercel projects.

## Actions

### Deploy to Vercel

This action will deploy the application to Vercel.

Example:

```yaml
  - uses: actions/checkout@v3

  - uses: aboutbits/github-actions-vercel/deploy@v1
    with:
      vercel-token: ${{ secrets.VERCEL_TOKEN }}
      vercel-org-id: ${{ env.VERCEL_ORG_ID }}
      vercel-project-id: ${{ env.VERCEL_PROJECT_ID }}
      arguments: --prod
```

## Versioning

In order to have a verioning in place and working, create leightweight tags that point to the appropriate minor release versions.

Creating a new minor release:

```bash
git tag v1
git push --tags
```

Replacing an already existing minor release:

```bash
git tag -d v1
git push origin :refs/tags/v1
git tag v1
git push --tags
```

## Information

About Bits is a company based in South Tyrol, Italy. You can find more information about us on [our website](https://aboutbits.it).

### Support

For support, please contact [info@aboutbits.it](mailto:info@aboutbits.it).

### Credits

- [All Contributors](../../contributors)

### License

The MIT License (MIT). Please see the [license file](license.md) for more information.
