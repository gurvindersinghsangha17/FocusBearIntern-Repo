✅ Tasks

1. Research best debugging techniques for Jupyter notebooks.

- Explore Jupyter's built-in debugging magics: %debug (post-mortem), %pdb on (auto-drop into debugger on exception), %xmode (Plain / Context / Verbose tracebacks), and %%debug for cell-level stepping.

- Jupyter has several built-in debugging magics that help find and understand errors:

1. %debug – Opens the debugger after an error occurs, allowing you to inspect variables and see what caused the error.
2. %pdb on – Automatically opens the debugger whenever an exception/error occurs, saving you from running %debug manually.
3. %xmode – Changes how much information an error traceback displays:
    - Plain – basic error information.
    - Context – includes surrounding code for context.
    - Verbose – provides the most detailed traceback, including variable values.
4. %%debug – Runs an entire notebook cell in debugging mode, allowing you to step through the code line by line and inspect what happens.

- Learn how to use the JupyterLab visual debugger (breakpoints in the gutter, variable inspector, call stack) and how it differs from pdb/ipdb in classic notebooks.

- The JupyterLab visual debugger provides a graphical way to find and fix errors in notebook code.

1. Breakpoints – Click in the gutter beside a line number to pause execution at that line.
2. Variable Inspector – Shows the current values and types of variables while the program is paused.
3. Call Stack – Shows which functions were called to reach the current point, helping trace where an error came from.
4. Step controls – Let you move through the program line by line or step into/out of functions.

- Difference from pdb/ipdb: JupyterLab’s debugger is visual and button-based, similar to an IDE. pdb and ipdb, commonly used in classic notebooks, are text/command-based, where you type commands such as n (next), s (step), c (continue), and p (print a variable).

- Investigate debugging performance issues in notebooks using %time, %timeit, %prun (cProfile), %lprun (line_profiler), and %memit (memory_profiler).

- For performance debugging in Jupyter notebooks, these tools help identify code that is slow or uses too much memory:

1. %time – Measures how long a single statement takes to run.
2. %timeit – Runs code multiple times and gives an average execution time, making it more reliable for comparing performance.
3. %prun – Uses Python’s cProfile to show which functions take the most execution time.
4. %lprun – Uses line_profiler to measure performance line by line inside a function, helping find specific slow lines.
5. %memit – Uses memory_profiler to measure how much memory a piece of code uses.

2. Summarize key debugging strategies in jupyter_debugging.md.

- What are the most common debugging techniques in notebooks (print/display() vs %debug post-mortem vs the JupyterLab debugger vs tools like icecream / snoop)?

- The most common debugging techniques in Jupyter notebooks include:

1. print() / display() – The simplest approach. Use them to check variable values and see what the code is doing at different points. display() is especially useful for DataFrames, images, and other rich objects.
2. %debug – Used after an error occurs. It lets you inspect variables and move through the call stack to determine what caused the exception.
3. JupyterLab debugger – A more visual approach using breakpoints, variable inspection, call stacks, and step-by-step execution. It is useful for debugging larger or more complex code.
4. icecream – A lightweight alternative to print(). It automatically shows the expression being inspected along with its value, making debugging output easier to understand.
5. snoop – Traces the execution of code automatically, showing which lines run and how variable values change. It is useful when you want detailed information without manually adding many print statements.

- Which tools and magics are most effective for the typical notebook workflow (long-running kernels, stale state, out-of-order cell execution)?

- For typical Jupyter notebook problems such as long-running kernels, stale variables, and cells being run out of order, these techniques are most effective:

1. Restart Kernel + Run All – One of the best ways to catch stale state or hidden dependencies. It resets all variables and runs the notebook from top to bottom.
2. %reset – Clears variables from the current namespace without fully restarting the kernel.
3. %who / %whos – Shows which variables currently exist, helping identify old or unexpected variables left in memory.
4. %debug / %pdb on – Useful when stale or incorrect state eventually causes an exception, because you can inspect the values that caused the problem.
5. %time / %timeit – Useful for finding cells or operations that are taking unexpectedly long to execute.
6. JupyterLab debugger – Helpful for complex state problems because breakpoints and the variable inspector let you see how values change while code executes.

- How do you debug harder notebook-specific issues — kernel hangs, memory leaks across cells, hidden state from re-running cells, and code imported from .py modules (autoreload, breakpoints in external files)?

- Restarting the kernel helps expose hidden notebook state, memory profilers help track leaks, autoreload keeps imported modules updated, and breakpoint(), %debug, or JupyterLab breakpoints help debug code located outside the notebook.

3. Commit and push your changes to GitHub.
Done