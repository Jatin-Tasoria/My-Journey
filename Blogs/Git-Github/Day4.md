# Merging conflicts,Previous version, Push & Pull from github

## Merging conflicts
Conflicts can occur when changes are made to the same section of the same file in the **main** branch and the branch we created.

In this case you have to solve the conflict manually.

Example conflict marker
```
<<<<<<< HEAD
Your content
=======
Incoming branch content
>>>>>>> feature-branch
```

To resolve:
1. Edit the file → choose correct content
2. Remove conflict markers
3. Add file
```
git add file.txt
```
4. Complete merge
```
git commit
```

---

## Checking previous version
Earlier we said that git helps in managing previous versions of file, s now we are going to see how.
- git checkout <Comment ID>

> To check previous comments and IDs run : git log --oneline.
> To go back to the latest commit : git checkout main

---

## Push & Pull
- Push : To push changes made in local repository to git hub repository
```git
git push origin <Branch Name>
```

- Fetch : Bringing remote changes to local but not merging them
```git
git fetch
```

- Pull : Fetching + Merging
```git
git pull
```