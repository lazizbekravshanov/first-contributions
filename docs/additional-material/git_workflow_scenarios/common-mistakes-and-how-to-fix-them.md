# Common mistakes and how to fix them

Everyone makes these mistakes their first few times — the Git commands are correct, the outcome is not what you wanted. This guide is a FAQ of the things that go wrong most often for new contributors and the shortest safe fix for each.

If a situation below links to a deeper guide, follow that — the short version here is meant to get you unstuck, the linked guide explains *why*.

## "I committed to the wrong branch"

You made a commit on `main` (or some other branch) when you meant to commit it on your feature branch.

If you haven't pushed yet, you can move the commit:

```
git branch feature-branch          # create the branch here, at HEAD
git reset --hard HEAD~1            # rewind the current branch by one commit
git switch feature-branch          # the commit is waiting here
```

For more detail and the multi-commit case, see [Moving a commit to a different branch](moving-a-commit-to-a-different-branch.md).

## "I made a typo in my commit message"

If it's the most recent commit and you haven't pushed:

```
git commit --amend -m "The corrected message"
```

If you've already pushed, see [Amending a commit](amending-a-commit.md) — amending a pushed commit rewrites history and needs a force push.

## "My PR has merge conflicts"

GitHub will show you which files conflict. Pull the target branch into your branch locally, resolve the markers, stage, and commit. The full walkthrough is in [Resolving merge conflicts](resolving-merge-conflicts.md).

## "I accidentally committed a large file (or a build artifact)"

Add the file or directory to [`.gitignore`](creating-a-gitignore-file.md) so it won't sneak back in, then untrack the file:

```
git rm --cached path/to/large-file
git commit -m "Stop tracking large-file"
```

If the file was already pushed and is genuinely huge (hundreds of MB) — especially if GitHub rejected your push — the file needs to be removed from the repository's *history*, not just its latest commit. That's a heavier operation; the tool most people reach for now is [`git-filter-repo`](https://github.com/newren/git-filter-repo). Coordinate with maintainers before rewriting pushed history.

## "I forgot to create a branch — I committed straight to main"

Exactly the same as "I committed to the wrong branch" above. Create a branch at the current HEAD and rewind `main`:

```
git branch feature-branch
git reset --hard HEAD~1
git switch feature-branch
```

If you already pushed to `main` on your fork, that's usually fine — your fork is yours. Just open the PR from `feature-branch` once you've moved the commit.

## "My fork is behind the upstream repo"

Your fork doesn't automatically update when the original repo changes. See [Keeping your fork synced](keeping-your-fork-synced-with-this-repository.md) — the short version is:

```
git remote add upstream https://github.com/firstcontributions/first-contributions.git
git fetch upstream
git switch main
git merge upstream/main
git push origin main
```

You only need to add the `upstream` remote once.

## "I pushed sensitive data (API key, password, token)"

Treat any pushed secret as **already compromised** — someone may have cloned or forked the repo within seconds.

1. **Rotate the secret first.** Revoke the key/token/password in whichever service issued it, and create a new one. This is the step that actually stops the damage.
2. Remove the secret from the codebase. Store it in an environment variable or a secrets manager instead, and add it to `.gitignore` if it was in a config file.
3. Optionally, scrub it from history with [`git-filter-repo`](https://github.com/newren/git-filter-repo). This requires a force push and coordination with collaborators.

Rotating is non-negotiable; scrubbing history without rotating doesn't protect you, because the secret is already out.

## "git push is rejected (non-fast-forward)"

Someone (or you, from another machine) pushed to this branch after you last pulled. Pull their changes first, then push:

```
git pull --rebase origin <branch-name>
git push origin <branch-name>
```

`--rebase` keeps the history linear by replaying your commits on top of theirs. If you hit conflicts during the rebase, resolve them and run `git rebase --continue`.

## "I want to undo a `git reset --hard`"

If you haven't garbage-collected yet (within the last couple of weeks, by default), your commits are still reachable via the reflog:

```
git reflog
```

Find the commit hash from *before* your reset, then:

```
git reset --hard <that-hash>
```

The reflog is your safety net for almost every "oh no" moment involving a lost commit — check it before assuming work is gone.

## "I have unpushed changes but I need to switch branches"

Use `git stash` to park them:

```
git stash
git switch other-branch
# ... do what you need ...
git switch original-branch
git stash pop
```

See [Stashing a file](stashing-a-file.md) for more.

---

If you're stuck and none of the above matches, open an issue on the project you're contributing to and describe what you tried. Maintainers would much rather help untangle a mistake than see you give up.
