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

✅ Tasks
1. Research strategies for handling errors and edge cases in code (include Guard Clauses).
- Effective error handling involves designing code to manage unexpected situations and edge cases gracefully. One useful strategy is guard clauses, which check for invalid conditions early and exit a function before the main logic runs, making code cleaner and easier to maintain. Other approaches include validating user inputs, using exception handling to prevent crashes, logging errors for debugging, and testing boundary cases such as empty values or extreme inputs. By anticipating potential failures and handling them appropriately, developers can create more reliable, secure, and user-friendly software.

2. Find an existing function that doesn’t properly handle errors or invalid inputs.

**Function**
def divide_numbers(a, b):
    return a / b

This function assumes that the inputs will always be valid. However, it does not handle cases where b is zero, which causes a ZeroDivisionError, or when non-numeric values are provided.

3. Refactor the function to improve error handling.
- A better implementation would use a guard clause to check invalid inputs before performing the calculation:

**Function**
def divide_numbers(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")

    if not isinstance(a, (int, float)) or not isinstance(b, (int, float)):
        raise TypeError("Inputs must be numbers")

    return a / b

- By validating inputs early, the function becomes more reliable and prevents unexpected crashes.

4. Write reflections in clean_code.md:
- What was the issue with the original code?
- The issue with the original code was that it did not check for invalid inputs or possible errors before performing the division. If the second value (b) was 0, the program would crash with a ZeroDivisionError. It also assumed that both inputs would always be numbers, meaning passing incorrect data types could cause unexpected failures. The function lacked validation and error handling, making it less reliable when dealing with edge cases.

- How does handling errors improve reliability?
- Handling errors improves reliability by preventing programs from crashing when unexpected situations occur. By checking for invalid inputs, handling exceptions, and providing clear error messages, the software can respond appropriately instead of failing. This makes the application more stable, easier to debug, and provides users with a better experience even when problems occur.

5. Commit and push your changes to GitHub.
Done

✅ Tasks

1. Research best practices for writing small, single-purpose functions.
- Best practices for writing small, single-purpose functions focus on keeping each function responsible for one clear task. A function should ideally do one thing well, making it easier to understand, test, and maintain. Functions should have meaningful names that describe their purpose, accept only the inputs they need, and avoid performing unrelated tasks. Keeping functions short reduces complexity and makes it easier to identify and fix errors. Developers should also avoid duplicating code by creating reusable functions for repeated logic. Small, focused functions improve readability, encourage code reuse, and make future changes safer and easier.

2. Find an example of a long, complex function in an existing codebase (or write your own).

**Long, Complex Function**
def register_user(username, email, password):
    # Validate username
    if username == "":
        return "Username required"

    if len(username) < 3:
        return "Username too short"

    # Validate email
    if "@" not in email:
        return "Invalid email"

    # Validate password
    if len(password) < 8:
        return "Password too short"

    # Check if user already exists
    existing_users = database.get_users()
    for user in existing_users:
        if user.email == email:
            return "User already exists"

    # Hash password
    hashed_password = hash_password(password)

    # Create user object
    user = {
        "username": username,
        "email": email,
        "password": hashed_password
    }

    # Save user to database
    database.save(user)

    # Send welcome email
    email_service.send(
        email,
        "Welcome to our platform!"
    )

    # Log registration
    logger.info(
        f"New user registered: {username}"
    )

    return "Registration successful"

3. Refactor it into multiple smaller functions with clear responsibilities.

**Smaller Functions with Clear Responsibilities**
def validate_username(username):
    if not username:
        return "Username required"

    if len(username) < 3:
        return "Username too short"

    return None


def validate_email(email):
    if "@" not in email:
        return "Invalid email"

    return None


def validate_password(password):
    if len(password) < 8:
        return "Password too short"

    return None


def check_existing_user(email):
    users = database.get_users()

    for user in users:
        if user.email == email:
            return True

    return False


def create_user(username, email, password):
    hashed_password = hash_password(password)

    return {
        "username": username,
        "email": email,
        "password": hashed_password
    }


def save_user(user):
    database.save(user)


def send_welcome_message(email):
    email_service.send(
        email,
        "Welcome to our platform!"
    )


def register_user(username, email, password):
    # Validate user information before creating an account
    errors = [
        validate_username(username),
        validate_email(email),
        validate_password(password)
    ]

    for error in errors:
        if error:
            return error

    # Prevent duplicate accounts
    if check_existing_user(email):
        return "User already exists"

    # Create and save the new user
    user = create_user(username, email, password)
    save_user(user)

    # Notify the user
    send_welcome_message(email)

    logger.info(f"New user registered: {username}")

    return "Registration successful"

4. Write reflections in clean_code.md:
- Why is breaking down functions beneficial?
- Breaking down functions into smaller, single-purpose functions improves code quality by making it easier to read, test, and maintain. Each function has a clear responsibility, which makes it easier for developers to understand what the code does and identify where problems occur. Smaller functions can be reused in different parts of an application and reduce the risk of introducing bugs when making changes. This approach also improves collaboration because other developers can modify or review individual components without needing to understand a large, complex function.

- How did refactoring improve the structure of the code?
- Refactoring improved the structure of the code by separating a large, complex function into smaller functions with clear responsibilities. Instead of handling validation, database checks, user creation, saving, and email notifications in one place, each task is now managed independently. This makes the code easier to read, test, and update because changes can be made to individual parts without affecting the entire system. The main register_user() function now clearly shows the overall process, improving maintainability and reducing complexity.

5. Commit and push your changes to GitHub.
Done

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


✅ Tasks

1. Research the "Don't Repeat Yourself" (DRY) principle.

- Don't Repeat Yourself (DRY) Principle

- The DRY (Don't Repeat Yourself) principle is a software development practice that aims to avoid repeating the same code or logic multiple times.

- Instead of copying and pasting code, repeated functionality should be placed into functions, classes, or reusable modules and called whenever it is needed.

- For example, instead of repeating:
print("Hello, John!")
print("Hello, Sarah!")
print("Hello, Alex!")

- We could create a reusable function:
def greet(name):
    print(f"Hello, {name}!")

greet("John")
greet("Sarah")
greet("Alex")

- DRY makes code shorter, easier to maintain, easier to update, and less likely to contain inconsistent bugs. If something needs to change, you can usually change it in one place instead of updating many duplicated sections.

2. Find a section of code in your test repo with unnecessary repetition.

print("User: Alice")
print("User: Bob")
print("User: Charlie")

3. Refactor the code to eliminate duplication.

users = ["Alice", "Bob", "Charlie"]

for user in users:
    print(f"User: {user}")

4. Write reflections in clean_code.md:
- What were the issues with duplicated code?

- Duplicated code made the program harder to read, maintain, and update. If the same logic appeared in several places, any change had to be repeated everywhere, which increased the chance of mistakes or inconsistent behaviour. Refactoring the repeated code into reusable functions, loops, or variables made the code cleaner, shorter, and easier to manage.

- How did refactoring improve maintainability?

- Refactoring improved maintainability by reducing duplicated code and making the program more organised. Repeated logic was moved into reusable functions or loops, meaning future changes only need to be made in one place. This makes the code easier to understand, update, test, and debug.

5. Commit and push your changes to GitHub.
Done