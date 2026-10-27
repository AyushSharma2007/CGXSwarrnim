**Git & GitHub – Short & Simple Revision Notes**  

---

### **Module 1: Introduction to Version Control Systems (VCS)**

**Why do we need VCS?**  
Without VCS we get files like:  
`final.doc`, `final2.doc`, `final_final.doc`, `final_v2_by_priya.doc`  

**Problems**: Confusing names, hard to know latest version, no history, risk of overwriting, messy collaboration.

**What is VCS?**  
A software tool that tracks changes, keeps complete history, allows rollback, and supports safe collaboration.

**Three Types of VCS**

| Feature                  | Local VCS              | Centralized (CVCS)          | Distributed (DVCS)                  |
|--------------------------|------------------------|-----------------------------|-------------------------------------|
| History stored           | Only on local PC       | Only on central server      | On **every** developer’s machine    |
| Collaboration            | Not possible           | Good                        | Excellent                           |
| Works offline            | Yes                    | Limited                     | Fully                               |
| Single point of failure  | Yes (your PC)          | Yes (server)                | **No**                              |
| Examples                 | RCS, SCCS              | CVS, SVN, Perforce          | **Git**, Mercurial                  |

**Advantages of VCS**  
1. Complete history  
2. Easy rollback  
3. Better collaboration  
4. Backup  
5. Branching & experimentation  
6. Accountability  
7. No more “final_final” files

**Why is Git most popular?**  
Created by Linus Torvalds (2005). Distributed, very fast, powerful branching, free, open-source, industry standard.

---

### **Module 2: Git, GitHub & Development Environment**

**Git** = Distributed Version Control System (software that runs on **your computer**).

**GitHub** = Cloud platform (website) that hosts Git repositories.

**Git vs GitHub**

| Point              | Git                              | GitHub                              |
|--------------------|----------------------------------|-------------------------------------|
| Type               | Version Control Software         | Cloud Platform / Website            |
| Location           | Your computer                    | Internet (cloud)                    |
| Main purpose       | Track changes & manage versions  | Host, share & collaborate           |
| Internet needed?   | No (works offline)               | Yes (for push/pull)                 |
| Created by         | Linus Torvalds                   | GitHub Inc. (Microsoft)             |
| Analogy            | Taxi service                     | Uber / Ola                          |

**You can use Git without GitHub, but not GitHub effectively without Git.**

**Repository (Repo)** = Storage space for project files + complete history.  
- Local Repo → on your computer  
- Remote Repo → on GitHub

**Development Environment** = Complete set of tools needed to write, test and manage code (VS Code, Git, GitHub, Terminal, Browser, etc.).

**IDE** = Integrated Development Environment (Code editor + Terminal + Debugger + File explorer + Extensions).  
**VS Code** is the most popular free lightweight editor.

---

### **Module 3 & 4: CLI/GUI + Core Concepts + Configuration**

**CLI** = Command Line Interface (type commands – Git Bash).  
**GUI** = Graphical User Interface (mouse + buttons).

Professionals prefer **CLI (Git Bash)** because it is faster, more powerful, gives full control, and is the industry standard.

**Git Configuration (do only once)**
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --list
```

**Important Concepts**

- **Staging Area (Index)** → Temporary area between Working Directory and Local Repository. Only staged files can be committed.  
- **Commit** → Snapshot of staged changes saved in **local** repository.  
- **Branch** → Independent line of development (default = `main`).  
- **Clone** → Copy remote repo to **your computer**.  
- **Fork** → Copy someone else’s repo to **your GitHub account**.

**Basic Flow**  
Working Directory → `git add` → Staging Area → `git commit` → Local Repo → `git push` → Remote Repo (GitHub)

---

### **Module 5 & 6: Basic Git Commands & Workflow**

**Most Important Commands**

| Command                      | Purpose                              |
|------------------------------|--------------------------------------|
| `git init`                   | Create new local repository          |
| `git clone <url>`            | Copy remote repo to local            |
| `git status`                 | Show current state                   |
| `git add .`                  | Stage **all** changes                |
| `git add filename`           | Stage specific file                  |
| `git commit -m "message"`    | Save snapshot locally                |
| `git log --oneline`          | Short commit history                 |
| `git push origin main`       | Upload commits to GitHub             |
| `git push -u origin main`    | First push + set upstream            |
| `git remote add origin <url>`| Connect local repo to GitHub         |
| `git branch -M main`         | Rename branch to main                |

**Upload brand-new local project to GitHub (very important)**
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/repo.git
git branch -M main
git push -u origin main
```

