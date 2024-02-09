# Adapt the CI pipeline

Run your CI workflow a couple of times, you will notice that the package in your registry starts looking like this:

<a href="./images/3-1-Build artifacts are constantly added.png">
    <img src="./images/3-1-Build artifacts are constantly added.png">
</a>

Maven is normally used like this:

* As long as you are working on a version, you specify your version with `-SNAPSHOT` added in the pom.xml file (go and check in your own project, it should have a snapshot version in the pom)
    * Every build of this version overwrites the previous one
* As soon as the release is finished, `-SNAPSHOT` is removed and a definitive version is released
* For the next build, the version number is set to what it should be according to semver conventions, and `-SNAPSHOT` is added again

We won't deal with version numbers in this course, the overhead is too much. We will simply always work with version `0.0.1-SNAPSHOT`. We would expect that every run of our build overwrites the previous one, but GitHub Packages behaves differently than a normal maven registry here, it just appends the new build to the same maven version.

This issue is very weird, unexpected and inconvenient: 
* https://github.com/orgs/community/discussions/48971
* https://stackoverflow.com/questions/68521637/how-to-delete-old-snapshot-artifacts-from-github-packages
* https://github.com/actions/delete-package-versions/issues/71

Unfortunately, dealing with tooling that does not exactly behave as expected is part of the job for a devops engineer.

We need a workaround to clean-up the previous versions, if we keep appending new builds (each one having a size of approximately 50 MBs), we will have to pay GitHub a heavy bill for all the used storage.

## 1. Acceptance Criteria

At the end of this task your workflow should be expanded with an extra step that deletes the previous build artifacts. The registry should always contain exactly one package: the result of the most recent build.

The workflow file should contain no sensitive information.

**This is a very important task from a practical point of view. The GitHub bill will effectively be too large for UCLL if this task is not implemented correctly. You will incur negative marks if we see that your build artifacts are clogging up the storage.**

## 2. Implementation Details

There are multiple ways to implement this, take a look at the [GitHub Packages APIs](https://docs.github.com/en/rest/packages/packages?apiVersion=2022-11-28) and come up with a plan.