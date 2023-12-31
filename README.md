# eslint-fe26labs

![Build](https://github.com/github/docs/actions/workflows/main.yml/badge.svg)

This package provides FE26 Labs .eslintrc as an extensible shared config. 

## Installation

We export one main ESLint configuration for your usage.

### eslint-config-fe26labs

Our default export extends the eslint-config-airbnb ruleset. It therefore contains all of our ESLint rules, including ECMAScript 6+ and React. It requires `eslint-config-airbnb`, `eslint`, `eslint-plugin-import`, `eslint-plugin-react`, and `eslint-plugin-jsx-a11y`.

If you use yarn, run `npm info "eslint-config-fe26labs@latest" peerDependencies` to list the peer dependencies and versions, then run `yarn add --dev <dependency>@<version>` for each listed peer dependency. See below for npm instructions.

1. Install the correct versions of each package, which are listed by the command:

  ```sh
  npm info "eslint-config-fe26labs@latest" peerDependencies
  ```

  Linux/OSX users can run

  ```sh
  (
    export PKG=eslint-config-fe26labs;
    npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG@latest"
  )
  ```

  Which produces and runs a command like:

  ```sh
  npm install --save-dev eslint-config-fe26labs eslint-config-airbnb@^#.#.# eslint@^#.#.# eslint-plugin-jsx-a11y@^#.#.# eslint-plugin-import@^#.#.# eslint-plugin-react@^#.#.#
  ```

  Windows users can either install all the peer dependencies manually, or use the [install-peerdeps](https://github.com/nathanhleung/install-peerdeps) cli tool.

  ```sh
  npm install -g install-peerdeps
  install-peerdeps --dev eslint-config-fe26labs
  ```

  The cli will produce and run a command like:

  ```sh
  npm install --save-dev eslint-config-fe26labs eslint-config-airbnb@^#.#.# eslint@^#.#.# eslint-plugin-jsx-a11y@^#.#.# eslint-plugin-import@^#.#.# eslint-plugin-react@^#.#.#
  ```

2. Add `"extends": "fe26labs"` to your .eslintrc

## Linting

You can make sure this module is linting correctly by adding the following script to the package.json file, which will lint all files inside of the package. Be warned however that this will lint all the files, including ones you may not want it to and therefore take much longer than expected.

 ```javascript
  "scripts": {
    "lint": "eslint .",
  }
  ```
This script can then be called from command line from npm in the usual manner and will output the broken rules to the console.

 ```sh
  npm run lint
  ```
This command can also be run as part of the CI pipeline and cause a build to fail if the linting rules are not matched.

### ESLint Ignore File

The linting script currently lints all files, which is not advised. This can be changed by specifying a particular folder, such as `./src` or by adding an ESLint ignore file `.elintignore`. A [default ignore file](./templates/.eslintignore) is included in this page and should be included by all repos by FE26 Labs.


## Improving this config

Consider adding test cases if you're making complicated rules changes, like anything involving regexes.

## License

Copyright (c) FE26 Labs. All rights reserved.

Licensed under the [MIT](./LICENSE) License.
