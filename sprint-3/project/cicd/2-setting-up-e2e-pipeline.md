# Setting up an E2E pipeline

## 1. Introduction

In this you will build a pipeline that runs your E2E tests. It should checkout a version of the front-end and back-end, start both applications, and run the E2E tests against them.

## 2. Acceptance Criteria

1. A separate pipeline for running E2E tests exists in the front-end repository.
1. The pipeline can be triggered either manually or automatically after the CI pipeline.
1. The pipeline checks out a version of the front-end (main branch or the latest published build from Github packages).
1. The pipeline should check out the latest published build of the back-end.
1. All E2E tests run within the GitHub Actions container.

## 3. Implementation Details

### 3.1 Back-end

This pipeline should checkout the latest published build of the back-end from GitHub Packages. Additional permissions may be required to access the back-end package. The following documentation may be helpful:

- https://docs.github.com/en/actions/security-for-github-actions/security-guides/automatic-token-authentication#granting-additional-permissions

- https://docs.github.com/en/actions/security-for-github-actions/security-guides/using-secrets-in-github-actions

Start the back-end application in the background, so the process does not block the pipeline.

### 3.2 Front-end

For the front-end you can checkout the latest published (standalone) build from GitHub Packages or the main branch. If you checkout the main branch, you will need to install dependencies and start the front-end in development mode.

Again, make sure the front-end is started in the background.

### 3.3 E2E tests

As a last step, run the cypress tests in headless mode. Make sure to run the back-end, front-end and E2E tests within the same job. If you run them in separate jobs, different containers are started and you won't be able to reach the running applications.

For now, you can follow the output in the logs. In the next task, you will setup proper reporting.
