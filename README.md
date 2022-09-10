# Lets-Learn-Git
## How do I revert a Git repository to a previous commit?
## Hard delete unpublished commits
If, on the other hand, you want to really get rid of everything you've done since then, there are two possibilities. One, if you haven't published any of these commits, simply reset:

// This will destroy any local modifications.
// Don't do it if you have uncommitted work you want to keep.
git reset --hard 0d1d7fc32

// Alternatively, if there's work to keep:
git stash
git reset --hard 0d1d7fc32
git stash pop
// This saves the modifications, then reapplies that patch after resetting.
// You could get merge conflicts, if you've modified things which were
// changed since the commit you reset to.
