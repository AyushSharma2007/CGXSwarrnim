**All Git & Git Bash Commands – Module-wise**

---

### **Module 1: Introduction to VCS**
No commands (purely conceptual).

---

### **Module 2: Git, GitHub & Development Environment**
No Git commands (conceptual + VS Code overview).

---

### **Module 3: CLI, GUI & Essential Git Bash Commands**

**Navigation**
```bash
pwd
cd foldername
cd ..
cd ../..
cd ~
cd -
```

**Listing Files**
```bash
ls
ls -l
ls -a
ls -la
```

**Create / Remove**
```bash
mkdir foldername
rmdir foldername
touch filename
echo "text" > file.txt
```

**File Operations**
```bash
cat filename
cp file1 file2
cp -r folder1 folder2
mv oldname newname
mv file folder/
rm filename
rm -r foldername
rm -rf foldername          # Force delete (be careful)
```

**Other Useful**
```bash
clear
date
whoami
history
exit
git --version
git -v
```

---

### **Module 4: Git Configuration & Core Concepts**

```bash
# Configuration
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --global user.name          # Check name
git config --global user.email         # Check email
git config --list                      # See all config

# Clone
git clone <HTTPS-URL>
git clone https://github.com/username/project-name.git
```

---

### **Module 5 & 6: Basic Git Commands & Workflow**

```bash
git status
git add .
git add filename
git add file1 file2
git commit -m "Meaningful message"
git log
git log --oneline
git push origin main
git push -u origin main                # First push (sets upstream)
git remote -v
```

**Complete first-time push of a new local project**
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/repo-name.git
git branch -M main
git push -u origin main
```

---

### **Module 7–11: Branching + Pull Request Workflow**

**Branching**
```bash
git branch                             # List branches
git branch feature-name                # Create branch
git switch feature-name                # Switch (modern)
git checkout feature-name              # Switch (old)
git switch -c feature-name             # Create + Switch (modern)
git checkout -b feature-name           # Create + Switch (old)
git switch main
git merge feature-name
git branch -d feature-name             # Safe delete
git branch -D feature-name             # Force delete
```

**Pull / Fetch**
```bash
git pull
git pull origin main
git fetch
git fetch origin main
git merge origin/main
```

**Remote branch management**
```bash
git push -u origin feature-name
git push origin --delete feature-name
```

**Full Professional PR Workflow**
```bash
git switch main
git pull origin main
git switch -c feature/login
# make changes
git add .
git commit -m "Add login page"
git push -u origin feature/login
# → Create PR on GitHub → Review → Merge
# After merge:
git switch main
git pull origin main
git branch -d feature/login
```

---

### **Module 12–13: Merge Conflicts + Diff**

```bash
git status                             # See conflicted files
# Open file → remove <<<<<<< ======= >>>>>>> markers
git add .
git commit -m "conflict resolved"
git push
```

**Diff Commands**
```bash
git diff                               # Unstaged changes
git diff --staged                      # Staged changes
git diff --cached                      # Same as --staged
```

---

### **Module 15: git restore, rm, .gitignore**

```bash
git restore filename                   # Discard changes in working directory
git restore --staged filename          # Unstage a file

rm filename                            # Delete file (normal)
git rm filename                        # Delete + stage the deletion
git rm --cached filename               # Stop tracking but keep the file locally
```

---

### **Module 16–17: git reset & git revert**

```bash
git reset --soft HEAD~1                # Undo commit, keep changes staged
git reset --mixed HEAD~1               # Undo commit, keep changes unstaged (default)
git reset --hard HEAD~1                # Undo commit + discard all changes (dangerous)
git reset <commit-hash>

git revert HEAD
git revert <commit-hash>
git revert --no-edit <commit-hash>
git revert --no-commit <commit-hash>
git revert --continue
git revert --abort
git revert --quit
```

---

### **Module 18: git reflog (Recovery)**

```bash
git reflog
git checkout <commit-hash>             # Go to lost commit (detached HEAD)
git switch -c recovery-branch          # Create branch from it
git switch main
git merge recovery-branch
git branch -d recovery-branch
```

---

### **Module 19: git stash**

```bash
git stash                              # Stash tracked changes
git stash push
git stash -u                           # Include untracked files
git stash --include-untracked
git stash -a                           # Include ignored files too
git stash --all
git stash push -m "WIP: login feature"

git stash list
git stash show
git stash show stash@{0}
git stash show stash@{0} -p            # Full patch

git stash apply
git stash apply stash@{0}
git stash pop
git stash pop stash@{0}

