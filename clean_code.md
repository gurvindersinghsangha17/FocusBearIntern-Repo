✅ Tasks

1. Research best practices for writing comments and documentation.
- Best practices for writing comments and documentation focus on making code easier to understand, maintain, and use. Comments should explain why something is done rather than simply repeating what the code already shows. Good comments are clear, concise, and kept up to date as the code changes. Developers should avoid unnecessary comments that add clutter and instead write self-explanatory code with meaningful variable and function names. Documentation should explain how a system works, how to use it, and any important limitations or requirements. Examples, setup instructions, and API documentation help other developers understand and use the code effectively. Overall, good documentation improves collaboration, reduces confusion, and makes future updates easier.

2. Find an example of poorly commented code and rewrite the comments to be more useful.

**Poorly Commented**
# Add numbers
def calculate_total(price, tax):
    # Add tax
    total = price + tax
    # Return total
    return total

Issues with the Comments:
- The comments only repeat what the code already shows.
- They do not explain the purpose of the function or why the calculation is performed.
- They add unnecessary clutter without providing useful information.

**Improved Comments**
def calculate_total(price, tax):
    # Calculate the final price by adding the applicable tax amount
    # to the original product price before returning the amount charged.
    total = price + tax

    return total

- The improved comment explains the purpose of the calculation rather than describing obvious actions. It gives future developers context about what the function represents and why the operation is needed, making the code easier to maintain.

3. Write reflections in clean_code.md:
- When should you add comments?
- Comments should be added when they provide useful information that is not obvious from the code itself. They are helpful for explaining why a decision was made, describing complex logic, documenting important assumptions, or warning about potential issues. Comments are also useful for explaining APIs, configuration requirements, or unusual workarounds. However, developers should avoid commenting every line of code or repeating what the code already shows, as this can make code harder to read. Good comments add context and help future developers understand and maintain the code more effectively.

- When should you avoid comments and instead improve the code?
- You should avoid comments when the code itself can be made clearer through better structure, naming, or design. If a comment only explains what the code is doing, it is often better to rewrite the code with meaningful variable and function names so it is self-explanatory. For example, instead of adding a comment like "calculate total price," use a function name such as calculate_total_price(). Avoid comments that explain confusing or messy code; improve the code first by simplifying logic, removing duplication, and making the purpose clearer. Comments should provide additional context, not compensate for poorly written code.

4. Commit and push your changes to GitHub.
Done