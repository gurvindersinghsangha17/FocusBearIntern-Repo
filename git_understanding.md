# Git Understanding - Pull Requests

## Research: Pull Requests

A Pull Request (PR) is a way of proposing changes to a codebase before
those changes are merged into another branch, such as the main branch.

A Pull Request (PR) is a way of proposing changes to a codebase before
those changes are merged into another branch, such as the main branch.
A developer normally creates a separate branch, makes and commits their
changes, pushes the branch to GitHub, and then opens a Pull Request.

The Pull Request allows other developers to review the proposed changes
before they become part of the main codebase. Reviewers can look at the
files and commits, leave comments, suggest improvements, request changes,
or approve the Pull Request.

Pull Requests are useful because they support collaboration and code
review. They can help teams identify bugs, improve code quality, discuss
different approaches, and make sure changes meet the project's standards
before they are merged.

A typical Pull Request workflow is:

1. Create a new branch from the appropriate base branch.
2. Make the required changes on the new branch.
3. Commit the changes with a meaningful commit message.
4. Push the branch to the remote repository.
5. Open a Pull Request on GitHub.
6. Describe what was changed and why.
7. Ask another developer to review the changes.
8. Respond to feedback and make additional changes if required.
9. After approval, merge the Pull Request.
10. Delete the feature branch when it is no longer needed.

From this research, I learned that a Pull Request is not only a way to
merge code. It also creates a place where developers can review,
discuss, and improve changes before they become part of the main
codebase.

## Open-Source Pull Request Review

I reviewed React Pull Request #37301, titled
"Fix: Add proper error handling to task scripts (eslint, linc, flow)."

The purpose of the Pull Request was to improve error handling in several
React build and CI task scripts. The author added error handling so that
unexpected asynchronous failures are logged properly and the process exits
with a non-zero status instead of causing unhandled promise rejections.

The Pull Request changed three files:

- `scripts/tasks/eslint.js`
- `scripts/tasks/linc.js`
- `scripts/tasks/flow.js`

I observed that GitHub Copilot automatically reviewed all three changed files.
It provided an overview of the changes but did not identify any code issues or
request any changes.

I also noticed that React has additional contribution requirements. The author
was initially asked to sign Meta's Contributor License Agreement before the
Pull Request could continue through the review process. After the agreement
was signed, the PR received the `CLA Signed` label and the CLA check passed.

The Pull Request also showed several automated workflow checks. Some checks
passed, while other workflows were waiting for approval from a maintainer.

At the time I reviewed the PR, it was still open and required at least one
approving review from someone with write access before it could be merged.

This showed me that Pull Requests in large open-source projects involve more
than just reviewing code. They can also include automated checks, contribution
agreements, repository rules, and approval requirements before changes are
allowed into the main branch.

## Pull Request Reflection

### Why are PRs important in a team workflow?

Pull Requests are important in a team workflow because they allow changes
to be reviewed before they are merged into the main codebase. Other team
members can check the code, identify possible problems, suggest improvements,
and discuss different approaches.

PRs also create a record of the changes and discussions that took place. This
can make collaboration easier and help maintain the quality of the project.

### What makes a well-structured PR?

A well-structured Pull Request should have a clear and meaningful title and
description. The description should explain what was changed and why the
change was needed.

The PR should focus on a specific task instead of containing many unrelated
changes. It should also be easy for reviewers to understand the changes,
review the affected files, and provide feedback. Relevant tests and automated
checks should also pass where applicable.

### What did you learn from reviewing an open-source PR?

From reviewing React Pull Request #37301, I learned that Pull Requests in
large open-source projects can go through several checks before they are
merged.

In the PR I reviewed, GitHub Copilot automatically reviewed the three changed
files and did not request any changes. The contributor also needed to sign
Meta's Contributor License Agreement before the contribution could continue
through the review process.

I also saw that automated workflow checks were used and that the PR still
required an approving review from someone with write access before it could
be merged.

This taught me that a Pull Request is not only about submitting code. It also
provides a process for code review, automated testing, contribution
requirements, discussion, and approval before changes become part of the
main project.
