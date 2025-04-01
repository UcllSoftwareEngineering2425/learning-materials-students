# Running E2E tests headless

## 1. Introduction

Up until now, we have been running our E2E tests in a browser window.

This is great for debugging, but it's not ideal for running tests in a CI/CD pipeline.
In a CI/CD pipeline, you want to run your tests headless, without a browser window.
This is faster and more reliable because there is no UI-rendering involved, what shortens the build time.

## 2. Acceptance Criteria

1. All E2E tests can be run headless.

## 3. Implementation Details

From the root of the front-end project, you should be able to run all E2E tests in headless mode.
Luckily, this is a very easy step to take. Cypress already offers the command `cypress run` to achieve that.
Make sure that your `package.json` has a script defined that calls this command.
You should be able to run the tests in headless mode with the command `npm run cypress:run`.

Check the output and report of the tests you get in the terminal.
In a later task, we will integrate proper reporting into the CI/CD pipeline.
