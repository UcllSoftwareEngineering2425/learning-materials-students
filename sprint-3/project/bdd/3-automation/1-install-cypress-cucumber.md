# Install Cypress and Cucumber

## 1. Introduction

In this phase of BDD, you will automate the features you have written during the formulation phase. BDD can be applied to all levels of the testing pyramid, but in this project, we will focus on End-2-End (E2E) testing. To do this, we will use Cypress in combination with Cucumber.

E2E testing means that you test the entire application from the user's perspective. This implies that you will test the application as a whole, including the front-end and back-end. Since the front-end is the starting point, we will implement E2E tests in this project.

Before starting with this task, make sure to read the reference material about [Cucumber](../../../reference/bdd/3-cucumber.md) and the [Cypress Introduction section](../../../reference/bdd/4-cypress.md#1-introduction).

## 2. Acceptance Criteria

The following criteria should be met after this task:

1. Cypress and Cucumber are installed in the front-end project.
1. Cypress is configured to work with TypeScript.

## 3. Implementation Details

### 3.1 Install Cypress and Cucumber

Using npm, install the following packages as a dev dependency:

- `cypress`: The main package for Cypress.
- `@badeball/cypress-cucumber-preprocessor`: A preprocessor that allows you to write Cucumber feature files and step definitions in Cypress. See [reference](../../../reference/bdd/4-cypress.md#2-cucumber-preprocessor) for more information.
- `@bahmutov/cypress-esbuild-preprocessor`: A transpiler and bundler for Cypress. See [reference](../../../reference/bdd/4-cypress.md#3-esbuild-preprocessor) for more information.

### 3.2 Configure Cypress with TypeScript

- Next step is to configure Cypress to process `.feature` files using the Cucumber preprocessor and ESBuild. You will need to create a `cypress.config.ts` file in the root of your project.
  On the [Cucumber preprocessor github page](https://github.com/badeball/cypress-cucumber-preprocessor/tree/master/examples/esbuild-ts) you can find an example configuration for ESBuild with TypeScript.

- To ensure Cypress correctly understands and processes TypeScript-specific syntax, without interfering with the main application's TypeScript configuration, it's important to set up a separate configuration for Cypress:

  - Create a `tsconfig.json` file specifically for Cypress. This file should be placed in the root of the `cypress` folder. Again, have a look at the examples on the Cucumber preprocessor github page.
  - Make sure to exclude the `cypress` folder and `cypress.config.ts` from the project root `tsconfig.json` file:

    ```json
    {
      ...
      "exclude": ["node_modules", "cypress.config.ts", "cypress"]
    }
    ```
