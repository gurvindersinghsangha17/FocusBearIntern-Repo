✅ Tasks

1. Research best practices for naming variables and functions.
- Good naming practices use clear and descriptive names that explain the purpose of variables and functions. Avoid vague names like x or data and use meaningful names such as user_age or calculate_total(). Consistent naming styles improve readability, reduce confusion, and make code easier to maintain and debug.

2. Find examples of unclear variable names in an existing codebase (or write your own).

**Poor Variable Names**
def calculate_total(a, b):
    x = a * b
    y = x * 0.1
    z = x + y
    return z

Problems:
- a and b do not explain what values they represent.
- x, y, and z make the calculations difficult to understand.
- Another developer would need to read the entire function to understand the purpose.

3. Refactor the code by renaming variables/functions for better clarity.

**Improved Version**

def calculate_total_price(quantity, price):
    subtotal = quantity * price
    tax_amount = subtotal * 0.1
    total_price = subtotal + tax_amount

    return total_price

Improvements:
- Variable names clearly describe their purpose.
- The code is easier to read and maintain.
- Developers can understand the logic without needing extra comments.


4. Write reflections in clean_code.md:
- What makes a good variable or function name?
- A good variable or function name should be clear, descriptive, and meaningful. It should explain what the value represents or what the function does without needing extra explanation. Avoid short or confusing names like x or temp, and use names like customer_age or calculate_total_price() instead. Consistent naming makes code easier to read, debug, and maintain.

- What issues can arise from poorly named variables?
- Poorly named variables can make code difficult to understand, debug, and maintain. Developers may spend extra time figuring out what a variable represents, increasing the chance of mistakes. Unclear names can also lead to confusion when updating or reviewing code, making collaboration harder. Using descriptive names improves readability and reduces errors.

- How did refactoring improve code readability?
- Refactoring improved code readability by replacing unclear names with descriptive variable and function names that clearly explain their purpose. It made the code easier to understand without needing extra comments or investigation. Clear naming helps developers quickly identify what the code does, making it easier to maintain, debug, and modify in the future.

5. Commit and push your changes to GitHub.
Done