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