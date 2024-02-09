# Play around with NPM

When building your cicd pipeline you will need to build and start the application manually (i.e. without help of your IDE). We will practice this locally in this story.

## 1. Acceptance Criteria

Make sure that you can:
* Do a local build of your next.js project using npm
* Run the output of the local build

## 2. Implementation Details

We will need a standalone build for the cicd-pipeline, so it might be worth it to already look at configuring a standalone build.

1. Configure a local build
    * https://nextjs.org/docs/pages/api-reference/next-config-js/output
    * https://tech.competa.com/standalone-deployment-of-nextjs-3286490cb39b
1. Verify that the standalone build works by executing the following steps:
    1. Copy `public` from your project to `public` in the `.next/standalone` folder
    1. Copy `.next/static` from your project to `.next/static` in the `.next/standalone` folder
    1. Execute `node server.js` in `.next/standalone` to see if the build works
1. If this works, add the following to the scripts tag in `package.json`: `"start": "node server.js"`
    * `npm run start` will be automatically ran by Azure after deploying
    * Adding this script makes sure that our application will be startup correctly by Azure