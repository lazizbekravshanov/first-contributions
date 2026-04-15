# Finding a bug with git bisect

Something used to work and now it doesn't, but you have no idea which commit broke it. You could read through every commit since the last known-good version, but if there are hundreds of them, that's slow. `git bisect` turns it into a binary search: mark one commit as "good", another as "bad", and Git walks you through the history in O(log n) steps, asking you at each stop whether the code works.

## When to use bisect

- A feature that worked last week is broken today, and you want to find the commit that broke it.
- A test started failing, and you need to know which change is responsible.
- You're reporting a bug upstream and want to pin down the exact commit that introduced it.

You don't need to understand the bug to use bisect — you just need a reliable way to tell whether a given commit is "good" or "bad".

## Running a bisect

Start a bisect session:

```
git bisect start
```

Mark the current commit (where the bug is reproducing) as bad:

```
git bisect bad
```

Then mark a commit you know was working as good. This is usually an older tag or commit hash:

```
git bisect good v1.2.0
```

Git will now check out a commit roughly halfway between the two and print something like:

```
Bisecting: 12 revisions left to test after this (roughly 4 steps)
```

Build the project, run the test or reproduce the bug, and tell Git what you found:

```
git bisect good    # bug is NOT present here
```

or

```
git bisect bad     # bug IS present here
```

Repeat until Git narrows it down to a single commit and prints something like:

```
a1b2c3d is the first bad commit
commit a1b2c3d
Author: Someone <someone@example.com>
Date:   ...
    Refactor user lookup
```

That's the commit that introduced the bug.

## Finishing up

When you're done, reset your working tree back to the branch you started from:

```
git bisect reset
```

This leaves you where you were before the bisect started. Without it, your `HEAD` stays detached at the last commit Git checked out.

## If you hit a commit that can't be tested

Some commits in the range might not build, or might be unrelated branches merged in. Skip them and Git will pick a different commit to test:

```
git bisect skip
```

If too many commits in a row can't be tested, Git will tell you and you can widen the range or bisect a subset.

## Automating the search

If you have a command that exits `0` when the bug is absent and non-zero when it's present (for example a failing test), `git bisect run` will do the whole search for you without asking:

```
git bisect start HEAD v1.2.0
git bisect run ./run-tests.sh
```

Git will build, run the script at each step, and stop on the first bad commit — no input required from you.

## A word of caution

Bisect only works if the "bad" symptom is caused by a single commit inside the range and your good/bad markers are correct. If you mark a commit as "good" that actually contained the bug (you didn't notice it at the time), bisect will lead you astray. When in doubt, pick a known-good tag — like the last release — as your "good" anchor.
