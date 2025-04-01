# Test isolation in E2E testing

## 1. Introduction

It's best practice in testing that tests should run independently of each other. This means that tests should not depend on the outcome of other tests. When you write tests that modify data, you need to be careful to ensure that the data is restored to its original state after each test run. This is especially important in end-to-end (E2E) tests, where the tests interact with the application as a user would.

## 2. Acceptance criteria

1. A scenario for enrolling students in a schedule exists and can be successfully executed repeatedly.
   1. The scenario should check that number of enrolled students is increased.
   1. The scenario should check that the enroll button disappears after a student is enrolled.
2. The data is restored to its original state after each test run.

## 3. Implementation Details

The following article might be helpful in understanding the different strategies to handle data in E2E tests: https://learn.cypress.io/advanced-cypress-concepts/database-initialization-and-seeding.

Since we are working with a back-end Rest API, the easiest approach is to call an endpoint that resets the database after each test run. As you can read in the 'Cons' section of this strategy, it poses potential security risks. You certainly don't want this endpoint to be publicly accessible in production.

1. Write a feature for Schedules that includes a scenario for enrolling students in a schedule. You can copy what you have written in the formulation phase, but you may need to make some adjustments later to make it work with Cucumber/Cypress.
1. Create a new endpoint in the back-end that resets the database. This endpoint should only be accessible in the "dev" profile. E.g. `/test-utils/reset-database`. Since this endpoint is only accessible in the "dev" profile, no authentication is needed.
1. In the front-end, configure Cypress so it is able to perform a fetch request to this endpoint. The following documentation might be helpful:

   - https://docs.cypress.io/api/node-events/overview#cytask

   - https://docs.cypress.io/api/commands/task

1. Make sure that after each test, the database is reset.
