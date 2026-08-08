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