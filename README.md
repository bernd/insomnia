# Unetus API Client

[![license](https://img.shields.io/github/license/bernd/unetus.svg)](LICENSE)

Unetus is an open-source, cross-platform API client for GraphQL, REST, WebSockets, Server-sent events and gRPC.

![Unetus API Client](https://raw.githubusercontent.com/bernd/unetus/main/screenshots/main.png)

## ⚠ DISCLAIMER ⚠

Unetus is a fork of the [Insomnia](https://github.com/Kong/insomnia) project.

TLDR: You probably want to use [bruno](https://www.usebruno.com/) instead of this project!

I created this fork because I am not yet ready to change to a different tool
and loose all my saved configurations.

This is a hobby project!

My plan is to keep this fork low maintenance. That means I will mainly keep
electron and other dependencies up-to-date and fix smaller bugs if I can.
I will not spend time extending or refactoring the code base.
I am pretty happy with the existing features.

Here's the deal:

- I will accept bug reports, but I can't promise a timely response.
- I will accept pull-requests to fix bugs, but I can't promise a timely response.
- I will most probably not accept feature requests.
- I will not accept pull-requests that do large refactorings.

If that works for you: Welcome! 👋

Please see the [contributing guidelines](CONTRIBUTING.md) for details about
bug reports and feature requests.

## Download

Unetus is available for Mac, Windows, and Linux and can be downloaded
from the [release page](https://github.com/bernd/unetus/releases).

## Bugs and Feature Requests

Have a bug or a feature request? First, read the
[issue guidelines](CONTRIBUTING.md#using-the-issue-tracker) and search for existing and closed issues. If your problem is not addressed yet, [please open a new issue](https://github.com/bernd/unetus/issues).

## Contributing

Please read through our [contributing guidelines](CONTRIBUTING.md) and [code of conduct](CODE_OF_CONDUCT.md). Included are directions for opening issues, coding standards, and notes on development.

## Develop Unetus

Development on Unetus can be done on Mac, Windows, or Linux as long as you have [Node.js](https://nodejs.org) and [Git](https://git-scm.com/). See the `.nvmrc` file located in the project for the correct Node version.

<details>
<summary>Initial Dev Setup</summary>

This repository is structured as a monorepo and contains many Node.JS packages. Each package has its own set of commands, but the most common commands are available from the root [`package.json`](package.json) and can be accessed using the `npm run …` command. Here are the only three commands you should need to start developing on the app.

```shell
# Install and Link Dependencies
npm i

# Run Lint
npm run lint

# Run type checking
npm run type-check

# Run Tests
npm test

# Start App with Live Reload
npm run dev
```

### Linux

If you are on Linux, you may need to install the following supporting packages:

<details>
<summary>Ubuntu/Debian</summary>

```shell
# Update library
sudo apt-get update

# Install font configuration library & support
sudo apt-get install libfontconfig-dev
```

</details>

<details>
<summary>Fedora</summary>

```shell
# Install libcurl for node-libcurl
sudo dnf install libcurl-devel
```

</details>

Also on Linux, if Electron is failing during the install process, run the following

```shell
# Clear Electron install conflicts
rm -rf ~/.cache/electron
```

### Windows

If you are on Windows and have problems, you may need to install [Windows Build Tools](https://github.com/felixrieseberg/windows-build-tools)

</details>

<details>
<summary>Editor Requirements</summary>

You can use any editor you'd like, but make sure to have support/plugins for the following tools:

- [ESLint](http://eslint.org/) - For catching syntax problems and common errors
- [JSX Syntax](https://facebook.github.io/react/docs/jsx-in-depth.html) - For React components

</details>

## Develop Inso CLI

- `npm i`
- Start the compiler in watch mode: `npm run inso-start`
- Run: `./packages/insomnia-inso/bin/inso -v`

## Community Projects

- [Insomnia Documenter](https://github.com/jozsefsallai/insomnia-documenter) - Generate beautiful API documentation pages using the [documenter plugin](https://insomnia.rest/plugins/insomnia-plugin-documenter) or your Insomnia export file.
- [GitHub API Spec Importer](https://github.com/swinton/github-rest-apis-for-insomnia) - A complete set of GitHub REST API route specifications that can be imported straight into Unetus.
- [Swaggymnia](https://github.com/mlabouardy/swaggymnia) - Generate [Swagger](https://swagger.io/) documentation for your existing API in Unetus.

## Acknowledgements

Unetus is a fork of the [Insomnia](https://github.com/Kong/insomnia) project.

## License

[MIT](LICENSE) &copy; 2016-2023 [Insomnia](https://insomnia.rest)
<br/>
[MIT](LICENSE) &copy; Unetus Contributors
