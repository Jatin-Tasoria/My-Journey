# Forking ang Pull request

## Fork
Your own copy of someone else's GitHub repo.

Steps:
1. Go to any GitHub repo (even your friend’s)
2. Click Fork
3. Clone your fork:
```git
git clone <your-fork-url>
```
4. Add the original repo as "upstream":
```git
git remote add upstream <original-repo-url>
```
5. Pull updates from upstream:
```git
git pull upstream main
```

> This is VERY important for open-source contributions.

## protected Branches
Enable it:
- GitHub Repo → Settings → Branches → Add Rule

Enable options:
- Require PR before merging
- Require at least 1 approval
- Block direct pushes to main

>This is how real teams prevent mistakes.

## Pull Request (PR)
It is a way to ask the repository owner to review and merge your changes into another branch (usually main).

### What happens in a Pull Request?

- You create a new branch
- You make changes & commit
- You push that branch to GitHub
- You open a Pull Request
- Someone reviews
- Changes are merged