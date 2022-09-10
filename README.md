# Lets-Learn-Git
## How to reset, revert, and return to previous states in Git
## Hard delete unpublished commits
If, on the other hand, you want to really get rid of everything you've done since then, there are two possibilities. One, if you haven't published any of these commits, simply reset:
```diff
# This will destroy any local modifications.
# Don't do it if you have uncommitted work you want to keep.
git reset --hard 0d1d7fc32

# Alternatively, if there's work to keep:
git stash
git reset --hard 0d1d7fc32
git stash pop
# This saves the modifications, then reapplies that patch after resetting.
# You could get merge conflicts, if you've modified things which were
# changed since the commit you reset to.
```

## Reverting Working Copy to Most Recent Commit
To revert to the previous commit, ignoring any changes:

```git reset --hard HEAD```

where HEAD is the last commit in your current branch

## How to reset a Git commit
Let's start with the Git command reset. Practically, you can think of it as a "rollback"—it points your local environment back to a previous commit. By "local environment," we mean your local repository, staging area, and working directory.

Take a look at Figure 1. Here we have a representation of a series of commits in Git. A branch in Git is simply a named, movable pointer to a specific commit. In this case, our branch master is a pointer to the latest commit in the chain.

![Local Git environment with repository, staging area, and working directory](https://opensource.com/sites/default/files/uploads/gitcommands1_local-environment.png)

If we look at what's in our master branch now, we can see the chain of commits made so far.

```
$ git log --oneline
b764644 File with three lines
7c709f0 File with two lines
9ef9173 File with one line
```
