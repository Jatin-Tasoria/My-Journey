# Core Concepts

## Installing and configuration

[![Install Java](https://img.shields.io/badge/Install_Git-orange?style=for-the-badge)](https://git-scm.com/install/)

Once Installed, you can verify it by using
```bash
git --version
```
After verification t configure git on local machine use
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --global color.ui auto
```

## Working Directory, Staging Area & Repository (Concept + Demo)

Understand these 3 areas clearly:

- **Working Directory** → Where you edit files
- **Staging Area** → Files marked ready to commit
- **Repository** → Permanent commits stored

## Creating git repositories
There are two ways of making a git repo-
- Local
- Remote

### **Steps to create Local repo**

1. Open terminal/cmd.
2. Go to your destination folder using "cd" command.
3. Once in your destination folder, make a directory using "mkdir" command.
4. Create files in your directory.
   1. For MacOs/Linux: Use "touch" command.
   2. For Windows: Use "type nul > filename" command.
5. Type "git init" to initialize git folder.
6. TO check whether the folder is initialized.
   1. For MacOs/Linux: Use "ls -la" command.
   2. For Windows: Use "dir /a" command.
7. If initialized you will see a .git file.

### **Steps to create remote repo**

1. Goto www.github.com/your-profile.
2. Goto Repositories and click on New.
3. Initialize the name of the repository and Click on Create.
4. Once created, open the repository and Click on code.
5. Copy the https link. 
6. Open terminal/cmd.
7. Type "git clone paste-the-link".
8. Your remote repository will be shown on your device.


> **Note**: This will be your Working directory.


## Checking status of files
To check if any changes were made in your project and see which files are being tracked by Git, we use:

```bash
git status
```

---

## Adding files to staging area
To save changes made in the directory we use:
1. For staging everything in the project.
    
```bash
    git add -A
        Or
    git add --all
```
2. For staging  only files in the current directory.
```bash
    git add .
```
3. For staging only modified or new files.
```bash
    git add *
```
4. For staging only one file.
```bash
    git add <filename>
```
For undoing in the Staging area, we use:
```bash
git reset
```
---

## Committing the changes
After you are sure that the files in the staging are final, you can commit the changes in repository.
We use:
```bash
git commit -m "Your-Message"
```
For undoing the commit changes, we use:
```bash
git reset HEAD~
```
---