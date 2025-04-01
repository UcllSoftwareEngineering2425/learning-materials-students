# Backgrounds

## 1. Acceptance Criteria

1. Duplicate given steps are moved to a `Background` section.

## 2. Implementation Details

By now, you should have two scenarios with the same first step: `Given I am logged in as "johanp" with password "johanp123"`.
It is a good practice to use the `Background` keyword to avoid repeating the same steps in multiple scenarios.
Create a `Background` section in your feature file and move the step to this section.

More info: https://cucumber.io/docs/gherkin/reference/#background

The unauthorized scenario should remain working after this change.
