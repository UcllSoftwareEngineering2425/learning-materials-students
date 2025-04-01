# Externalize URLs

## 1. Introduction

At this point, you might have hardcoded URLs in `cypress.config.ts`.

Our E2E tests only run locally at the moment, but in order to prepare for ci/cd, it's a good idea to externalize the URLs.

## 2. Acceptance Criteria

1. No hardcoded URLs exist in `cypress.config.ts`.

## 3. Implementation Details

1. In you local `.env` file, make sure entries exist for API_URL and the Cypress BASE_URL.
1. In cypress.config use dotenv.config() and process.env to load the values for API_URL and BASE_URL.
