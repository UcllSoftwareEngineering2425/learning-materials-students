# Build a ci pipeline

## 1. Acceptance Criteria

At the end of this task you should have a workflow in your GitHub repository with one job that performs the following steps every time code is pushed on the default branch:

1. Checkout the code
2. Setup the Node version
3. Trigger a build 
    * If tests are failing, the workflow should fail!
4. Publish to GitHub packages

The workflow file should contain no sensitive information.

## 2. Implementation Details

Make sure to look at the generated workflow for inspiration for some of these sections.

### 2.1. Code the workflow trigger

1. Make it so that the workflow triggers every time code is pushed to the main branch

### 2.2. Checkout the code

1. Create a job for the workflow
1. The first step of the workflow should checkout the code

### 2.3. Setup the Node version

1. Add a step that makes sure that the rest of the job uses the Node version required by your Next.js app
    * You can see the Node version your app depends on in `package.json`

### 2.4. Trigger a build

1. Use npm to automate as much of this step as possible
    * The workflow should fail if not all tests are green
1. You should create a _standalone_ build so that the build output can be ran on its own
    * https://nextjs.org/docs/pages/api-reference/next-config-js/output
    * https://tech.competa.com/standalone-deployment-of-nextjs-3286490cb39b
    * You can verify that your standalone build works by executing the same steps locally:
        1. Copy `public` from your project to `public` in the `.next/standalone` folder
        1. Copy `.next/static` from your project to `.next/static` in the `.next/standalone` folder
        1. Execute `node server.js` in `.next/standalone` to see if the build works
    * If it works locally, code the creation of the standalone build in your workflow
1. Add the following to the scripts tag in `package.json`: `"start": "node server.js"`
    * `npm run start` will be automatically ran by Azure after deploying
    * Adding this script makes sure that our application will be startup correctly by Azure

It is best to do work like this in two steps:
1. First verify everything on your local machine (if you use Windows, it's best to use a Linux VM or WSL to
   figure out the correct Linux commands)
1. If that works code what you just did in the workflow
1. The following resource should be of interest:
    * https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-nodejs

### 2.5. Publish to GitHub packages

1. We will start from a successful build
1. First create a standalone output folder from the build results
    1. Copy `public` from your project to `public` in the `.next/standalone` folder
    1. Copy `.next/static` from your project to `.next/static` in the `.next/standalone` folder
    1. Execute `node server.js` in `.next/standalone` to see if the build works
1. Now publish the standalone output folder (`.next/standalone`) to GitHub Packages
    1. The node_modules should **not** be published, only the code files
    1. Try to work with `npm publish` and config in your `package.json`
        * Other approaches are possible, but this is the cleanest way
        * You'll be missing some properties that you'll still need to configure appropriately in `package.json` (you can set the version number to `0.0.1`).
    1. Some pointers:
        * https://docs.github.com/en/actions/publishing-packages/publishing-nodejs-packages
        * https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry
        * https://stackoverflow.com/questions/58637544/unable-to-login-to-github-package-registry