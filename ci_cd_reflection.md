# CI/CD Reflection

## Research: What is CI/CD and why is it used?

CI/CD stands for Continuous Integration and Continuous Delivery/Deployment.

Continuous Integration helps catch bugs early by automatically testing new code
when it is added to a shared repository.

Continuous Delivery or Deployment helps prepare or release code after it passes
the required checks.

CI/CD is useful because it saves time, reduces manual work, catches problems
earlier, and makes software releases faster and more reliable.

## CI Workflow Setup

I set up a CI workflow that runs Markdown linting and spell checks on pull
requests in the repository.

The workflow automatically checks Markdown files when a pull request is opened
or updated. This helps identify formatting and spelling issues before changes
are merged.

## Git Hooks with Husky

I experimented with Husky to create a Git pre-commit hook.

I configured the hook to run Markdownlint before each commit. This means
Markdown files are automatically checked for formatting problems before Git
allows the commit to continue.

Git hooks are useful because they can catch issues locally before they are
pushed to GitHub.

## Test Pull Request

I opened a test pull request in the repository and reviewed the automated checks
created by the CI workflow.

I used the results of the checks to identify and fix Markdown formatting issues
before pushing the final changes.

## CI/CD Configuration

I pushed the CI/CD workflow configuration and related files to the repository.

## Reflections

### What is the purpose of CI/CD?

The purpose of CI/CD is to make developing, testing, and releasing software
faster and more reliable.

Continuous Integration helps developers regularly combine their code changes
and automatically test them for problems. Continuous Delivery or Deployment
helps prepare and release those changes once they pass the required checks.

### How does automating style checks improve project quality?

Automating style checks helps keep code and documentation consistent across a
project.

It can automatically find formatting, spelling, or coding-style problems before
changes are merged. This saves developers time and helps maintain cleaner and
easier-to-read projects.

### What are some challenges with enforcing checks in CI/CD?

One challenge is that automated checks can sometimes fail because of small
issues, such as an unknown technical word being flagged by a spell checker.

Checks can also slow down the development process if there are many tests to
run. Developers need to configure the checks carefully so that they catch
useful problems without creating unnecessary failures.

### How do CI/CD pipelines differ between small projects and large teams?

Small projects usually have simpler CI/CD pipelines with basic checks such as
linting and automated tests.

Large teams often need more complex pipelines because many developers may be
working on the same project. Their pipelines can include multiple testing
stages, security checks, code reviews, deployment environments, and approval
steps before changes are released.
