# Small but powerful git additions (Must-have)

## `.gitignore`
The `.gitignore` file tells Git which files or folder to ignore so they are not tracked or committed.

This is expected in real projects and interviews.

### Why `.gitignore` is used?
- Prevents committing sensitive data.
- Avoid unnecessary files in version control.
- Keeps Repository clean.

### Examples
```bash
node_modules/
.env
*.log
dist/
target/
```

---

## git diff
Used to see changes before committing.

### Commands
```bash 
git diff
```
Used to get difference between working directory and staging area.

```bash 
git diff --staged
```
Shows changes between staging area and last commit.

---

## Commit Message
Good commit message show **discipline** and **maturity**.

### Rules to follow: 
- Use present tense
   ✅ Add login validation.
   ❌  Added login validation.
- Be clear and descriptive.
- keep one logical change per commit.
- Avoid vague message like:
  - `fix`
  - `update`
  - `changes`
- Keep the first line under 50 characters.
- Optional : Explain ``why`` in the message if needed.

---

## Mini real world git flow
This is how Git is used in companies

### Real-World Git Workflow:

1. Create a new branch
```bash
git checkout -b feature-branch
```
2. Make code changes
3. Stage and commit
```bash
git add .
git commit -m "Add feature X"
```
4. Push to remote
```bash
git push origin feature-branch
```
5. Open a Pull Request (PR) on GitHub
6. Team reviews the code
7. Merge into main branch

---