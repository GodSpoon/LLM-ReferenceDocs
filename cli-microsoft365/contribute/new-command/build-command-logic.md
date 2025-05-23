-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Building the command

:::tip

Once you have correctly set up your local environment, you can run `npm run watch` in the background to test your changes live. This command enables live reloading, allowing you to see the effects of your modifications in real-time as you make edits to the code. This is especially useful for quickly iterating and verifying the behavior of your changes before finalizing them.

:::

To start writing the logic for the command, you will need to create a new TypeScript file. All the command services can be found in the folder `src/m365`. Here you will find all the services available within the CLI for Microsoft 365. Each service contains a subfolder named `commands` where all the service commands are located. For our example issue, mentioned [here](./step-by-step-guide.mdx#new-command-get-site-group), that will be `src/m365/spo/commands`.

:::note

When the service has a lot of commands within the `commands` folder, they will be split up into subfolders. For example, `src/m365/spo/commands/group`.

:::

When you are in the correct folder, you can create two new files: your command file `group-get.ts` and a file for the unit tests `group-get.spec.ts`.

## Minimum command file

With our two new files created, we can start working on our `group-get.ts` file. Each command in the CLI for Microsoft 365 is defined as a class extending the [Command](https://github.com/pnp/cli-microsoft365/blob/main/src/Command.ts) base class. At a minimum, a command must define `name`, `description`, and `commandAction`:

```ts title="src/m365/spo/commands/group/group-get.ts"
import commands from '../../commands.js';
import { Logger } from '../../../../cli/Logger.js';
import SpoCommand from '../../../base/SpoCommand.js';

class SpoGroupGetCommand extends SpoCommand {
  public get name(): string {
    return commands.GROUP_GET;
  }

  public get description(): string {
    return 'Gets site group';
  }

  public async commandAction(logger: Logger, args: CommandArgs): Promise<void> {
    if (this.verbose) {
      await logger.logToStderr(`Retrieving information for group in site ...`);
    }

    // Command implementation goes here
  }
}

export default new SpoGroupGetCommand();
```

Depending on your command and the service for which you're building the command, there might be a base class that you can use to simplify the implementation. For example, for SPO, you can inherit from the [SpoCommand](https://github.com/pnp/cli-microsoft365/blob/main/src/m365/base/SpoCommand.ts) base class. This class contains several helper methods to simplify your implementation.

### Include command name

When you create the minimum file, you'll get an error about a nonexistent type within `commands`. This is correct because we haven't defined the name of the command yet. Let's add this to the `commands` export located in `src/m365/spo/commands.ts`:

```ts title="src/m365/spo/commands.ts"
const prefix: string = 'spo';

export default {
  // ...
  GROUP_GET: `${prefix} group get`,
  // ...
};
```

Next, to enhance our command with options, validators, telemetry, there are a bunch of methods already available for you. When you make use of a method we order them alphabetically.

## Defining command options

Some commands require options. For example, when you want to get a group, you need to specify the site URL and the group ID. In CLI for Microsoft 365 we define options in a [Zod](https://zod.dev/) schema. Using Zod allows us to define the options in a type-safe way so that we can easily convert arguments specified by the user in the command line to objects that can be used in the command logic.

Global CLI options, such as `query`, `output`, `debug` or `verbose` are defined in the `globalOptionsZod` property. To define options specific to your command, extend the global schema with your command-specific options.

```ts title="src/m365/spo/commands/group/group-get.ts"
import { globalOptionsZod } from '../../Command.js';

export const options = globalOptionsZod
  .extend({
    webUrl: z.string(),
    id: z.number().optional(),
    name: z.string().optional(),
    associatedGroup: z.string().optional()
  })
  .strict();
```

In this example, we're adding 4 command options: `webUrl`, `id`, `name`, and `associatedGroup`. The `webUrl` option is required and must be a string. The `id`, `name`, and `associatedGroup` options are optional. Since our command doesn't support unknown options, we set the schema to strict.

Next, we define a TypeScript type for options and command args, which allows us to benefit from type-safety when working with options in the command logic.

```ts title="src/m365/spo/commands/group/group-get.ts"
import { globalOptionsZod } from '../../Command.js';

export const options = globalOptionsZod
  .extend({
    webUrl: z.string(),
    id: z.number().optional(),
    name: z.string().optional(),
    associatedGroup: z.string().optional()
  })
  .strict();
declare type Options = z.infer<typeof options>;

interface CommandArgs {
  options: Options;
}
```

Finally, we expose the options schema in the command class.

```ts title="src/m365/spo/commands/group/group-get.ts"
import { globalOptionsZod } from '../../Command.js';

export const options = globalOptionsZod
  .extend({
    webUrl: z.string(),
    id: z.number().optional(),
    name: z.string().optional(),
    associatedGroup: z.string().optional()
  })
  .strict();
declare type Options = z.infer<typeof options>;

interface CommandArgs {
  options: Options;
}

class SpoGroupGetCommand extends SpoCommand {
  // ...

  public get schema(): z.ZodTypeAny | undefined {
    return options;
  }

  public async commandAction(logger: Logger, args: CommandArgs): Promise<void> {
    if (this.verbose) {
      await logger.logToStderr(`Retrieving information for group in site at ${args.options.webUrl}...`);
    }

    // Command implementation goes here
  }
}
```

## Defining aliases

To simplify using the CLI, we often use aliases for options. For example, the `--webUrl` option can be shortened to `-u`. To define an alias for an option, we wrap the property in the `alias` function in the schema.

```ts title="src/m365/spo/commands/group/group-get.ts"
import { globalOptionsZod } from '../../Command.js';
import { zod } from '../../utils/zod.js';

export const options = globalOptionsZod
  .extend({
    webUrl: zod.alias('u', z.string()),
    id: zod.alias('i', z.number().optional()),
    name: z.string().optional(),
    associatedGroup: z.string().optional()
  })
  .strict();
```

## Defining option autocomplete

Some options require predefined values. For example, the `associatedGroup` option can only have one of the following values: `Owner`, `Member`, or `Visitor`. To define the allowed values for an option, we use enums with the `coercedEnum` helper function. This function allows users to specify the values in a case-insensitive way. In the code, the value of the `associatedGroup` option will be expressed as an enum which allows us to benefit from type-safety and support refactoring.

```ts title="src/m365/spo/commands/group/group-get.ts"
import { globalOptionsZod } from '../../Command.js';
import { zod } from '../../utils/zod.js';

enum AssociatedGroup {
  Owner = 'owner',
  Member = 'member',
  Visitor = 'visitor'
};

export const options = globalOptionsZod
  .extend({
    webUrl: zod.alias('u', z.string()),
    id: zod.alias('i', z.number().optional()),
    name: z.string().optional(),
    associatedGroup: zod.coercedEnum(AssociatedGroup).optional()
  })
  .strict();
```

## Option validation

The options that users specify won't always be correct. So instead of passing faulty values to the CLI, we can add logic to validate the input first. This allows us to fail fast and offer users the ability to correct their input before continuing.

Zod automatically validates primitive values, which means that you only need to add 'business' validation logic. Validation is implemented using Zod refinements on the specific property. For example, to validate that the specified URL is a SharePoint URL, use:

```ts title="src/m365/spo/commands/group/group-get.ts"
import { globalOptionsZod } from '../../Command.js';
import { validation } from '../../utils/validation.js';
import { zod } from '../../utils/zod.js';

enum AssociatedGroup {
  Owner = 'owner',
  Member = 'member',
  Visitor = 'visitor'
};

export const options = globalOptionsZod
  .extend({
    webUrl: zod.alias('u', z.string().refine(url => validation.isValidSharePointUrl(url) === true, url => ({
      message: `Specified URL ${url} is not a valid SharePoint URL`,
    }))),
    id: zod.alias('i', z.number().optional()),
    name: z.string().optional(),
    associatedGroup: zod.coercedEnum(AssociatedGroup).optional()
  })
  .strict();
```

A refinement takes two arguments: a predicate function and an error object. The predicate function is used to validate the input, and the error object is used to define the error message that will be displayed when the input is invalid.

## Option sets

Option sets are used to ensure that only one option has a value from a set of options. When no option is used, the command will return an error, and the same goes when multiple of these options are used. To use option sets, add a Zod refinement on the whole schema, which gives you access to all schema properties.

```ts title="src/m365/spo/commands/group/group-get.ts"
import { globalOptionsZod } from '../../Command.js';
import { validation } from '../../utils/validation.js';
import { zod } from '../../utils/zod.js';

enum AssociatedGroup {
  Owner = 'owner',
  Member = 'member',
  Visitor = 'visitor'
};

export const options = globalOptionsZod
  .extend({
    webUrl: zod.alias('u', z.string().refine(url => validation.isValidSharePointUrl(url) === true, url => ({
      message: `Specified URL ${url} is not a valid SharePoint URL`,
    }))),
    id: zod.alias('i', z.number().optional()),
    name: z.string().optional(),
    associatedGroup: zod.coercedEnum(AssociatedGroup).optional()
  })
  .strict();
declare type Options = z.infer<typeof options>;

interface CommandArgs {
  options: Options;
}

class SpoGroupGetCommand extends SpoCommand {
  // ...

  public get schema(): z.ZodTypeAny | undefined {
    return options;
  }

  public getRefinedSchema(schema: typeof options): z.ZodEffects<any> | undefined {
    return schema
      .refine(options => options.id !== undefined || options.name !== undefined && !(options.id !== undefined && options.name !== undefined), {
        message: `Either id or name is required, but not both.`
      });
  }

  public async commandAction(logger: Logger, args: CommandArgs): Promise<void> {
    if (this.verbose) {
      await logger.logToStderr(`Retrieving information for group in site at ${args.options.webUrl}...`);
    }

    // Command implementation goes here
  }
}
```

In the `refine` function, you define how the option set should be validated. In this case, we check if either `id` or `name` is defined, but not both. If both are defined, the command returns an error. You can use different logic, depending on the requirements of your command.

## Command action

After everything is written for our options, we can start to write the logic required to execute the command. This will be done, as mentioned before, in the method `commandAction`. The command will start with a verbose message explaining what we are about to do, and then we start writing the command logic. Here you can write several new methods to be called in `commandAction` to keep the code a bit tidier.

When writing your code, there are a few pointers to keep in mind:

- It's recommended to add some verbose logging along the path of your command. This can keep the user informed about what you are doing.
- Async tasks will be written with async/await.
- When an endpoint errors, make sure that the output is returned to the user.

```ts title="src/m365/spo/commands/group/group-get.ts"
class SpoExampleListCommand extends Command {
  // ...

  public async commandAction(logger: Logger, args: CommandArgs): Promise<void> {
    if (this.verbose) {
      await logger.logToStderr(`Retrieving information for group in site at ${args.options.webUrl}...`);
    }

    // ...
    // Command logic
    // ...

    try {
      const groupInstance = await request.get(requestOptions);
      await logger.log(groupInstance);
    }
    catch (err: any) {
      this.handleRejectedODataJsonPromise(err);
    }
  }
}
```

After this, the new command will be fully functional. During development, it can be useful to have `npm run watch` running in the background. This builds the entire project first. After this, a watcher will ensure that every time a file is saved, an incremental build is triggered. This means that not the entire project is rebuilt, but only the changed files. That way, you can easily apply new changes to the command and test it out locally.

In the end, your command file will look something like this: [group-get.ts](https://github.com/pnp/cli-microsoft365/blob/main/src/m365/spo/commands/group/group-get.ts)

## Running it locally

Before creating a PR, you should test your code locally. This will help you catch bugs, errors, and performance issues early on and ensure that the code functions as intended before it is made available to real users. You can execute `npm run watch` to start a live watcher. This will build the entire project first, and after that, a watcher will ensure that every time a file is saved, an incremental build is triggered. This means that not the entire project is rebuilt, but only the changed files. This makes it easy to make quick changes and test them immediately after saving them.

If this command fails, be sure to check if your environment has been set up correctly following the guidelines of [Setting up your local project](../environment-setup.mdx#setting-up-your-local-project) or if you use a dev container or GitHub Codespaces: [GitHub Codespaces & Visual Studio Remote Development Container](./../github-codespaces-and-devcontainer.mdx).

## Next step

Now that the command is fully functional we will need to add some tests to ensure that the command works as expected. This will be explained in the next chapter: [Unit Tests](./unit-tests.mdx).
