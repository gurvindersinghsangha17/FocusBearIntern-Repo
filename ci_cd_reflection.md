Tasks

1. Research what CI/CD is and why it’s used in software development.

- CI/CD stands for Continuous Integration and Continuous Delivery/Deployment. It is a way of automatically testing and preparing code whenever developers make changes.
- CI helps catch bugs early by testing new code when it is added to a shared repository. CD helps prepare or release that code after it passes the required tests.
- CI/CD is useful because it saves time, reduces manual work, catches problems earlier, and makes software releases faster and more reliable.

2. Set up a CI workflow that runs Markdown linting and spell checks on PRs in your repo.
Done

3. Experiment with Git Hooks (e.g., Husky) to enforce linting before commits.
- I experimented with Husky to create a Git pre-commit hook. I configured the hook to run Markdownlint before each commit. This means Markdown files are automatically checked for formatting problems before Git allows the commit to continue. Git hooks are useful because they can catch issues locally before they are pushed to GitHub.

4. Open a test PR in your repository and review the automated checks.
Done

5. Push your CI/CD configuration to your repo.
Done

6. Write reflections in ci_cd_reflection.md:
- What is the purpose of CI/CD?
- The purpose of CI/CD is to make developing, testing, and releasing software faster and more reliable. Continuous Integration helps developers regularly combine their code changes and automatically test them for problems. Continuous Delivery or Deployment helps prepare and release those changes once they pass the required checks.

- How does automating style checks improve project quality?
- Automating style checks helps keep code and documentation consistent across a project. It can automatically find formatting, spelling, or coding-style problems before changes are merged. This saves developers time and helps maintain cleaner and easier-to-read projects.

- What are some challenges with enforcing checks in CI/CD?
- One challenge is that automated checks can sometimes fail because of small issues, such as an unknown technical word being flagged by a spell checker. Checks can also slow down the development process if there are many tests to run. Developers need to configure the checks carefully so that they catch useful problems without creating unnecessary failures.

- How do CI/CD pipelines differ between small projects and large teams?
- Small projects usually have simpler CI/CD pipelines with basic checks such as linting and automated tests. Large teams often need more complex pipelines because many developers may be working on the same project. Their pipelines can include multiple testing stages, security checks, code reviews, deployment environments, and approval steps before changes are released.