# Branching, Merging & undoing changes


## What is Branching?
It allows to create separate workspaces within the same project.

### Why it matters?
- Work on new features without breaking main code
- Experiment freely
- Collaborate easily
- Switch between tasks anytime

### Commands
- git branch : To check all branches.
- git branch < branch name> : To create a new branch.
- git checkout < branch name> : To switch to that particular branch.

---

## Merging
Combining the two separate branches into one.

> If the changes made in another branch, it will not be visible in main branch until it's merged in the main branch.

### Commands
- git merge < branch name> -m "Comment" : To merge branch into another branch.

> For it to work make sure you are on the branch you are supposed to merge in.
> For eg: I you want to merge in main branch you need to be in merge branch.

---

## Undoing changes
Undoing changes is one of the most powerful skill in git.  

### Commands
- git restore < filename> : Undo changes in working directory.
- git restore --staged < filename> : To unstage a file.
- git reset [options] HEAD~
  -  --soft : Keep everything staged.
  -  --mixed : keep changes in working directory.
  -  --hard : **Delete** changes
- git revert : safest way to undo changes.