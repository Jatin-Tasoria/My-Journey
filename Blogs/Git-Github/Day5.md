# Git stash, revert, rebase and cherry-pick

## Stash
Saving files without committing.

### Commands
- git stash : Save uncommitted work
- git stash list : Shows Stash list
- git stash apply : Apply stash back
- git stash drop : Remove stash
- git stash push -m "MESSAGE" : Save stash with message

## Revert
Fixing an old mistake without removing it.
Creates a new commit opposite of bad commit.

- git revert <Commit-id>

## Rebase
Move your commits to a new base commit.
It rewrites commit history to make it clean and linear.

- git rebase main

## Cherry-pick
Copy a specific commit from one branch to another.

- git cherry-pick <commit-id>