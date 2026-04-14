# Deleting a locally created Branch

This will be handy when you accidentally misspelled a branch name.

This can be done in *3* ways

```
git branch -D <branch_name>
```

```
git branch --delete --force <branch_name>  # Same as -D
```

```
git branch --delete  <branch_name>         # Errors if the branch is unmerged
```

`-D` is shorthand for `--delete --force`, which deletes the branch even if it has unmerged changes. `-d` (shorthand for `--delete`) refuses to delete a branch that still has unmerged commits, so you don't lose work by accident.