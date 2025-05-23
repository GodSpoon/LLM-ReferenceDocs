-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# How to debug locally

Debugging code on a local device is handy because it allows for real-time testing and quicker identification and resolution of bugs and errors. Local debugging provides direct access to the code and environment, enabling developers to step through the code, examine variables, and test changes in real time. This leads to faster iteration, improved accuracy, and increased efficiency in the development process. Here are a few steps on how to debug different areas of the CLI for Microsoft 365 project.

:::note

This guide will be mainly focused on how to debug the project using Visual Studio Code

:::

## Debugging a command

One of the key features of Visual Studio Code is its great debugging support. VS Code's built-in debugger helps accelerate your edit, compile, and debug loop. We can fully use this to our advantage to start debugging a CLI for Microsoft 365 command. 

To start, we will define which command we want to debug. This can be achieved by navigating to `.vscode/launch.json`. This will look a bit like the following. 

```json title=".vscode/launch.json"
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "pwa-node",
      "request": "launch",
      "name": "Debug CLI",
      "skipFiles": [
        "<node_internals>/**"
      ],
      "program": "${workspaceFolder}/dist/index.js",
      // add here the name of the command to debug, eg. to debug
      // 'm365 spo site get --url /', you'd use:
      // "args": ["spo", "site", "get", "--url", "/"]
      // after debugging, revert changes so that they won't end up in your PR
      "args": []
    },
    {
      "type": "node",
      "request": "launch",
      "name": "Debug Tests",
      "program": "${workspaceFolder}/node_modules/mocha/bin/_mocha",
      "args": [],
      "skipFiles": [
        "<node_internals>/**"
      ]
    }
  ]
}
```

Under the configuration named `Debug CLI`, we can define the command we want to debug in the `args` section. As the comments explain in the configuration `Debug CLI`, you will need to define the entire command, including the options, as a string array. E.g. we want to test the following command.

```bash
m365 spo group get --id 1 --webUrl "https://contoso.sharepoint.com/sites/contoso"
```

Translating this to the `args` array, it will look like this:

```json
args: ["spo", "group", "get", "--id", "1", "--webUrl", "https://contoso.sharepoint.com/sites/contoso"]
```

With the `args` array in place, we can save the file and run the debugger. To run the debugger we can simply press the `F5` button. This will start the debugger and a debug console will appear, logging the output of the command executed. Breakpoints can be set in the code and they will be hit when the debugger is activated. 

:::note

If the debugger doesn't appear. You can also run it by opening the `Run and Debug` tab in the activity bar. 
Also, be sure that the debug configuration is set to `Debug CLI` and **not** to `Debug Tests`

:::

## Debugging tests

With the CLI for Microsoft 365 requiring a code coverage of 100%, the chance exists that you will need to troubleshoot certain tests. This can be achieved in several ways.

### Using .only

One way is to run just your tests, either add `.only` to your test suite (eg. `describe.only(commands.MY_COMMAND)`) or update the glob in the `.mocharc.json` file, `spec` property to match the path to your test files, like `dist/m365/spo/commands/group/**/*.spec.js`. Once you're done with your unit tests, run `npm test` to verify that you're covering all code and branches of your command with your unit tests.

```ts 
// ...

// If we want to run this test suite, we can add .only after 'describe':
describe.only(commands.GROUP_GET, () => {
  // ...

  // If we want to run only one test, we can add .only after 'it':
  it.only('has correct name', () => {
    assert.strictEqual(command.name.startsWith(commands.GROUP_GET), true);
  });

  // ...
}
```

With this in place, be sure that your changes are compiled with `npm run build` or a `npm run watch`. Then you can open the debugger, either using the `F5` button or by opening the `Run and Debug` tab in the activity bar. 

:::note

Be sure that the debug configuration is set to `Debug Tests` and **not** to `Debug CLI`.

:::

### Using Test Explorer UI VS Code extension

[Test Explorer](https://marketplace.visualstudio.com/items?itemName=hbenl.vscode-test-explorer) provides an extensible user interface for running your tests in VS Code. This will add an extra tab in your activity bar named `Testing`. When you open this, you should see all the commands written for the CLI for Microsoft 365, grouped by their utility. Here you have the option to run all the tests, by clicking the play button next to the title. Or we can only run a certain command, by clicking the play button next to the command name. This will visually display the status of every command. If a command fails, you can select it and view the logs to see what went wrong. You can also go even deeper by starting a debugger for a single test.
