# cypress-e2e-testing-for-orangehrm-application

> Cypress 13+ project

### 💻 Topics

Integrated with:

- [x] https://docs.cypress.io/guides/getting-started/installing-cypress
- [x] https://www.npmjs.com/package/cypress-mochawesome-reporter
- [x] https://www.npmjs.com/package/cypress-multi-reporters

- ## 💻 Pre-requisites

1. Node JS

## 🚀 Install the project

Install project dependencies with: npm install

## Run the demo:

1. Standard Headless Execution: npx cypress run 
2. Standard Execution: npx cypress open

## Reporting

   Automatically generated html report (mochawesome) under folder "reports/html"
   e.g /Users/oluseunbolarinwa/cypress-projects/cypress-safeguard/olu-safeguard-qatests/cypress/reports

## Future reporting implementation
1. Using native report with JSON FORMATTER

## Steps to implement the native report JSON FORMATTER
1. Download cucumber-json-formatter(MacOS darwin amd64 or Windows amd64)
2. Rename the file as cucumber-json-formatter (MacOS) or cucumber-json-formatter.exe
3. Move file to a directory that's on the path
4. Make it executable with "chmod +x cucumber-json-formatter"
5. Verify that you can run it: cucumber-json-formatter --help
6. Run test execution (eg. npx cypress run). This will generate two files "log.json" and "messages.ndjson".
   These files can be used to convert into html
7. In order to convert these json files, first install multiple cucumber html reporter using 
   "npm install multiple-cucumber-html-reporter --save-dev"
8. Finally run command "node cucumber-html-reporter.js" to convert into html generated reporting

Integrated with:

- [x] https://github.com/cucumber/json-formatter
- [x] https://github.com/cucumber/json-formatter/releases/tag/v19.0.0
- [x] https://www.npmjs.com/package/multiple-cucumber-html-reporter

<main.yml> -- Information
Starting from a top, we’re defining GitHub Actions workflow’s name and under which conditions it will be triggered. 
I’ve chosen to trigger it after pushing new commit into the main branch.

Next, there is a jobs section, with only one job defines — cypress-run

Above we define the name of a workflow, which host runner will be used and finally  workflow will be running .

Then we can move on to the steps of a workflow.
First we need to set up a job, by checking out the code from the main branch and then downloading and installing all necessary dependencies for running tests.

After that we can run our tests in a Firefox browser. There is the continue-on-error flag set to true because even if our tests fail we want to run other workflow steps responsible for generating a report.
