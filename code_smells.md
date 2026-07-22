✅ Tasks

1. Research common code smells and how they impact code quality.
- Code smells are signs of poor code structure that can make software harder to maintain, understand, and modify. Common examples include long functions, duplicate code, unclear naming, deep nesting, dead code, and tightly connected components. These issues increase complexity, make bugs more likely, and slow down development. Refactoring code smells improves readability, reliability, and long-term maintainability.

2. Find or write code examples that demonstrate the following code smells:

- Magic Numbers & Strings – Using hardcoded values instead of constants.

def calculate_discount(price):
    return price * 0.15

- Long Functions – Functions that do too much and should be broken into smaller parts.

def process_order(order):
    validate_order(order)
    calculate_total(order)
    apply_discount(order)
    save_to_database(order)
    send_confirmation_email(order)
    update_inventory(order)
    create_invoice(order)

- Duplicate Code – Copy-pasting logic instead of reusing functions.

def calculate_student_total():
    price = 100
    tax = price * 0.1
    return price + tax

def calculate_staff_total():
    price = 200
    tax = price * 0.1
    return price + tax

- Large Classes (God Objects) – Classes that handle too many responsibilities.

class UserManager:
    def create_user(self):
        pass

    def send_email(self):
        pass

    def process_payment(self):
        pass

    def generate_report(self):
        pass

- Deeply Nested Conditionals – Complex if/else trees that make code harder to follow.

def access_account(user):
    if user:
        if user.active:
            if user.is_admin:
                return "Access granted"
            else:
                return "Admin required"
        else:
            return "Inactive account"
    else:
        return "No user found"

- Commented-Out Code – Unused code that clutters the codebase.

def calculate_price(price):
    return price * 1.1

- Inconsistent Naming – Variable names that don't clearly describe their purpose.

def process(x, y):
    a = x * y
    return a

3. Refactor the code to eliminate these code smells.
- Magic Numbers & Strings – Using hardcoded values instead of constants.

DISCOUNT_RATE = 0.15

def calculate_discount(price):
    return price * DISCOUNT_RATE

- Long Functions – Functions that do too much and should be broken into smaller parts.
- Improvement: Split into smaller functions such as validate_order(), save_order(), and send_email().

- Duplicate Code – Copy-pasting logic instead of reusing functions.

def calculate_total(price):
    tax = price * 0.1
    return price + tax

- Large Classes (God Objects) – Classes that handle too many responsibilities.
Split responsibilities into separate classes: UserManager, EmailService, PaymentProcessor, ReportGenerator

- Deeply Nested Conditionals – Complex if/else trees that make code harder to follow.

def access_account(user):
    if not user:
        return "No user found"

    if not user.active:
        return "Inactive account"

    if not user.is_admin:
        return "Admin required"

    return "Access granted"

- Commented-Out Code – Unused code that clutters the codebase.
# def old_calculate_price(price):
#     return price * 1.2

- Inconsistent Naming – Variable names that don't clearly describe their purpose.

def calculate_total_price(quantity, price):
    total_price = quantity * price
    return total_price

4. Write reflections in code_smells.md:
- What code smells did you find in your code?
- The code smells found were magic numbers, long functions, duplicate code, large classes, deeply nested conditionals, commented-out code, and inconsistent naming. These issues made the code harder to understand, maintain, and modify. For example, hardcoded values reduced flexibility, large functions handled too many responsibilities, and unclear names made the purpose of variables and functions difficult to identify. Refactoring these areas improved readability, reduced complexity, and made the code easier to maintain.

- How did refactoring improve the readability and maintainability of the code?
- Refactoring improved the readability and maintainability of the code by simplifying complex sections and giving each part a clear purpose. Long functions were split into smaller, focused functions, duplicate code was replaced with reusable logic, and unclear names were improved to make the code easier to understand. Removing code smells such as deep nesting and magic numbers also made future changes safer and reduced the chance of introducing bugs. Overall, the code became cleaner, easier to test, and simpler for other developers to work with.

- How can avoiding code smells make future debugging easier?
- Avoiding code smells makes future debugging easier by keeping the code organised, readable, and easier to understand. When functions have clear responsibilities and code is not duplicated or overly complex, developers can quickly locate the source of problems and fix them without affecting other parts of the system. Clear naming, proper structure, and reduced complexity also make it easier to identify errors and understand how different parts of the code interact. This saves time during troubleshooting and reduces the risk of introducing new bugs.

5. Commit and push your changes to GitHub.
Done