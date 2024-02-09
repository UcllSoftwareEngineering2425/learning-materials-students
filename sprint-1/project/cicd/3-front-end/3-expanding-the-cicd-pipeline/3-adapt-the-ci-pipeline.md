# Adapt the CI pipeline

Run your CI workflow again, you will see that the workflow fails with an error:

```console
npm ERR! code EPUBLISHCONFLICT
npm ERR! publish fail Cannot publish over existing version.
npm ERR! publish fail Update the 'version' field in package.json and try again.
npm ERR! publish fail 
npm ERR! publish fail To automatically increment version numbers, see:
npm ERR! publish fail     npm help version
```

We won't deal with version numbers in this course, the overhead is too much. We want to keep working with version `0.0.1`.

We need a workaround to clean-up the previous version so that the registry accepts our new version `0.0.1`.

## 1. Acceptance Criteria

At the end of this task your workflow should be expanded with an extra step that deletes the previous build artifacts. The registry should always contain exactly one package: the result of the most recent build.

The workflow file should contain no sensitive information.

## 2. Implementation Details

There are multiple ways to implement this, take a look at the GitHub Packages APIs and come up with a plan.