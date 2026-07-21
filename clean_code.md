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