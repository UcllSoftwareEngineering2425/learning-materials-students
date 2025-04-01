# Cypress

## 1. Introduction

- [Watch this video about E2E testing in NextJS with Cypress and Cucumber](https://www.youtube.com/watch?v=JYy3g_tHm9I)

  Note: This video is older than 2 years , the outdated package cypress-cucumber-preprocessor is used. In this project we will use @badeball/cypress-cucumber-preprocessor.

## 2. Cucumber preprocessor

- The `cypress-cucumber-preprocessor` integrates BDD into Cypress by allowing developers to write tests in plain-language Gherkin syntax.
  This preprocessor translates Gherkin `.feature` files into executable Cypress test code.

- https://github.com/badeball/cypress-cucumber-preprocessor

## 3. ESBuild preprocessor

- This preprocessor enables Cypress to **bundle** and **transpile** test files quickly using `esbuild`, a high-performance JavaScript bundler that transpiles JavaScript and TypeScript.
  The reason why this preprocessor is being used is to reduce Cypress test startup time.
  - **Transpiling** means transforming modern JavaScript or TypeScript code into older JavaScript syntax that browsers widely support, which allows developers to use the latest language features while ensuring that their code remains functional across various browsers.
  - **Bundling** is the process of combining multiple JavaScript files into a single file or a small set of files. This helps reduce the number of network requests a browser needs to make when loading a webpage or application. Bundlers, such as esbuild, analyze dependencies, optimize code, and minimize the final output to make applications load faster.
- [@bahmutov/cypress-esbuild-preprocessor](https://github.com/bahmutov/cypress-esbuild-preprocessor)
- https://esbuild.github.io/
