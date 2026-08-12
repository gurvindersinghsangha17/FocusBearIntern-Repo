# Jupyter Notebook Debugging Guide

## Common Debugging Techniques

There are several ways to debug problems in Jupyter notebooks, depending on the complexity of the issue.

### print() and display()

`print()` and `display()` are simple ways to inspect variable values and understand what the code is doing at different points. `display()` is especially useful in notebooks because it can show DataFrames, images, and other rich objects clearly.

### Jupyter Debugging Magics

Jupyter provides several built-in magic commands for debugging:

* `%debug` – Opens the debugger after an error occurs, allowing variables and the call stack to be inspected.
* `%pdb on` – Automatically starts the debugger whenever an exception occurs.
* `%xmode` – Changes the amount of information displayed in an error traceback. The available modes include Plain, Context, and Verbose.
* `%%debug` – Runs a notebook cell in debugging mode so the code can be stepped through while inspecting its behaviour.

## JupyterLab Visual Debugger

JupyterLab provides a visual debugger that works more like the debugging tools found in an IDE. It includes:

* **Breakpoints** – Pause execution at a selected line of code.
* **Variable Inspector** – View the values and types of variables while execution is paused.
* **Call Stack** – See the sequence of function calls that led to the current point.
* **Step Controls** – Move through code line by line or step into and out of functions.

The JupyterLab debugger is visual and button-based, while `pdb` and `ipdb` are command-based. With `pdb` or `ipdb`, commands such as `n` (next), `s` (step), `c` (continue), and `p` (print a value) are entered manually.

## Other Debugging Tools

Tools such as `icecream` and `snoop` can also make debugging easier.

* **icecream** provides a more informative alternative to `print()` by displaying both the expression being inspected and its value.
* **snoop** traces code execution and shows how variable values change as different lines execute.

These tools can be useful when more detailed information is needed without manually adding many print statements.

## Performance Debugging

Jupyter also provides tools for investigating slow code and excessive memory usage:

* `%time` – Measures how long a single statement takes to execute.
* `%timeit` – Runs code multiple times and reports an average execution time.
* `%prun` – Uses Python's `cProfile` profiler to identify functions that take the most execution time.
* `%lprun` – Uses `line_profiler` to measure execution time line by line within a function.
* `%memit` – Uses `memory_profiler` to measure the memory used by a piece of code.

These tools help identify performance bottlenecks and code that may be consuming unnecessary resources.

## Notebook State and Cell Execution Problems

One challenge with Jupyter notebooks is that cells can be executed in any order. This can leave old variables in memory or create hidden dependencies between cells.

Useful techniques include:

* **Restart Kernel + Run All** – Clears the current state and runs the notebook from beginning to end. This is one of the best ways to identify hidden dependencies and stale variables.
* `%reset` – Clears variables from the current namespace without completely restarting the kernel.
* `%who` and `%whos` – Display the variables currently stored in memory.
* `%debug` and `%pdb on` – Help inspect incorrect variable values when notebook state eventually causes an exception.

Running the notebook from a fresh kernel is particularly important before assuming that the notebook works correctly.

## Harder Notebook Issues

### Kernel Hangs

If a kernel becomes unresponsive because of an infinite loop or long-running operation, interrupting the kernel should be tried first. If it remains unresponsive, restarting the kernel clears the current execution state.

### Hidden State

Re-running cells in different orders can create variables or values that would not exist if the notebook were executed normally from top to bottom. Restarting the kernel and using **Run All** helps detect these problems.

### Memory Leaks

Memory usage can increase across multiple cell executions, particularly when large objects remain referenced in memory. Memory profiling tools such as `%memit` and `memory_profiler` can help identify code that is consuming excessive memory. Restarting the kernel can also confirm whether accumulated notebook state is contributing to the problem.

### Debugging Imported .py Modules

Code imported from external `.py` files can also be debugged from a notebook. The `autoreload` extension can automatically reload changed Python modules during development:

```python
%load_ext autoreload
%autoreload 2
```

This prevents the notebook from continuing to use an older imported version of a module after the `.py` file has been edited.

For errors inside external modules, `breakpoint()`, `%debug`, or JupyterLab debugging tools can be used to inspect the code and variables involved.

## Recommended Debugging Strategy

For most notebook problems, I would start with `print()` or `display()` for simple checks. If an exception occurs and the cause is unclear, I would use `%debug` or the JupyterLab debugger to inspect the program state.

For notebook-specific problems, I would restart the kernel and run all cells from the beginning to check for hidden state or out-of-order execution. If the problem is related to speed or memory, I would use profiling tools such as `%timeit`, `%prun`, or `%memit`.

Overall, the most effective approach depends on the problem. Simple debugging methods are usually best to try first, while interactive debuggers and profiling tools are more useful for complex problems.
