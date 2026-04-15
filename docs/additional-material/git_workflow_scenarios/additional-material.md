# Additional information

We assume that you have already finished with the basic tutorial before coming here. This document will give you some additional information about advanced Git techniques.

### [Amending a commit](amending-a-commit.md)
This document provides information about how to amend a commit on the remote repository. Amending a commit is a way to modify the most recent commit you have made in your current branch. This can be helpful if you need to edit the commit message or if you forgot to include changes in the commit. You can continue to amend a commit until you push it to the remote repository.
> Use this when you need to adjust a commit you made.

### [Check commit log](check-commit-log.md)
This document explains how to review a branch's (or file's) commit history with `git log`, and lists useful flags such as `--oneline` and `-n`.
> Use this to inspect the commit history of your branch.

### [Cherry-picking a commit](cherry-picking.md)
This document explains how to use `git cherry-pick` to copy a single commit (or a range of commits) from one branch to another without merging the rest of the branch, and how to resolve conflicts that arise.
> Use this when you need one specific commit on your branch — e.g. a hotfix — without bringing along everything else.

### [Common mistakes and how to fix them](common-mistakes-and-how-to-fix-them.md)
A short FAQ for the things that go wrong most often for first-time contributors — wrong-branch commits, typo'd commit messages, PRs with merge conflicts, accidentally-committed secrets, rejected pushes, and how to recover from `git reset --hard` with the reflog.
> Start here when something has gone wrong and you want the quickest safe fix.

### [Configuring git](configuring-git.md)
This document provides information about how to configure user details and other options in git.
> Use this to better control your git configurations.

### [Creating a .gitignore file](creating-a-gitignore-file.md)
This document explains what a .gitignore file does, why to use it and how to create a .gitignore file. This file is used in almost all git projects. It helps commit only necessary files to git.

### [Deleting a branch locally](delete-branch-locally.md)
This document explains the difference between `git branch -d` and `git branch -D` and how to safely delete a local branch.
> Use this when you no longer need a local branch.

### [Finding a bug with git bisect](finding-a-bug-with-bisect.md)
This document explains how to use `git bisect` to binary-search through commit history and pinpoint the exact commit that introduced a bug, including how to skip untestable commits and automate the search with `git bisect run`.
> Use this when something used to work and you need to find the commit that broke it.

### [Git Flow](gitflow.md)
This document explains the Gitflow branching model — long-lived `develop` and `master` branches, feature/release/hotfix branches — and discusses when it is (and isn't) a good fit for a project.
> Read this if you want a structured release workflow for a larger project.

### [Installing Git on Arch](installing-git-arch.md)
This document walks through installing Git on Arch Linux and configuring user details.
> Use this if you're setting up Git on Arch Linux.

### [Installing Git on Ubuntu](installing-git-ubuntu.md)
This document walks through installing Git on Ubuntu, configuring user details, and caching or storing credentials.
> Use this if you're setting up Git on Ubuntu.

### [Keeping your fork synced with the repository](keeping-your-fork-synced-with-this-repository.md)
This document provides information about how to keep your forked repository up-to-date with the base repository. This is important, as hopefully you and many others will contribute to the project.
> Follow these steps if your fork doesn't have any changes in parent repository.

### [Moving a Commit to a different Branch](moving-a-commit-to-a-different-branch.md)
This document provides information about how to move a Commit to another Branch.
> Take these steps to move a commit to another branch.

### [Rebase vs Merge](rebase-vs-merge.md)
This document explains the difference between `git merge` and `git rebase`, when each is appropriate, and why you should never rebase a public/shared branch.
> Read this before you integrate changes from one branch into another.

### [Removing a branch from your repository](removing-branch-from-your-repository.md)
This document provides information about how to delete a branch from your repository.
> Only after your pull request gets merged, follow to next steps

### [Removing a File](removing-a-file.md)
This document provides information about how to remove a file from your local repository.
> Follow these steps to learn how to remove a file prior to a commit

### [Resetting a branch](resetting-a-branch.md)
This document explains how to reset one branch to match another using `git reset`, and when that's preferable to deleting and recreating the branch.
> Use this when you need one branch to mirror another without recreating it.

### [Resetting a commit](resetting-a-commit.md)
This document explains how to use `git reset` to move the repository back to a specific commit.
> Use this when you want to rewind your branch to an earlier commit.

### [Resolving Merge Conflicts](resolving-merge-conflicts.md)
This document provides information about how to resolve merge conflicts.
> Take these steps to resolve the annoying merge conflicts.

### [Reverting a commit](reverting-a-commit.md)
This document provides information about how to revert a commit on the remote repository. It will come in handy in case you need to undo a commit that has already been pushed to Github.
> Take these steps if you want to reverse a commit.

### [Signing your commits](signing-commits.md)
This document walks through signing commits with SSH (the simpler, modern path) or GPG so they show up with the green Verified badge on GitHub.
> Use this when a project requires signed commits, or when you want to prove a commit really came from you.

### [Squashing Commits](squashing-commits.md)
This document provides information about how to squash commits with an interactive rebase.
> Use this if you want to open a PR in an open source project and the reviewer asks you to squash every commit into one, with an informative commit message.

### [Stashing a file](stashing-a-file.md)
This document explains how to use `git stash` to temporarily shelve work-in-progress changes so you can switch branches without committing.
> Use this when you need to park unfinished changes and come back to them later.

### [Storing Credentials](storing-credentials.md)
This document explains how to store your credentials for repositories. This can be a security concern, so please follow the security policies of your place of work/study.

### [Undo-ing a local commit](undoing-a-commit.md)
This document provides information about how to undo a commit on your local repository. This is what you need to do when you feel you've messed up your local repository and wish to reset the local repository.
> Take these steps if you want to undo/reset a local commit.

### [Why use branches](why-using-branches.md)
This document explains what a branch is, why feature branches matter in collaborative development, and walks through creating, switching, and deleting branches.
> Read this if you're new to branching and want to understand why it exists.

### [Useful Links](Useful-links-for-further-learning.md)
This document is dedicated to all the tips and tricks websites, blog posts, and helpful sites that make our lives easier. They are a great reference to serve all of our needs, be it a beginner or an expert. This page should act as an index of all those useful links that would help everybody who is new in the open-source domain or someone who wants to learn more.