**git status common messages**  
- Untracked files  
- Changes not staged for commit  
- Changes to be committed  
- Working tree clean

---

### **Module 7–11: Branching + Pull Request Workflow**

**What is a Branch?**  
Independent line of development.  
Analogy: `main` = main road (always stable), Feature branch = side road (safe to experiment).

**Why avoid working directly on `main`?**  
One mistake can break the entire project. Main should stay stable and production-ready.

**Commands**
```bash
git branch                  # list branches
git branch feature-name     # create branch
git switch feature-name     # switch to branch
# or
git checkout -b feature-name
```

**Simple Pull Request (PR) Workflow** (very important for exam)

1. Create feature branch  
2. Make changes → `git add` → `git commit`  
3. `git push origin feature-name`  
4. Open **Pull Request** on GitHub  
5. Review  
6. Merge PR  
7. Update local main → `git pull`  
8. Delete feature branch

**Local Merge vs Pull Request Merge**  
- Local merge = merge on your computer (`git merge`)  
- PR merge = merge on GitHub after review  
**PR is safer** for team projects because of review + discussion.

---

### **Module 12–13: Merge Conflicts**

**What is a Merge Conflict?**  
When two people change the **same lines** of the **same file** and Git cannot decide which change to keep.

**Basic steps to resolve**
1. Open the conflicted file  
2. Look for conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)  
3. Decide which code to keep (or combine both)  
4. Remove the markers  
5. `git add .`  
6. `git commit`  
7. Push the resolved code

---

### **Module 15–20: Extra Important Topics **

**`.gitignore`**  
File that tells Git which files/folders **not to track**.  
Common examples: `node_modules/`, `.env`, `*.log`, `__pycache__/`, `.DS_Store`

**git stash**  
Temporarily saves uncommitted work so you can switch branches safely.  
```bash
git stash
git stash list
git stash pop
```

**Git Tag**  
Marks a specific important commit (usually a release version like `v1.0.0`).  
```bash
git tag v1.0.0
git push origin v1.0.0
```

**git reset vs git revert**

| Command     | What it does                          | Safe on shared branches? |
|-------------|---------------------------------------|--------------------------|
| `git reset` | Moves branch pointer (can rewrite history) | **No** (use carefully)  |
| `git revert`| Creates a **new** commit that undoes changes | **Yes** (safer)         |

---

### **Quick One-Liners for MCQs & Short Answers**

- Major problem without VCS → Multiple confusing files (`final.doc`, `final2.doc`…)  
- Distributed VCS → Every developer has **complete copy + full history**  
- GitHub is a **cloud platform** that hosts Git repositories  
- Stage all files → `git add .`  
- Tag → Marks important commit (release)  
- Repository → Project + history  
- Staging Area → Intermediate area before commit  
- Clone = local copy | Fork = copy under your GitHub account  
- Branch = independent line of development  
- Purpose of `.gitignore` → Tell Git which files not to track  

---

**Exam Tip**  
Focus extra on:  
1. Types of VCS + comparison table  
2. Git vs GitHub + analogy  
3. Clone vs Fork table  
4. Basic workflow + commands  
5. Complete first-time push steps  
6. Simple PR workflow  
7. Merge conflict resolution steps  
8. `git stash`, Tag, reset vs revert  
