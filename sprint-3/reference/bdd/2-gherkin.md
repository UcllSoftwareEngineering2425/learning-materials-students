# Gherkin

Gherkin is a natural language to describe the behaviour of software. It follows a given-when-then structure, which makes it easy to understand and write, but also to automate in the next phase.

Below, you can see an example of a Gherkin feature file for the User Story "User Login":

```gherkin
Feature: User Login
    Scenario: Successful login
        Given I am on the login page
        When I enter valid credentials
        Then I should be redirected to the dashboard

    Scenario: Unsuccessful login
        Given I am on the login page
        When I they enter invalid credentials
        Then I should see an error message
```

This example just covers the very basics. There is much more to Gherkin, such as: Background, Scenario Outline, Tags, etc. Make sure to read and use the [Gherkin reference](https://cucumber.io/docs/gherkin/reference) during the formulation phase.
