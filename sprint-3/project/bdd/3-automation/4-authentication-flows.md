# Authentication flows

## 1. Acceptance Criteria

1. A new scenario exists for an authenticated user accessing the lecturers overview page.
1. A custom command for login exists that is able to log in with a username and password.
1. The login command waits for the entire authentication flow to complete.

## 2. Implementation Details

### 2.1. Scenario: Authenticated user accesses the lecturers overview page

Write a scenario for an authenticated user accessing the lecturers overview page.

```gherkin
Scenario: Authenticated user attempts to access the lecturers overview page
    Given I am logged in as "johanp" with password "johanp123"
    When I navigate to the lecturers page
    Then I should see a table with all lecturers
```

Create a custom command for login that is able to log in with a username and password.
In your Cypress command, you will need to visit the login page, fill in the username and password, and submit the form.

### 2.2. Authentication flow

Tricky part of submitting a login form, is that you will need to wait for a request to the back-end to successfully complete.
Again, from a user's perspective in our front-end, we can be sure that a user is successfully logged in when he is redirected to the homepage.

Read [this article](https://medium.com/@muhammedsaidsyed215/best-practices-for-handling-dynamic-authentication-flows-in-cypress-f45b4e197986) on handling dynamic authentication flows in Cypress that should give you a clue on how to solve this.

Keep the last step simple for now, just check if the page contains a table without validating the content of the table.
