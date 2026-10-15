# Local build and test

Use the committed package-lock.json and a Node version supported by package.json
(`^18.19 || >=20.0`; the existing test workflow uses 18.19). New runtime choices
must also account for the Node release support policy.

```sh
npm ci
npm test
npm run lint
node src/cli.js -i test-positive/state1.mmd -o /tmp/mermaid-state1.svg
```

`npm ci` runs prepare (`tsc && vite build`) and Puppeteer may download a browser.
An offline or restricted environment needs those dependencies and a compatible
browser available first. Record unavailable checks as NOT RUN/BLOCKED.
For an existing Chromium installation see
[the browser setup guide](docs/already-installed-chromium.md).
The output above is a derived preview and should stay outside the checkout.

The normal public-dependency workflow in `.github/workflows/test.yml` does not
require adding a personal access token or a private registry configuration.
The former `test/state1.mmd` example pointed to a nonexistent directory.

## Historical instructions (not the current setup procedure)

The original instructions below are preserved for reference. Do not follow their
token/login steps for the public dependency workflow above, and never commit
credentials or a credential-bearing .npmrc file.

# Simple steps to test this locally

1. Add a .npmrc file

```
registry=https://registry.npmjs.com/
@mermaid-js:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken="YOUR-TOKEN"
```

Generate the auth token from the github profile page => settings => developer settings => personal access tokens. Click on the button “Generate new token” and check the checkboxes concerning repo and github registry.

Instead of creating a .npmrc file on your own you can also use npm login --registry=https://npm.pkg.github.com which gives you an interactive prompt for entering your credentials.

1. Do `npm install`

```sh
npm install
```

2. Run the script like below:

```sh
node src/cli.js -i test/state1.mmd
```
