-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Implementing unit tests

:::tip

Once you have correctly set up your local environment, you can run `npm run watch` in the background to test your changes live. This command enables live reloading, allowing you to see the effects of your modifications in real-time as you make edits to the code. This is especially useful for quickly iterating and verifying the behavior of your changes before finalizing them.

:::

Each command must be accompanied by a set of unit tests. We aim for 100% code and branch coverage in every command file. To accomplish this, the CLI for Microsoft 365 makes use of `Sinon` and `Mocha`. `Mocha` is the JavaScript test framework that's often used for testing Node.js applications. It's a widely used testing tool for both JavaScript and TypeScript projects. `Sinon`, on the other hand, will be used to test a method that is required to interact with or call other external methods. Therefore, you need a utility to spy, stub, or mock those external methods.

To get started, we will need a file to work in. Each command will have its own test file that you can work in. These are the common files found in the `src` directory and end with `*.spec.ts`. For our example, we'll create a new one based on our sample issue, which is mentioned [here](./step-by-step-guide.mdx#new-command-get-site-group). We'll name it `group-get.spec.ts`.

## Mocha basis

Each `Mocha` file that ends with `*.spec.ts` will contain several common interfaces. These will be used to execute logic before or after the test cases. Most of the time, they will be used to set up common variables or stubs and restore them afterward.

```ts title="src/m365/spo/commands/group/group-get.spec.ts"
import commands from '../../commands.js';

describe(commands.GROUP_GET, () => {
  before(() => {
    // Execute before running tests
  });

  beforeEach(() => {
    // Execute before each test case
  });
  
  afterEach(() => {
    // Execute after each test case
  });

  after(() => {
    // Execute after running tests
  });

  // All the test cases ...
}); 
```

## Sinon basis

With the basis of `Mocha` ready, we will set up the basis for `Sinon`. This will be used to spy on our results and stub our functions. Once `Sinon` has been implemented, we can start stubbing a whole bunch of common functions used by the CLI for Microsoft 365 internally. 

### Before

Before we start with the test suite, we want to make sure that the basic functions like `telemetry` and `authentication` are ignored. This will make it so functions like `restoreAuth` return a response when our code, `group-get.ts`, requires it. 

```ts title="group-get.spec.ts"
// ...
import sinon from 'sinon';
import auth from '../../../../Auth.js';
import { cli } from '../../../../cli/cli.js';
import { CommandInfo } from '../../../../cli/CommandInfo.js';
import { telemetry } from '../../../../telemetry.js';
import { pid } from '../../../../utils/pid.js';
import { session } from '../../../../utils/session.js';
import commands from '../../commands.js';
import command from './group-get.js';

describe(commands.GROUP_GET, () => {
  let commandInfo: CommandInfo;
  
  before(() => {
    sinon.stub(auth, 'restoreAuth').resolves();
    sinon.stub(telemetry, 'trackEvent').resolves();
    sinon.stub(pid, 'getProcessName').returns('');
    sinon.stub(session, 'getId').returns('');
    auth.connection.active = true;
    commandInfo = cli.getCommandInfo(command);
  });
}); 
```

### BeforeEach

`BeforeEach` will be used to execute its logic before each test. We will use this to set up the `Sinon` logger spy. This will record arguments, return values, values of `this`, and exceptions that are thrown (if any) for all its calls.

```ts title="src/m365/spo/commands/group/group-get.spec.ts"
// ...
import { Logger } from '../../../../cli/Logger.js';

describe(commands.GROUP_GET, () => {
  let log: any[];
  let logger: Logger;
  let loggerLogSpy: sinon.SinonSpy;
  // ...

  beforeEach(() => {
    log = [];
    logger = {
      log: async (msg: string) => {
        log.push(msg);
      },
      logRaw: async (msg: string) => {
        log.push(msg);
      },
      logToStderr: async (msg: string) => {
        log.push(msg);
      }
    };
    loggerLogSpy = sinon.spy(logger, 'log');
  });
}); 
```

During our test cases, we can make use of this spy together with `assert` from `Node.js` to validate our desired output.

```ts
// Used in the test cases
assert(loggerLogSpy.calledWith({ /* The required result */ }));
```

### AfterEach

When a test case is finished, this function will trigger. In our case, it's perfect to reset the `request.get` stub. As this command will make use of the SharePoint REST API, we can reset the stubbed API request and write up a different scenario for our next test case. This is required because you can only stub a function once. If you want to stub it again, you will need to reset it first.

```ts title="src/m365/spo/commands/group/group-get.spec.ts"
// ...
import request from '../../../../request.js';
import { sinonUtil } from '../../../../utils/sinonUtil.js';

describe(commands.GROUP_GET, () => {
  // ...

  afterEach(() => {
    sinonUtil.restore([
      request.get
    ]);
  });
}); 
```

### After

At the end of our test suite, we will clean up all the stubs we have set in our `before` function, and this can be done in the `after` function.

