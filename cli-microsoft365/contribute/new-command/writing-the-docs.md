-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Writing docs page

Each command has a corresponding documentation page. The contents of this page are almost identical to the help implemented in the command itself. This way, users working with the CLI can get help directly inside the CLI, while users interested in the capabilities of the CLI, can browse through the help pages published in our documentation. In the CLI for Microsoft 365, we extend this basic information with additional remarks and examples to help users work with the CLI. This will also be published in the terminal when users execute your command with the `--help` flag. 

All the command help files are written in [Markdown](https://www.markdownguide.org/cheat-sheet/#overview) and can be found in the folder `docs/docs/cmd`. This will have a similar look and file to the src folder structure for the commands. One difference here is that the command groups with a lot of similar commands won't be bundled in a `commands` folder. For our example, we can create a new file named `group-get.mdx` in the folder `docs/docs/cmd/spo/group`.

## Running Docusaurus locally

You can build and run our documentation site locally. The `docs` folder has an entire Node project with its own `package.json`. This also means that we have to restore the dependencies of this project by installing all modules. This can be done by navigating to the `docs` folder and running the command:

```sh
npm install
```

When this has been done, we have a simple one-liner to build and run the site locally:

:::note 

Your terminal should point to the `docs` folder.

:::

```sh
npm start
```

## Minimum help file 

With our help file created, we can start writing down the command specs. A help file for a command will have at minimum the following topics. The command name as the title, a description, the usage, options, a few examples on how to use them, and a sample response output. We'll start with the `title`, `description`, and `usage`.

````md title="docs\docs