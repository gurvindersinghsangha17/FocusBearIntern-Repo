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