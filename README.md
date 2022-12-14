# amancio
Mand in Brasil 


# Codacy documentation

[![MkDocs](https://github.com/codacy/docs/actions/workflows/mkdocs.yml/badge.svg)](https://github.com/codacy/docs/actions/workflows/mkdocs.yml) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/5e8bce49e0df4be8a880f2df02759d88)](https://app.codacy.com/gh/codacy/docs/dashboard?utm_source=github.com&utm_medium=referral&utm_content=codacy/docs&utm_campaign=Badge_Grade)

[<span class="skip-vale">https://docs.codacy.com</span>](https://docs.codacy.com)

## Contributing to the documentation

Contributions to the documentation are <span class="skip-vale">very</span> welcome!

See [CONTRIBUTING.md](CONTRIBUTING.md) to:

-   Set up your environment to preview your changes locally
-   Follow the Markdown conventions used in this repository
-   Deploy updates to the documentation or release new documentation versions

By participating in this project you are expected to adhere to the [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

## <span class="skip-vale">What is</span> Codacy

[Codacy](https://www.codacy.com/) is an automated code review tool that monitors your technical debt, helps you improve your code quality, teaches best practices to your developers, and helps you save time in code reviews.

### Among Codacy's features

-   Identify new static analysis issues
-   Commit and pull request analysis with GitHub, Bitbucket, and GitLab
-   Auto comments on commits and pull requests
-   Integrations with Slack and Jira
-   Track issues in code style, security, error proneness, performance, unused code and other categories

Codacy also helps keep track of code coverage, code duplication, and code complexity.

Codacy supports PHP, Python, Ruby, Java, JavaScript, and Scala, [among others](https://docs.codacy.com/getting-started/supported-languages-and-tools/).

### Free for Open Source

Codacy is free for Open Source projects.

# Create a JavaScript Action

<p align="center">
  <a href="https://github.com/actions/javascript-action/actions"><img alt="javscript-action status" src="https://github.com/actions/javascript-action/workflows/units-test/badge.svg"></a>
</p>

Use this template to bootstrap the creation of a JavaScript action.:rocket:

This template includes tests, linting, a validation workflow, publishing, and versioning guidance.

If you are new, there's also a simpler introduction.  See the [Hello World JavaScript Action](https://github.com/actions/hello-world-javascript-action)

## Create an action from this template

Click the `Use this Template` and provide the new repo details for your action

## Code in Main

Install the dependencies

```bash
npm install
```

Run the tests :heavy_check_mark:

```bash
$ npm test

 PASS  ./index.test.js
  ✓ throws invalid number (3ms)
  ✓ wait 500 ms (504ms)
  ✓ test runs (95ms)
...
```

## Change action.yml

The action.yml defines the inputs and output for your action.

Update the action.yml with your name, description, inputs and outputs for your action.

See the [documentation](https://help.github.com/en/articles/metadata-syntax-for-github-actions)

## Change the Code

Most toolkit and CI/CD operations involve async operations so the action is run in an async function.

```javascript
const core = require('@actions/core');
...

async function run() {
  try {
      ...
  }
  catch (error) {
    core.setFailed(error.message);
  }
}

run()
```

See the [toolkit documentation](https://github.com/actions/toolkit/blob/master/README.md#packages) for the various packages.

## Package for distribution

GitHub Actions will run the entry point from the action.yml. Packaging assembles the code into one file that can be checked in to Git, enabling fast and reliable execution and preventing the need to check in node_modules.

Actions are run from GitHub repos.  Packaging the action will create a packaged action in the dist folder.

Run prepare

```bash
npm run prepare
```

Since the packaged index.js is run from the dist folder.

```bash
git add dist
```

## Create a release branch

Users shouldn't consume the action from master since that would be latest code and actions can break compatibility between major versions.

Checkin to the v1 release branch

```bash
git checkout -b v1
git commit -a -m "v1 release"
```

```bash
git push origin v1
```

Note: We recommend using the `--license` option for ncc, which will create a license file for all of the production node modules used in your project.

Your action is now published! :rocket:

See the [versioning documentation](https://github.com/actions/toolkit/blob/master/docs/action-versioning.md)

## Usage

You can now consume the action by referencing the v1 branch

```yaml
uses: actions/javascript-action@v1
with:
  milliseconds: 1000
```

See the [actions tab](https://github.com/actions/javascript-action/actions) for runs of this action! :rocket:


<summary><b><i>Looking


# tslint-to-eslint-config

[![Code Style: Prettier](https://img.shields.io/badge/code_style-prettier-e72163.svg)](https://prettier.io)
![Coverage: 100%](https://img.shields.io/badge/coverage-100%25-orange.svg)
![TypeScript: Strict](https://img.shields.io/badge/typescript-strict-yellow.svg)
[![NPM version](https://badge.fury.io/js/tslint-to-eslint-config.svg)](http://badge.fury.io/js/tslint-to-eslint-config)
[![Circle CI](https://img.shields.io/circleci/build/github/typescript-eslint/tslint-to-eslint-config.svg)](https://circleci.com/gh/typescript-eslint/tslint-to-eslint-config)
[![Join the chat at https://gitter.im/tslint-to-eslint-config/community](https://img.shields.io/badge/chat-gitter-informational.svg)](https://gitter.im/tslint-to-eslint-config/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Speed: Blazingly Fast](https://img.shields.io/badge/speed-blazingly_fast-blueviolet.svg)](#)

Converts your TSLint configuration to the closest reasonable ESLint equivalent.

👉 Did you know [TSLint is deprecated](https://github.com/palantir/tslint/issues/4534)?
Hooray!
Use `tslint-to-eslint-config` to expedite migrating your project onto ESLint.

Consider taking a peek at the relevant documentation: 🤔

-   [ESLint](https://eslint.org/docs) itself
-   [typescript-eslint](https://typescript-eslint.io), which allows TypeScript files to be linted by ESLint

## Usage

> ⚠ Coming from Angular? Use **[angular-eslint](https://github.com/angular-eslint/angular-eslint#migrating-an-angular-cli-project-from-codelyzer-and-tslint)** instead to coordinate around this tool and others.

```shell
npx tslint-to-eslint-config
```

_⚡ (wow, so simple!) ⚡_

The `tslint-to-eslint-config` command reads in any existing linter, TypeScript, and package configuration files, then creates an `.eslintrc.js` result based on them.

For any TSLint rules with corresponding ESLint equivalents, those equivalents will be used in the new configuration.
TSLint rules without ESLint equivalents will be wrapped with [eslint-plugin-tslint](https://github.com/typescript-eslint/typescript-eslint/tree/master/packages/eslint-plugin-tslint).

> Requires Node 14+ (LTS) and TSLint 5.18+

### FAQs

We **strongly** advise reading [docs/FAQs.md](./docs/FAQs.md) before planning your conversion from TSLint to ESLint.

### CLI Flags

Each of these flags is optional:

-   **[`comments`](#comments)**: TypeScript configuration or file glob path(s) to convert TSLint rule flags to ESLint within.
-   **[`config`](#config)**: Path to print the generated ESLint configuration file to.
-   **[`editor`](#editor)**: Path to an editor configuration file to convert linter settings within.
-   **[`eslint`](#eslint)**: Path to an ESLint configuration file to read settings from.
-   **[`package`](#package)**: Path to a package.json file to read dependencies from.
-   **[`prettier`](#prettier)**: Add [`eslint-config-prettier`](https://github.com/prettier/eslint-config-prettier) to the plugins list.
-   **[`tslint`](#tslint)**: Path to a TSLint configuration file to read settings from.
-   **[`typescript`](#typescript)**: Path to a TypeScript configuration file to read TypeScript compiler options from.

#### `comments`

```shell
npx tslint-to-eslint-config --comments
```

_Default: none_

Indicates to convert from [TSLint rule flags](https://palantir.github.io/tslint/usage/rule-flags) to [ESLint inline comments](https://eslint.org/docs/user-guide/configuring#disabling-rules-with-inline-comments).
Comments such as `// tslint:disable: tslint-rule-name` will be converted to equivalents like `// eslint-disable eslint-rule-name`.

If passed without arguments, respects the `excludes`, `files`, and `includes` in your TypeScript configuration.

If passed a single file path ending with `.json`, that is treated as a TypeScript configuration file describing with files to convert.

```shell
npx tslint-to-eslint-config --comments tsconfig.json
```

If passed any other arguments, those are treated as glob paths for file paths to convert:

```shell
npx tslint-to-eslint-config --comments 'src/**/*.ts'
```

#### `config`

```shell
npx tslint-to-eslint-config --config .eslintrc.json
```

_Default: `.eslintrc.js`_

Path to print the generated ESLint configuration file to.

The file extension of this path will be used to determine the format of the created file:

-   `.js` file paths will be written `module.exports = ...` JavaScript
-   Other file paths will default to JSON

#### `editor`

```shell
npx tslint-to-eslint-config --editor ./path/to/.vscode/settings.json
```

_Default: `.vscode/settings.json`_

Path to an editor configuration file to convert settings settings within.
Any VS Code style editor settings for TSLint will be converted to their ESLint equivalents.

#### `eslint`

```shell
npx tslint-to-eslint-config --eslint ./path/to/eslintrc.js
```

_Default: `--config`'s value_

Path to an ESLint configuration file to read settings from.
The generated ESLint configuration file will include any settings `import`ed from this file.

#### `package`

```shell
npx tslint-to-eslint-config --package ./path/to/package.json
```

_Default: `package.json`_

Path to a `package.json` file to read dependencies from.
This will help inform the generated ESLint configuration file's [env](https://eslint.org/docs/user-guide/configuring#specifying-parser-options) settings.

#### `prettier`

```shell
npx tslint-to-eslint-config --prettier
```

_Default: `false`_

Add [`eslint-config-prettier`](https://github.com/prettier/eslint-config-prettier) to the list of ESLint plugins.
We [highly recommend](./docs/FAQs.md#should-i-use-prettier) you use [Prettier](http://prettier.io) for code formatting.

When `--prettier` isn't enabled:

-   If the output configuration already doesn't enable any formatting rules, it'll extend from `eslint-config-prettier`.
-   Otherwise, a CLI message will suggest running with `--prettier`.

#### `tslint`

```shell
npx tslint-to-eslint-config --tslint ./path/to/tslint.json
```

_Default: `tslint.json`_

Path to a TSLint configuration file to read settings from.
This file is piped into TSLint's `--print-config` to generate the list of rules to enable in the generated ESLint configuration file.

#### `typescript`

```shell
npx tslint-to-eslint-config --typescript ./path/to/tsconfig.json
```

_Default: `tsconfig.json`_

Path to a TypeScript configuration file to read TypeScript compiler options from.
This will help inform the generated ESLint configuration file's [env](https://eslint.org/docs/user-guide/configuring#specifying-parser-options) settings.

## Node API

You can use `tslint-to-eslint-config` programmatically via its exported functions.
See [docs/API](./docs/API.md) for details.

```ts
import { convertLintConfig } from "tslint-to-eslint-config";

const result = await convertLintConfig();
```

## Development

See the [Code of Conduct](./.github/CODE_OF_CONDUCT.md) and [general development docs](./docs/Development.md). 💖


