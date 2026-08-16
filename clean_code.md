Tasks

1. Research the importance of consistent code style.
- Consistent code style makes code easier to read, understand, and maintain. When everyone follows the same formatting and naming rules, developers can spend less time figuring out how the code is written and more time focusing on what it does.
- It also helps reduce mistakes, makes code reviews easier, and improves teamwork because the project looks organised and predictable. Tools like linters and formatters can automatically enforce these rules and keep the codebase consistent.

2. Review the Airbnb javascript style guide.
- The Airbnb JavaScript Style Guide provides a set of rules and best practices for writing clean and consistent JavaScript. It covers areas such as variables, functions, naming conventions, spacing, comments, objects, arrays, and modules.
- Some key practices I found include:
1. Prefer const and let instead of var.
2. Use consistent naming conventions for variables and functions.
3. Use consistent spacing, indentation, commas, and semicolons.
4. Use JavaScript modules with import and export.
5. Keep functions and code organised and readable.
6. Use ESLint to help identify code that does not follow the style rules.
- Overall, the guide shows how having a consistent coding style can make JavaScript easier to read, maintain, and work on as a team.

3. Install and configure ESLint and Prettier in your development environment.
Done

4. Run the formatter and linter on your codebase and fix any issues.
Done

5. Write reflections in clean_code.md:
- Why is code formatting important?
- Code formatting is important because it makes code consistent, organised, and easier to read. When developers follow the same formatting style, it is easier for everyone to understand and maintain the code. Tools like Prettier can automatically format code and save time.

- What issues did the linter detect?
- When I tested ESLint, it detected an unused variable and an undefined console. The unused variable warning showed that I had created a variable that was never used. The console error occurred because it was not initially defined as a global in my ESLint configuration. This helped me understand how ESLint can identify potential problems and enforce coding rules.

- Did formatting the code make it easier to read?
- Yes, formatting made the code easier to read. Prettier automatically changed inconsistent formatting, such as double quotes and missing semicolons, to match the rules I configured. This made the code look cleaner and more consistent without having to manually format it.

6. Commit and push your changes to GitHub.
Done