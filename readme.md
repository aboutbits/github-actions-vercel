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

| Name                     | Required/Default | Description                              |
|--------------------------|------------------|------------------------------------------|
| `working-directory`      | (.)              | The working directory of the action      |
| `vercel-token`           | Required         | The token to access the Vercel API       |
| `vercel-organization-id` | Required         | The ID of the Vercel organization        |
| `vercel-project-id`      | Required         | The ID of the Vercel project             |
| `build-arguments`        | (empty)          | Additional build command line arguments  |
| `deploy-arguments`       | (empty)          | Additional deploy command line arguments |

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
      deployment-domain: https://xyz.vercel.app
      preview-domain: example.aboutbits.it
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

### Unlink a domain of a Vercel deployment

This action will unlink an added domain of a Vercel deployment URL.

#### Example

```yaml
  - uses: actions/checkout@v3

  - uses: aboutbits/github-actions-vercel/unlink-domain@v1
    env:
    with:
      vercel-token: ${{ secrets.VERCEL_TOKEN }}
      vercel-scope: xxx
      preview-domain: example.aboutbits.it
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                     | Required/Default | Description                                       |
|--------------------------|------------------|---------------------------------------------------|
| `working-directory`      | (.)              | The working directory of the action               |
| `vercel-token`           | Required         | The token to access the Vercel API                |
| `vercel-scope`           | Required         | The Vercel scope                                  |
| `preview-domain`         | Required         | The custom preview domain that should be unlinked |

## Build & Publish

To build and publish the action, visit the GitHub Actions page of the repository and trigger the workflow "Release Package" manually.

## Information

About Bits is a company based in South Tyrol, Italy. You can find more information about us on [our website](https://aboutbits.it).

### Support

For support, please contact [info@aboutbits.it](mailto:info@aboutbits.it).

### Credits

- [All Contributors](../../contributors)

### License

The MIT License (MIT). Please see the [license file](license.md) for more information.
