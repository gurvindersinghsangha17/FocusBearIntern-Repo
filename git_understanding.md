# Git Bisect

## Research

`git bisect` is a Git debugging tool used to find the specific commit that
introduced a bug. It uses binary search between a known working commit and a
known broken commit.

Instead of manually reviewing every commit, Git checks commits in the middle of
the selected range. After testing each commit, I mark it as either:

`git bisect good`

or:

`git bisect bad`

Git continues narrowing down the history until it identifies the first bad
commit.

When finished, I use:

`git bisect reset`

to return to my original branch.

## Test Scenario

I created four commits for the test:

1. `0f9179b` - Added the first working version.
2. `74bc80e` - Updated the file while it was still working.
3. `d4e0ce9` - Introduced the bug.
4. `0503a05` - Made another change while the bug was still present.

I started the bisect process with:

`git bisect start`

I marked the latest broken commit as bad using:

`git bisect bad`

I then marked the last known working commit as good using:

`git bisect good 74bc80e`

Git checked the commit in between. I tested the file and found:

`BUG - broken version`

I then marked that commit as bad using:

`git bisect bad`

Git identified the following as the first bad commit:

`d4e0ce9 - test: introduce bisect bug`

This confirmed that commit `d4e0ce9` introduced the issue.

After the test, I used:

`git bisect reset`

to return to my original branch.

## Reflection

### What does `git bisect` do?

`git bisect` helps find the commit that introduced a bug. It uses binary search
between a known good commit and a known bad commit, allowing Git to quickly
narrow down where the problem started.

### When would you use it in a real-world debugging situation?

I would use `git bisect` when a feature previously worked but is now broken and
I do not know which commit caused the problem. It is especially useful when
there are many commits between the working and broken versions.

### How does it compare to manually reviewing commits?

`git bisect` is faster and more efficient than manually checking every commit.
Instead of reviewing commits one by one, it repeatedly reduces the number of
possible commits until the first bad commit is found.

In my test scenario, it helped me identify the exact commit that introduced the
bug without manually reviewing the complete commit history.
