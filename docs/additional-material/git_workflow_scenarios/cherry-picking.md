# Cherry-picking a commit

What if there is one specific commit on another branch — a bug fix, a small feature, a config tweak — that you want on your branch, *without* merging everything else? That's what `git cherry-pick` is for. It takes the changes introduced by an existing commit and reapplies them as a new commit on your current branch.

## When to cherry-pick (and when not to)

Cherry-pick when:
- You need a hotfix from `main` on a release branch, but don't want the rest of `main`.
- A useful commit lives on a branch that isn't ready to merge.
- You accidentally committed to the wrong branch and want to move just one commit.

Avoid cherry-picking when:
- You want *all* the changes from another branch — use `git merge` or `git rebase` instead.
- The commit has already been merged into your branch — cherry-picking it again will create a duplicate commit with the same changes.

## How to cherry-pick

First, find the commit you want. `git log --oneline` is the easiest way — the short hash on the left is what you'll need:

```
git log --oneline <branch-name>
```

You should see something like:

```
a1b2c3d Fix off-by-one in pagination
d4e5f6a Add caching to user lookup
9a8b7c6 Update README
```

Switch to the branch where you want the commit to land:

```
git switch <your-branch>
```

Then cherry-pick the commit by its hash:

```
git cherry-pick a1b2c3d
```

Git will reapply the changes and create a new commit on your branch. The new commit has a different hash from the original — that's expected. The commit message is reused.

## Cherry-picking a range of commits

To pick several consecutive commits, pass a range. The `^` on the left-hand side makes it inclusive:

```
git cherry-pick a1b2c3d^..d4e5f6a
```

This picks every commit from `a1b2c3d` through `d4e5f6a`, in order.

## Resolving conflicts during a cherry-pick

If the commit touches lines that have also been changed on your branch, Git will pause and ask you to resolve the conflict — the same process as a merge conflict. Open the conflicted files, pick the right version of each conflicted section, then stage your fixes and continue:

```
git add <resolved-files>
git cherry-pick --continue
```

If you'd rather bail out entirely and leave your branch as it was:

```
git cherry-pick --abort
```

For help resolving the conflicts themselves, see [Resolving Merge Conflicts](resolving-merge-conflicts.md).

## A note on duplicate history

Cherry-picking creates a *new* commit with the same changes, not a pointer to the original. That means the same change can appear on two branches with two different hashes. That's fine for a hotfix, but if you later merge one branch into the other, Git usually handles the duplicate gracefully (it sees no new changes to apply). If you see odd duplicate commits in your history, it's often because the same change was cherry-picked *and* later merged.
