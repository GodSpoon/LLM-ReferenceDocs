-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import AsciinemaPlayer from '../src/components/AsciinemaPlayer';
import 'asciinema-player/dist/bundle/asciinema-player.css';

# CLI for Microsoft 365

Using the CLI for Microsoft 365, you can manage your Microsoft 365 tenant and SharePoint Framework projects on any platform. No matter if you are on Windows, macOS or Linux, using Bash, Cmder or PowerShell, using the CLI for Microsoft 365 you can configure Microsoft 365, manage SharePoint Framework projects and build automation scripts.

<AsciinemaPlayer src="https://asciinema.org/a/445653.cast" rows={15} idleTimeLimit={3} preload={true} loop autoplay/>

## Installation

The CLI for Microsoft 365 is distributed as an NPM package. To use it, install it globally using:

```sh
npm i -g @pnp/cli-microsoft365
```

or using yarn:

```sh
yarn global add @pnp/cli-microsoft365
```

## Getting started

Start, by configuring CLI for Microsoft 365 to your preferences. Configuration includes specifying an Microsoft Entra application registration that the CLI should use. You can choose between using an existing application registration or creating a new one. To configure the CLI, run the [setup](./cmd/setup) command:

```sh
m365 setup
```

After configuring the CLI, you can start using it. Start managing the settings of your Microsoft 365 tenant by logging in to it, using the [login](./cmd/login) command, for example:

```sh
m365 login
```

To list all available commands, type in the CLI for Microsoft 365 prompt `help`:

```sh
m365 help
```

See the [User Guide](user-guide/installing-cli.mdx) to learn more about the CLI for Microsoft 365 and its capabilities.

## Microsoft 365 Platform Community

CLI for Microsoft 365 is a [Microsoft 365 Platform Community](https://pnp.github.io) (PnP) project. Microsoft 365 Platform Community is a virtual team consisting of Microsoft employees and community members focused on helping the community make the best use of Microsoft products. CLI for Microsoft 365 is an open-source project not affiliated with Microsoft and not covered by Microsoft support. If you experience any issues using the CLI, please submit an issue in the [issues list](https://github.com/pnp/cli-microsoft365/issues).

The project is built and managed publicly on GitHub at [https://github.com/pnp/cli-microsoft365](https://github.com/pnp/cli-microsoft365) and accepts community contributions. We would encourage you to try it and [tell us what you think](https://github.com/pnp/cli-microsoft365/issues). We would also love your help! We have a number of feature requests that are a [good starting point](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) to contribute to the project.

### Community Discord server

We also have a [community Discord server](https://aka.ms/cli-m365/discord) where you can hang out, share, collaborate, and discuss more about the CLI for Microsoft 365!

<br/>
<p align="center">
  <a href="https://aka.ms/cli-m365/discord">
    <img src="https://img.shields.io/badge/Discord-aka.ms/cli--m365/discord-7289da?style=for-the-badge"
      alt="Discord" />
  </a>
</p>
