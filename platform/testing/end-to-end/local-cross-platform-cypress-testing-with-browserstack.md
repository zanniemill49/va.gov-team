# Local Cross-Platform e2e Cypress Test Execution with BrowserStack

BrowserStack allows you to run your Cypress tests locally via the [BrowserStack Cypress CLI](https://www.browserstack.com/docs/automate/cypress/cli-reference) on over 2000 real devices and browsers. Your tests are uploaded to BrowserStack where they are executed, and the results are displayed in the CLI and in the BrowserStack Automate Dashboard app.

This document details the steps necessary to get BrowserStack setup locally so you can quickly start running your `vets-website` Cypress tests against the platforms we support. It also includes a list of helpful resources.

## Getting Started

### Step 1: Install the BrowserStack Cypress CLI

Install the CLI via npm:

```
npm install -g browserstack-cypress-cli
```

### Step 2: Configure `browserstack.json`

Run the following command to generate a sample `browserstack.json` file in the root directory of your `vets-website` installation:

```
browserstack-cypress init
```

Replace the contents of the sample `browserstack.json` file with the following template that is configured with the platforms (browser/OS combos) and the Cypress version you should run your tests against. All you need to do is replace the values for the `username` and `access_key` keys with your credentials.

```javascript
{
    "auth": {
        "username": "<your_username>",
        "access_key": "<your_access_key>"
    },
    "browsers": [
        {
            "browser": "chrome",
            "os": "Windows 10",
            "versions": [
                "latest",
                "latest-1"
            ]
        },
        {
            "browser": "firefox",
            "os": "Windows 10",
            "versions": [
                "latest",
                "latest-1"
            ]
        },
        {
            "browser": "edge",
            "os": "Windows 10",
            "versions": [
                "latest",
                "latest-1"
            ]
        },
        {
            "browser": "chrome",
            "os": "OS X Mojave",
            "versions": [
                "latest",
                "latest-1"
            ]
        },
        {
            "browser": "firefox",
            "os": "OS X Mojave",
            "versions": [
                "latest",
                "latest-1"
            ]
        }
    ],
    "run_settings": {
        "cypress_config_file": "./config/cypress.json",
        "project_name": "Vets Website",
        "cypress_version": "6",
        "parallels": 5,
        "headless": true
    },
    "connection_settings": {
        "local": true,
        "local_identifier": null
    },
    "disable_usage_reporting": false
}
```

Please note: The VA is currently subscribed to a 5 parallel running thread plan. At any time, we can execute a maximum of 10 tests on BrowserStack (5 Running + 5 Queued). Any further tests triggered will be terminated with the exception `All parallel tests are currently in use including Queued Tests'`.

### Step 3: Setup Local Testing

1. [Download the Local binary](https://www.browserstack.com/docs/automate/cypress/local-testing#setting-up-local-testing)
2. Unzip `BrowserStackLocal-darwin-x64.zip` and put the `BrowserStackLocal` executable in the directory of your choosing
3. `cd` into the directory
4. Enter the following command (replace `<your_access_key>` with your `access_key`) to establish a Local Testing connection:

```
./BrowserStackLocal --key <your_access_key>
```

If the connection is successful you will see messages like the following logged to your console:

```
Thu Feb 04 2021 10:43:48 GMT-0500 (Eastern Standard Time) -- BrowserStackLocal v8.2

Thu Feb 04 2021 10:43:49 GMT-0500 (Eastern Standard Time) -- [WARNING] Detected instance of BrowserStackLocal Application, running in onlyAutomate mode to avoid port clash
Thu Feb 04 2021 10:43:49 GMT-0500 (Eastern Standard Time) -- Skipping initialisation of configuration console because: port already in use by another Binary
Thu Feb 04 2021 10:43:50 GMT-0500 (Eastern Standard Time) -- [SUCCESS] You can now access your local server(s) in our remote browser

Thu Feb 04 2021 10:43:50 GMT-0500 (Eastern Standard Time) -- Press Ctrl-C to exit
```

### Step 4: Run Your Tests

To run your tests, enter the following command:

```
browserstack-cypress run --sync
```

You can also use the `--spec` param to for specific spec files:

```
# Run a single spec instead of everything
browserstack-cypress run --sync --specs "cypress/integration/examples/actions.spec.js"

# Run all tests matching the regex / glob
browserstack-cypress run --sync --specs "cypress/integration/login/**/*"

# Run multiple spec files
browserstack-cypress run --sync --specs "cypress/integration/examples/actions.spec.js,cypress/integration/examples/files.spec.js"
```

For a list of other CLI commands and arguments see the BrowserStack CLI reference.
https://www.browserstack.com/docs/automate/cypress/cli-reference

## Resources

List to come...
