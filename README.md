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