```ts title="src/m365/spo/commands/group/group-get.spec.ts"
// ...

describe(commands.GROUP_GET, () => {
  // ...

  after(() => {
    sinon.restore();
    auth.connection.active = false;
  });
}); 
```

## Test cases

Now we will start writing the test cases for several different scenarios our command can undergo. This will be accomplished with `it` functions in our test suite (within `describe`). The CLI for Microsoft 365 aims for 100% code and branch coverage in every command file.

### Basic tests

With the basis set and ready to go, we can start writing the test cases. There are a few 'basic' tests that you can implement right off the bat. This will be a test to validate the command name and another one to validate the command description.

```ts title="src/m365/spo/commands/group/group-get.spec.ts"
// ...
import assert from 'assert';

describe(commands.GROUP_GET, () => {
  // ...

  it('has the correct name', () => {
    assert.strictEqual(command.name, commands.GROUP_GET);
  });

  it('has a description', () => {
    assert.notStrictEqual(command.description, null);
  });
});
```

### Testing validation conditions

Zod validates if the option input is correct with the input we require. For our scenario, we have a condition that will check whether or not the option `id` input is a number. Because this condition can pass and fail, we will need to write two tests. One for failure and one where the condition passes.

```ts title="src/m365/spo/commands/group/group-get.spec.ts"
// ...

describe(commands.GROUP_GET, () => {
  // ...

 it('fails validation if the specified ID is not a number', async () => {
    const actual = commandOptionsSchema.safeParse({
      webUrl: 'https://contoso.sharepoint.com',
      id: 'a'
    });
    assert.strictEqual(actual.success, false);
  });

  it('passes validation when the URL is valid and the ID is passed', async () => {
    const actual = commandOptionsSchema.safeParse({
      webUrl: 'https://contoso.sharepoint.com',
      id: 7
    });
    assert.strictEqual(actual.success, true);
  });
});
```

### Achieving 100% coverage

The CLI for Microsoft 365 requires 100% code and branch coverage in every command file. We have already set up several basic tests, but now we need to go more specifically towards the command. To achieve 100% coverage, make sure that every condition is hit at least once in a test case. Continuing with our example `m365 group get`, we will write a test where we successfully fetch a group based on an associated owner group. Take a look at the sample below.

```ts title="src/m365/spo/commands/group/group-get.spec.ts"
// ...

describe(commands.GROUP_GET, () => {
  // ...
  
  it('correctly retrieves the associated owner group', async () => {
    const ownerGroupResponse = {
      Id: 3,
      IsHiddenInUI: false,
      LoginName: "Team Site Owners",
      Title: "Team Site Owners",
      PrincipalType: 8
    };

    sinon.stub(request, 'get').callsFake(async opts => {
      if (opts.url!.endsWith('/_api/web/AssociatedOwnerGroup')) {
        return ownerGroupResponse;
      }

      throw 'Invalid request';
    });

    await command.action(logger, {
      options: {
        associatedGroup: 'Owner'
      }
    });

    assert(loggerLogSpy.calledWith(ownerGroupResponse));
  });
});
```

Here, we will start by stubbing a response from the SharePoint REST API. As we make use of `request.get` in our code, we can start by stubbing this method. Next, in our code, we can make use of several GET API endpoints, so we make sure that we only mock the result for the endpoint `/_api/web/AssociatedOwnerGroup`. This is achieved by writing a condition based on the stub options. With this in order, we can safely say it's the correct endpoint and return the mocked result stated in the variable `ownerGroupResponse`. Now that this stub is created, we can execute the command with the proper option. Using the method `command.action`, we can execute the command. In this method, you'll be able to pass along the logger we initiated at the very beginning and our options needed for this command execution. Finally, we will validate the response from our command with the expected response.

### Testing API errors

When working on a command, in most scenarios, you will need to write an API call to execute a task. As API calls are known to not always return a proper result when they fail, we will include a test for this scenario. As our example only makes use of a GET endpoint, the following test will suffice.

```ts title="src/m365/spo/commands/group/group-get.spec.ts"
// ...
import { CommandError } from '../../../../Command.js';

describe(commands.GROUP_GET, () => {
  // ...

  it('handles errors correctly', async () => {
    sinon.stub(request, 'get').rejects({error: { error: { message: 'An error has occured' } } });

    await assert.rejects(command.action(logger, {
      options: {
        associatedGroup: 'Visitor'
      }
    }), new CommandError('An error has occurred'));
  });
});
```

## Validating the written tests

With everything in order, we should validate if our command reaches 100% coverage and that every test case will succeed. This can easily be done by running `npm run test` in your terminal from the project root. This will result in a list where you can see the status of each test and at the end, you will get a report of the current coverage. 

:::tip

The coverage report is exported as well to an HTML page where you can view the report in more detail. This can be found in the folder `coverage/lcov-report` and then you can open the file `index.html`.

:::

## Next step

Now that the command is fully functional and tested, we can move on to the next step. This will be the documentation of the command. This will be covered in the next chapter: [Help Page](./writing-the-docs.mdx).