git stash drop
git stash drop stash@{1}
git stash clear                        # Delete all stashes
```

---

### **Module 20: Git Tags**

```bash
git tag v1.0                           # Lightweight tag
git tag -a v1.0.0 -m "First release"   # Annotated tag (recommended)
git tag -a v0.9.0 <commit-hash> -m "Beta"

git tag                                # List tags
git tag -l "v1.*"
git show v1.0.0

git push origin v1.0.0
git push origin --tags

git tag -d v1.0.0                      # Delete local
git push origin --delete v1.0.0        # Delete remote

git switch --detach v1.0.0             # View old version
git switch -c hotfix v1.0.0            # Create branch from tag
```

---

### **Module 21: Git Rebase**

```bash
git switch feature-branch
git fetch origin
git rebase origin/main
# or
git rebase main

# During conflict
git status
# fix files
git add .
git rebase --continue

git rebase --abort
git rebase --skip

git push --force-with-lease origin feature-branch
```

---

### **Module 22: Git Cherry-Pick**

```bash
git switch main
git log --oneline
git cherry-pick <commit-id>
git cherry-pick <commit1> <commit2>
git cherry-pick <start>..<end>         # Excludes start
git cherry-pick <start>^..<end>        # Includes start

# During conflict
git add .
git cherry-pick --continue
git cherry-pick --abort
git cherry-pick --skip
```

---

### **Most Used Daily Commands (Quick Sheet)**

```bash
git status
git add .
git commit -m "message"
git push
git pull
git switch -c feature/name
git branch
git log --oneline
git stash
git restore --staged filename
```

---


**Important Commands (Git & GitHub)**


---

### **1. Configuration**
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --list
```

---

### **2. Starting a Project**
```bash
git init                          # Create new local repository
git clone <url>                   # Copy remote repository to local
```

---

### **3. Basic Daily Commands**
```bash
git status                        # Check current state
git add .                         # Stage all changes
git add filename                  # Stage specific file
git commit -m "message"           # Save snapshot locally
git log --oneline                 # View short commit history
git push origin main              # Upload commits to GitHub
git push -u origin main           # First time push
```

---

### **4. Connecting Local Project to GitHub (Very Important)**
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin <url>
git branch -M main
git push -u origin main
```

---

### **5. Branching Commands**
```bash
git branch                        # List all branches
git switch -c feature-name        # Create + switch to new branch (modern)
git checkout -b feature-name      # Create + switch (old style)
git switch main                   # Switch to main
git merge feature-name            # Merge feature into current branch
git branch -d feature-name        # Delete branch (safe)
```

---

### **6. Pull Request Related**
```bash
git push -u origin feature-name   # Push feature branch
git pull origin main              # Update local main after PR is merged
git push origin --delete feature-name   # Delete remote branch
```

---

### **7. Stash (Temporarily save work)**
```bash
git stash                         # Save uncommitted changes
git stash -u                      # Include untracked files
git stash list                    # See all stashes
git stash pop                     # Restore latest stash
git stash apply                   # Restore but keep stash
```

---

### **8. Tags**
```bash
git tag -a v1.0.0 -m "First release"   # Create annotated tag
git tag                               # List tags
git push origin v1.0.0                # Push tag to GitHub
```

---

### **9. Undo / Reset / Revert**
```bash
git restore filename                  # Discard changes in file
git restore --staged filename         # Unstage a file
git reset --soft HEAD~1               # Undo commit (keep changes staged)
git reset --mixed HEAD~1              # Undo commit (keep changes unstaged)
git reset --hard HEAD~1               # Undo commit + discard changes
git revert HEAD                       # Safely undo a commit (creates new commit)
```

---

### **10. Other Useful Commands**
```bash
git remote -v                         # Check remote URL
git diff                              # See unstaged changes
git diff --staged                     # See staged changes
git rm filename                       # Delete file + stage deletion
git rm --cached filename              # Stop tracking file but keep it
```

---

### **Most Important (Must Remember)**

| Purpose                        | Command                          |
|--------------------------------|----------------------------------|
| Stage all files                | `git add .`                      |
| Commit changes                 | `git commit -m "message"`        |
| Check status                   | `git status`                     |
| View short history             | `git log --oneline`              |
| First time push                | `git push -u origin main`        |
| Create + switch branch         | `git switch -c feature-name`     |
| Temporary save work            | `git stash`                      |
| Mark a release                 | `git tag -a v1.0.0 -m "msg"`     |
| Safe undo of commit            | `git revert HEAD`                |

---

** Workflow commands to create a local folder to git repo and push your code:**  

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin <url>
git branch -M main
git push -u origin main
```


