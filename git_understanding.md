✅ Tasks

1. Research best practices for writing commit messages.
- A good commit message should clearly describe what changed and why. Each commit should focus on one logical change, begin with a short, specific summary written in the imperative mood (e.g. Fix login bug or Add user report), and include a body when needed to explain the reason for the change, implementation decisions, or important side effects. Avoid vague messages like Updated code or Fixed stuff, and reference related issues if applicable. Many teams also follow the Conventional Commits format (e.g. feat:, fix:, docs:) to keep commit histories consistent and support automated tools. Overall, clear, concise, and descriptive commit messages make code easier to review, maintain, and debug.

2. Explore commit histories in an open-source GitHub project (e.g., React, Node.js) and analyze good vs. bad commit messages.
- I explored commit histories from projects such as React and Node.js. Good commit messages are clear, specific, and explain what changed, such as fix(timer): prevent sessions ending early. Poor commit messages are vague, such as fixed stuff or update, because they do not explain the change. Clear messages make the project history easier to understand, review, and debug.

3. Make three commits in your repo with different commit message styles:
- A vague commit message (e.g., "fixed stuff").
- An overly detailed commit message.
- A well-structured commit message.

4. Write reflections in git_understanding.md:
- What makes a good commit message?
- A good commit message is clear, specific, and easy to understand. It should briefly explain what was changed and, when necessary, why the change was made. Good commit messages usually use the imperative mood, such as Fix login error or Add activity report, and avoid vague wording like Updated files or Fixed stuff.

- How does a clear commit message help in team collaboration?
- A clear commit message helps team members quickly understand the purpose of a change without needing to examine every line of code. It makes code reviews easier, improves communication, and helps developers follow the progress of a project. It is also useful when someone needs to find when and why a particular feature or bug fix was introduced.

- How can poor commit messages cause issues later?
- Poor commit messages can make the project history confusing and difficult to search. Messages such as Changes, Update, or Fix do not explain what was modified, which can waste time when debugging or reviewing previous work. They can also make it harder to identify the cause of a problem, safely revert a change, or understand decisions made by other developers.

5. Commit and push your changes to GitHub.
Done

✅ Tasks


1. Research the following Git commands and test them in your repo:

- git checkout main -- <file> – Restores a specific file to the version stored on the main branch without changing other files in the current branch. This is useful when you want to undo changes to only one file.

- git cherry-pick <commit-hash> – Applies one specific commit from another branch onto the current branch without merging the entire branch. This is useful when you only want selected changes.

- git log – Displays the commit history of the repository, including commit hashes, authors, dates, and commit messages. It helps understand how the project has changed over time.

- git blame <file> – Shows who last changed each line in a file and which commit introduced that change. This can help identify when and why a particular section of code was modified.

2. Experiment with each command in your test repo:

- Modify a file, then restore it using checkout.
- Commit changes on a branch, then cherry-pick one commit onto main.
- Use git log to explore the commit history.
- Use git blame to see past changes in a file.
Done

3. Write reflections in git_understanding.md:

- What does each command do?
    - git checkout main -- <file> restores a specific file from the main branch without changing other files in the current branch.

    - git cherry-pick <commit-hash> copies a specific commit from another branch and applies it to the current branch.

    - git log shows the commit history, including commit messages, authors, dates, and commit hashes.

    - git blame <file> shows who last changed each line in a file and which commit that change came from.

- When would you use it in a real project (hint: these are all really important in long running projects with multiple developers)?

    - git checkout main -- <file> – I would use this when I want to restore one file to the version from main without losing changes I have made to other files.

    - git cherry-pick <commit-hash> – I would use this when another developer has made a useful fix or change on a different branch and I only want that specific commit without merging their entire branch.

    - git log – I would use this to review the history of a long-running project, understand what changes were made, and find specific commits when investigating bugs or previous work.

    - git blame <file> – I would use this to find when and by whom a particular line was last changed. In a project with multiple developers, this can help me understand the history and context of the code and identify the relevant person to ask about a change.

- What surprised you while testing these commands?
- I was surprised by how much information Git keeps about a project’s history. Commands like git log and git blame made it easy to see when changes were made and which commits they came from. I also found it useful that git checkout can restore just one file and git cherry-pick can apply a single commit without merging an entire branch.

4. Commit and push your changes to GitHub.
Done

Tasks


1. Research git bisect and how it helps in debugging.
- git bisect is a Git debugging tool used to find the specific commit that introduced a bug. It uses a binary search, meaning it repeatedly checks commits in the middle of a known working (good) commit and a broken (bad) commit until it finds where the problem started.

- For Example: 
git bisect start
git bisect bad
git bisect good <good-commit>

- Git then selects commits for you to test. After each test, you mark the commit as:
git bisect good OR git bisect bad

- Once Git identifies the first bad commit, you can inspect the changes that caused the problem. When finished, you use:
git bisect reset

- This is useful because instead of manually checking every commit, git bisect quickly narrows down the project history and helps developers find when a bug was introduced.

2. Create a test scenario:
- Make a series of commits in your test repo.
- Introduce a bug in one of the commits.
- Use git bisect to track down the commit that introduced the issue.

Done

3. Experiment using your Git desktop client (or CLI if preferred).

Done

4. Write reflections in git_understanding.md:
- What does git bisect do?
- git bisect is a Git tool that helps find the commit that introduced a bug. It uses a binary search between a known good commit and a bad commit, allowing Git to narrow down where the problem was introduced.

- When would you use it in a real-world debugging situation?
- I would use git bisect when a feature previously worked but is now broken and I am not sure which commit caused the problem. It would be especially useful when there are many commits between the working and broken versions.

- How does it compare to manually reviewing commits?
- git bisect is faster and more efficient than manually checking every commit. Instead of reviewing each commit one by one, it repeatedly narrows down the possible commits until the first bad commit is found. This can save a lot of time when working with a large commit history.

Commit and push your changes to GitHub.
Done