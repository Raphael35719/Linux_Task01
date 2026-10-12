# Git Bash — Publish This Project to GitHub

These commands run in **Git Bash on Windows**, from the extracted project folder. They do not perform the Linux task itself.

## 1. Extract and enter the folder
Extract `linux-task-01-secure-file-management.zip`, then in Git Bash:
```bash
cd /c/path/to/linux-task-01-secure-file-management
```
Replace the example path with the actual folder path on your computer.

## 2. Initialize Git and inspect files
```bash
git init
git status
git add README.md commands docs evidence scripts submission workflow
git status
git commit -m "Add Linux Task 01 workflow and evidence structure"
```

## 3. Create an empty GitHub repository
On GitHub, create a new repository, for example `linux-task-01-secure-file-management`. If you already created it, use its repository URL in the next step. Avoid adding a second README/license on GitHub if you want to push this existing project as-is.

## 4. Connect and push
Replace `YOUR-USERNAME` with your GitHub username:
```bash
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/linux-task-01-secure-file-management.git
git push -u origin main
```
If `origin` already exists, inspect it with `git remote -v`; use `git remote set-url origin <repository-url>` if you need to correct it.

## 5. Future updates
After adding screenshots or changing documentation:
```bash
git status
git add .
git commit -m "Add task evidence and verification notes"
git push
```

## Before pushing
- Check that no passwords, access tokens, private keys, or unrelated personal files are present.
- Ensure screenshots are your real evidence and do not expose secrets.
- Keep the original assignment in `submission/`.
