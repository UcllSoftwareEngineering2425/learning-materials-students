# Build a ci pipeline

## 1. Acceptance Criteria

At the end of this task you should have a workflow in your GitHub repository with one job that performs the following steps every time code is pushed on the default branch:

1. Checkout the code
2. Setup the Java version
3. Trigger a full maven build that ends with a publish to GitHub packages
    * If tests are failing, the workflow should fail!

The workflow file should contain no sensitive information.

## 2. Implementation Details

Make sure to look at the generated workflow for inspiration for some of these sections.

### 2.1. Code the workflow trigger

1. Make it so that the workflow triggers every time code is pushed to the main branch

### 2.2. Checkout the code

1. Create a job for the workflow
1. The first step of the workflow should checkout the code

### 2.3. Setup the Java version

1. Add a step that makes sure that the rest of the job uses Java 21

### 2.4. Change group ID

Since everyone starts from the same code the `pom.xml` will contain the same `groupId`
and `artifactId` for everyone. This will lead to conflicts when we want to publish our package to
GitHub packages. Update the `groupId` in `pom.xml` to match your team so that your package's full name
is unique.

### 2.5. Build and publish to GitHub packages

1. Use maven to automate as much of this step as possible
    * The workflow should fail if not all tests are green
1. The following resources might be helpful if you are stuck
    * About the Apache Maven Registry in GitHub Packages in general
        * https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-apache-maven-registry
        * https://docs.github.com/en/actions/publishing-packages/publishing-java-packages-with-maven
    * About authenticating to GitHub Packages from within an action
        * https://docs.github.com/en/actions/security-guides/automatic-token-authentication
    * About directly configuring your action to publish to the correct registry
        * https://stackoverflow.com/questions/57711558/deploy-to-github-package-registry-from-github-action
