**Important Workflows (Git & GitHub)**


---

### **1. First-Time Upload of Local Project to GitHub** (Very Important)

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <repository-url>
git push -u origin main
```

---

### **2. Daily Working Workflow**

```bash
# 1. Check status
git status

# 2. Stage changes
git add .

# 3. Commit
git commit -m "Added login feature"

# 4. Push to GitHub
git push origin main
```

---

### **3. Feature Branch + Pull Request Workflow** (Most Important)

```bash
# 1. Create and switch to new branch
git switch -c feature-login

# 2. Make changes → Stage → Commit
git add .
git commit -m "Added login page"

# 3. Push the feature branch
git push -u origin feature-login

# 4. Go to GitHub → Create Pull Request (PR)
# 5. After PR is merged on GitHub:

# 6. Switch back to main
git switch main

# 7. Pull the latest changes
git pull origin main

# 8. Delete local branch (optional)
git branch -d feature-login
```

---

### **4. Resolving Merge Conflict**

```bash
# After git merge or git pull shows conflict:

# 1. Open the conflicted file
# 2. Remove conflict markers (<<<<<<< ======= >>>>>>>)
# 3. Keep the correct code
# 4. Stage the resolved file
git add filename

# 5. Complete the merge
git commit -m "Resolved merge conflict"
```

---

### **5. Using Stash (When you need to switch branch urgently)**

```bash
# Save current uncommitted work
git stash

# Switch branch
git switch main

# Later come back and restore work
git switch feature-login
git stash pop
```

---

### **6. Cloning an Existing Repository**

```bash
git clone <repository-url>
cd folder-name
```

---

### **7. Creating a Tag (Release)**

```bash
git tag -a v1.0.0 -m "First stable release"
git push origin v1.0.0
```

---

### **Quick Revision – Most Asked Workflows**

| Workflow                        | Key Commands                                      | Priority |
|--------------------------------|----------------------------------------------------|---------------|
| Upload new project             | `init` → `add` → `commit` → `remote add` → `push` | High          |
| Daily work                     | `status` → `add` → `commit` → `push`              | High          |
| Feature + Pull Request         | `switch -c` → `add` → `commit` → `push` → PR      | Very High     |
| Resolve Conflict               | Edit file → `git add` → `git commit`              | High          |
| Temporary save work            | `git stash` → `git stash pop`                     | Medium        |

---

