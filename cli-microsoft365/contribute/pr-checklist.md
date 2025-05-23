-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# PR Checklist

This document outlines the requirements for submitting a pull request (PR) to the project.

## General guidelines

- [ ] Ensure the build passes.
- [ ] Achieve 100% code coverage.
- [ ] The submission should match the specification.
- [ ] Maintain a single commit, or squash multiple commits.
- [ ] Use single quotes `' '` for strings.
- [ ] If submitting a sample, ensure it is properly formatted and indented.

## Coding standards

- [ ] Command options should follow the naming convention.
- [ ] The command should have a correct name
- [ ] The command class is named following the pattern `[Service][Command]Command`. For example, `SpoWebRemoveCommand`.
- [ ] Verify the command works as expected.
- [ ] List commands must have readable output in `text` mode, with each item fitting in one row of 130 characters preferably.
- [ ] Command telemetry must not track Personally Identifiable Information (PII).
- [ ] Avoid commented-out code and usage of `any` types, preferring specific types.
- [ ] Remove commands should include a `force` option.
- [ ] For bug fixes, include a test for the fixed use case.
- [ ] Avoid unnecessary retrieval of form digest.
- [ ] Handle failed promises properly when `responseType: 'json'` is used by using `handleRejectedODataJsonPromise`.
- [ ] Escape user input in XML and URLs.
- [ ] Verbose and debug outputs are logged to stdErr (`logger.logToStderr` instead of `logger.log`).
- [ ] Do not do conditional output in JSON output mode; use `defaultProperties` for defining default properties.
- [ ] For commands with multiple options where the user is required to choose one, define these options using an `optionSet` without specific validation logic in the command's validate method.
- [ ] Use `async/await` instead of `promise/then`.
- [ ] When working with `spo` commands, use `GetFileByServerRelativePath` and `GetFolderByServerRelativePath` API endpoint instead of `GetFileByServerRelativeUrl` and `GetFolderByServerRelativeUrl`.
- [ ] All tests must pass.

## Documentation

- [ ] Include an md help page.
- [ ] Reference the md help page in the table of contents.
- [ ] Start all code samples with `m365`.
- [ ] Ensure samples use long names of options rather than short ones.
- [ ] Include the marker to incorporate global options rather than listing them explicitly.
- [ ] Check for no warnings when building docs (lines that begin with `WARNING - `).
- [ ] If there is an option modifying the output, include responses for both default and modified output.
