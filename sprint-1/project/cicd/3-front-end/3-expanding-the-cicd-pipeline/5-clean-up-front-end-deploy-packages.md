# Clean up front-end deploy packages

## 1. Acceptance Criteria

Every time a new front-end package is deployed to Azure, the old zip packages are cleaned-up.

## 2. Implementation Details

Every time the front-end is deployed a new zip archive is pushed to disk on Azure (see [this task, section 2.1](./4-build-a-cd-pipeline.md)). This will fill-up the disk over time.

You will need to tackle the growing disk usage, especially if your apps [share a free App Service Plan](<../../../../reference/cicd/azure/1 - note on app service plan.md>).

As long as your app is running you can manually clean-up the previous deploys via SSH. This is cumbersome to do.

Can you think of an automated solution to fix this?

Here are two possible avenues on how you could start tackling this:

* Configure your start-up command: the start-up command should run a script that cleans up the old packages and then starts up the application
* [Via a post deployment action](https://github.com/projectkudu/kudu/wiki/Post-Deployment-Action-Hooks)