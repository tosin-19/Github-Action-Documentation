## GITHUB ACTION
# What is a Github Action?
**GitHub Actions** is a **built-in CI/CD (Continuous Integration and Continuous Deployment)** feature in GitHub that lets you **automate tasks** in your software workflow.

## Purpose of Github Action
GitHub Actions helps you automate **repetitive tasks** like:
| ------------ | | ----------- |
| **Use Case** | | **Example** |
|--------------| |-------------|
| Running Tests | | Run unit tests when you push code |
|---------------| | --------------------------------- |
| Deploying applications | | Deploy your app to AWS, Azure, Netlify, etc. |
|----------------------- | | -------------------------------------------- |
| Linting and formatting | | Auto-check your code style |
|-----------------------|  | ---------------------------|
| Labeling issues/PRs | | Add tags like bug or enhancement |
| --------------------| | -------------------------------- | 
| Sending notifications | | Post to Slack, send emails, etc. |
| --------------------- | | -------------------------------- |

## Why use Github Action?
- **Automation:** Save time by automating manual processes.
- **Reliability:** Ensure your code works with every change.
- **Integration:** Tightly integrated into GitHub – no external tools needed.
- **Customizable:** Use existing Actions from the marketplace or write your own.

## How Github Action Works.
GitHub Actions is made up of:
|----------| |-------------|
| **Term** | | **Meaning** |
| -------- | | ----------- |
| **Workflow** | | A .yml file that defines what to run and when. |
| ------------ | | ---------------------------------------------- |
| **Job** | | A group of step (like build, test and deploy) |
| ------- | | --------------------------------------------- |
| **Step** | | An individual command in a job |
| -------- | | ------------------------------ |
| **Action** | | A resuable unit of code that does a task |
| ---------- | | ---------------------------------------- |

## Workflow File Example :
This workflow runs tests every time code is pushed:
-yaml
name: Run Tests
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - name: Install Dependencies
        run: npm install
      - name: Run Tests
        run: npm test
