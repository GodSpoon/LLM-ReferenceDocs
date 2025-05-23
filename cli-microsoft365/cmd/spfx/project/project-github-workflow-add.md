-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spfx project github workflow add

Adds a GitHub workflow for a SharePoint Framework project

## Usage

```sh
m365 spfx project github workflow add [options]
```

## Options

```md definition-list
`-n, --name [name]`
: Name of the workflow that will be created. If none is specified a default name will be used 'Deploy Solution ${name of sppkg file}'.

`-b, --branchName [branchName]`
: Specify the branch name which should trigger the workflow on push. If none is specified a default will be used which is 'main'.

`-m, --manuallyTrigger`
: When specified a manual trigger option will be added to the workflow: `workflow_dispatch`.

`-l, --loginMethod [loginMethod]`
: Specify the login method used for the login action. Possible options are: `user`, `application`. Default `application`.

`-s, --scope [scope]`
: Scope of the app catalog: `tenant`, `sitecollection`. Default is `tenant`.

`-u, --siteUrl [siteUrl]`
: The URL of the site collection where the solution package will be added. Required if scope is set to `sitecollection`.

`--skipFeatureDeployment`
: When specified and the app supports tenant-wide deployment, deploy it to the whole tenant.
```

<Global />

## Remarks

The `spfx project github workflow add` will create a workflow .yml file in the `.github/workflows` directory in your project. If such directory does not exist the command will automatically create it.

For the `application` login method the command does not register a Microsoft Entra application nor create the required certificate. In order for you to proceed you will need to first obtain (create) a self-signed certificate and register a new Microsoft Entra application with certificate authentication. After that in GitHub repo settings, you will need to create the following secrets:

- `APP_ID` - client id of the registered Microsoft Entra application
- `CERTIFICATE_ENCODED` - application's encoded certificate
- `CERTIFICATE_PASSWORD` - certificate password. This applies only if the certificate is encoded which is the recommended approach

This use case is perfect in a production context as it does not create any dependencies on an account

For the `user` login method you will need to create the following secrets in GitHub repo settings:

- `ADMIN_USERNAME` - username
- `ADMIN_PASSWORD` - password

This method is perfect to test your workflow, in a dev context, for personal usage. It will not work for accounts with MFA.

The workflow will overwrite the existing .sppkg if it is already deployed in the app catalog. Overwriting your sppkg file on every deployment is required to make continuous delivery of the latest version of your app which is the aim of the continuous delivery pipeline.

:::info

Run this command in the SPFx solution folder.

:::
    
## Examples

Adds a GitHub workflow for a SharePoint Framework project with `application` login method triggered on push to main.

```sh
m365 spfx project github workflow add 
```

Adds a GitHub workflow for a SharePoint Framework project with `user` login method triggered on push to main and when manually triggered. 

```sh
m365 spfx project github workflow add --manuallyTrigger --loginMethod "user"
```

Adds a GitHub workflow for a SharePoint Framework project with deployment to a site collection app catalog.

```sh
m365 spfx project github workflow add --scope "sitecollection" --siteUrl "https://some.sharepoint.com/sites/someSite"
```

## Response

The command won't return a response on success.

## More information

- Automate your CI/CD workflow using CLI for Microsoft 365 GitHub Actions: [https://pnp.github.io/cli-microsoft365/user-guide/github-actions](https://pnp.github.io/cli-microsoft365/user-guide/github-actions)
