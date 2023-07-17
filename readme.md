# GitHub Actions Vercel

A collection of GitHub actions for Vercel projects.

## Actions

### Deploy to Vercel

This action will deploy the application to Vercel.

#### Example

```yaml
  - uses: actions/checkout@v3

  - uses: aboutbits/github-actions-vercel/deploy@v1
    env:
    with:
      vercel-token: ${{ secrets.VERCEL_TOKEN }}
      vercel-organization-id: yyy
      vercel-project-id: zzz
      arguments: --prod
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                     | Required/Default | Description                                 |
|--------------------------|------------------|---------------------------------------------|
| `working-directory`      | (.)              | The working directory of the action         |
| `vercel-token`           | Required         | The token to access the Vercel API          |
| `vercel-organization-id` | Required         | The ID of the Vercel organization           |
| `vercel-project-id`      | Required         | The ID of the Vercel project                |
| `arguments`              | (empty)          | Additional CLI arguments for the deplyoment |

#### Outputs

The following outputs can be used after the successful execution:

| Name                     | Description                       |
|--------------------------|-----------------------------------|
| `url`                    | The URL of the deployment         |

### Link a domain to a Vercel deployment

This action will link an added domain to a Vercel deployment URL.

#### Example

```yaml
  - uses: actions/checkout@v3

  - uses: aboutbits/github-actions-vercel/link-domain@v1
    env:
    with:
      vercel-token: ${{ secrets.VERCEL_TOKEN }}
      vercel-scope: xxx
      domain: example.aboutbits.it
      url: https://xyz.vercel.app
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                     | Required/Default | Description                                     |
|--------------------------|------------------|-------------------------------------------------|
| `working-directory`      | (.)              | The working directory of the action             |
| `vercel-token`           | Required         | The token to access the Vercel API              |
| `vercel-scope`           | Required         | The Vercel scope                                |
| `deployment-domain`      | Required         | The deployment domain recieved from Vercel      |
| `preview-domain`         | Required         | The custom preview domain that should be linked |

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
