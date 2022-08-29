# testingjavascript.com

## Notes

### Part 1 - Creating your own test runner

Explains how you can create a simple test runner to understand the basics of what `jest` is doing under the hood

### Part 2 - Static analysis

Goes over tools like `eslint`, `typescript`, `prettier`, and `husky` to show how tooling can eliminate the need for manual testing of code.

Eslint by default expects ECMAScript5

Important to install and configure `eslint` in a project to get all the benefits.

`"extends": ["eslint:recommended"]` is the default recommended rule set by eslint.

`"extends": ["eslint:recommended", "eslint-config-prettier"],` is great if you're using prettier as well, this prevents clashes between eslint and prettier.

Using a `--` inside of a script tells package.json to forward on the following flags to the command you're calling

```json
"scripts": {
  "prettier": "prettier \"**/*.+(js|json)\"",
  "format": "npm run prettier -- --write",
  "check-format": "npm run prettier -- --list-different"
}
```

`jest.spyOn` doesn't working well with es6 import syntax. Instead use `jest.mock`

Snapshots are good to use for non-html files as well! Saves explicitly stating the expected result.

`"test:debug": "node --inspect-brk ./node_modules/jest/bin/jest.js --runInBand --watch"` - Allows us to debug jest tests while they are running.

After running go to `chrome://inspect`, click on `inspect` which will open the chrome developer tools.

Add `--coverage` to jest call.
