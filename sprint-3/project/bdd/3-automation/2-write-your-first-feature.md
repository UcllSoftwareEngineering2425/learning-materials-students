# Write your first feature

## 1. Acceptance Criteria

1. All code related to E2E testing is placed in the `cypress` folder:
   1. Features: `cypress/e2e/features`
   1. Step definitions: `cypress/support/step_definitions`
   1. Custom commands: `cypress/support/e2e.ts`

## 2. Implementation Details

### 2.1. Lecturers overview page

To get things started, write a feature file for a simple User Story. For example, the lecturers overview page.
This story should have a few happy and unhappy paths. Start with the most basic one:

```gherkin
Feature: Lecturers Overview

Scenario: Unauthenticated user attempts to access the lecturers overview page
    Given I am an unauthenticated user
    When I navigate to the lecturers page
    Then I should see an unauthorized error message
```

Place this feature file in the `cypress/e2e/features/lecturers.overview.feature` folder.

### 2.2. Implement the step definitions

- You need to tell Cucumber how to execute the steps in the feature file by implementing the step definitions. Create a new file in the `cypress/support/step_definitions` that will contain the step definitions for the lecturers page.
  On [this page](https://github.com/badeball/cypress-cucumber-preprocessor/blob/master/docs/cucumber-basics.md) you can learn how to implement step definitions with Cypress and Cucumber.

- The first step, `Given I am an unauthenticated user`, must assure that the user is not logged in. From a user's perspective, this means that if there is a "Logout" link somewhere on the screen, it should be clicked. If there is no "Logout" link, the user is already logged out. It makes sense to create a custom command for this, which is reusable in other step definitions.

- You can define commands in the `cypress/support/e2e.ts` file.
  Read [Cypress custom commands](https://docs.cypress.io/api/cypress-api/custom-commands) and [Cypress best practices for custom commands](https://medium.com/%40muhammedsaidsyed215/best-practices-for-cypress-io-custom-commands-in-typescript-and-javascript-0d76511d5589) to learn how to create custom commands.

- Write a custom command for `logout` and call it from your step definition.

- Implement the step definitions for the other steps in the feature file.
