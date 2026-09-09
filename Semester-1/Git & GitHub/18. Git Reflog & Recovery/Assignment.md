# 📝 Assignment: Git Reflog & Recovery

## 🎯 Objective
Practice recovering lost commits and reworking old commits using `git reflog`, detached HEAD, and branching strategies.

***

## 📋 Part 1: Recovery After `git reset --hard` (5 Points)

### Task
1. Create a new repository called `reflog-practice-part1`
2. Create 3 commits:
   - **C0:** `README.md` with project title
   - **C1:** `index.html` with `<h1>Welcome</h1>`
   - **C2:** `style.css` with basic styling
3. Accidentally delete C1 and C2 using `git reset --hard <C0-commit-hash>`
4. Use `git reflog` to find the lost C2 commit
5. Recover C2 (and C1) using detached HEAD + branch + merge
6. Verify all commits are restored

### Deliverables
```
✅ Screenshot of: git log --oneline BEFORE reset
✅ Screenshot of: git log --oneline AFTER reset (showing lost commits)
✅ Screenshot of: git reflog output (highlighting the commit you recovered)
✅ Screenshot of: git log --oneline AFTER recovery (showing all commits restored)
✅ Push final repository to GitHub
```

### Expected Output
```bash
# Initial state
C0 ────── C1 ────── C2 (main)

# After reset --hard
C0 (main)    [C1 & C2 lost from log]

# After recovery
C0 ────── C1 ────── C2 (main)  ← All restored!
```

***

## 📋 Part 2: Reworking Old Commit (5 Points)

### Task
1. Create a new repository called `reflog-practice-part2`
2. Create 3 commits:
   - **C0:** `README.md` with just title
   - **C1:** `app.js` with basic function
   - **C2:** `utils.js` with helper functions
3. Realize you need to add description to README (C0) without losing C1 and C2
4. Create a branch at C0: `git switch -c rework/readme-update <C0-hash>`
5. Update README.md with description, commit
6. Merge the branch back to main
7. Verify C0, C1, and C2 are all preserved

### Deliverables
```
✅ Screenshot of: git log --oneline BEFORE creating branch
✅ Screenshot of: git branch output (showing both branches)
✅ Screenshot of: git log --oneline --graph (showing merge)
✅ Screenshot of: Final README.md content
✅ Push final repository to GitHub
```

### Expected Output
```bash
# Before rework
C0 ────── C1 ────── C2 (main)

# After rework + merge
      C3 (README update) ─┐
                          │
C0 ────── C1 ────── C2 ─── Merge (main)

All commits preserved!
```

***

## 📋 Part 3: Reflog Exploration 

### Task
1. In either repository, run `git reflog`
2. Document at least 5 different HEAD movements
3. For each movement, explain what command caused it

### Deliverables
```
✅ Screenshot of: git reflog output
✅ Written explanation (in README or written answer in notebook) for 5 HEAD movements:
   - HEAD@{0}: What happened?
   - HEAD@{1}: What happened?
   - HEAD@{2}: What happened?
   - HEAD@{3}: What happened?
   - HEAD@{4}: What happened?
```

### Example Format
```markdown
## Reflog Analysis

- **HEAD@{0}**: `git log` - Just viewing history (no movement)
- **HEAD@{1}**: `git checkout main` - Switched to main branch
- **HEAD@{2}**: `git merge rework/readme` - Merged rework branch
- **HEAD@{3}**: `git commit -m "Updated README"` - Made a commit
- **HEAD@{4}**: `git switch -c rework/readme abc1234` - Created branch at C0
```

***

## 📋 Part 4: Challenge - Multiple Recoveries (BONUS ASSIGNMENT)

### Task
1. Create a repository with 5 commits (C0 to C4)
2. Reset to C2 (losing C3 and C4)
3. Recover C4 using reflog
4. Make 2 more commits (C5, C6)
5. Reset to C3 (losing C4, C5, C6)
6. Recover all lost commits using reflog
7. Document your process

### Deliverables
```
✅ Screenshot of: git reflog showing multiple recoveries
✅ Screenshot of: Final git log --oneline --graph
✅ Brief write-up: What challenges did you face? How did you solve them?
```

***

## 📤 Submission Guidelines

- Push all repositories to your GitHub account
- Use your **CodingGita_Assignment** repository for all practical work and submission.
- Complete the assignments in order.
- For theoretical questions → write a short and correct answer in your notebook.
- Take clear photos of the written answers.
- Take screenshots of terminal / GitHub where asked.
- Push your practical work to the repository and submit the repository link along with the required photos and screenshots.

***

## ⏰ Deadline
**Submit by:** 13th September, 2026.

***

## 💡 Tips for Success

1. **Take screenshots at each step** - Don't wait until the end!
2. **Use meaningful branch names** - e.g., `recovery/restore-work`, `rework/readme-update`
3. **Write clear commit messages** - e.g., "Added index.html with welcome message"
4. **Verify after each step** - Use `git log --oneline` and `git branch`
5. **Don't panic if you make mistakes** - That's what reflog is for!
6. **Ask for help** - If stuck, reach out before the deadline

***

## 🔗 Resources

- [Git Reflog Documentation](https://git-scm.com/docs/git-reflog)
- [Git Tools - Revision Selection](https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection)
- [Class Notes: Day 18](https://github.com/codinggita/CGXSwarrnim/blob/main/Semester-1/Git%20%26%20GitHub/18.%20Git%20Reflog%20%26%20Recovery/Notes.md)

***

## ❓ FAQ

**Q: What if I accidentally delete my repository?**  
A: Start over! The practice is what matters. You can also clone from GitHub if you pushed.

**Q: Can I work in groups?**  
A: Individual work only. You can discuss concepts, but each person must submit their own work.

**Q: My reflog is empty. What happened?**  
A: Reflog might be disabled or the repo is too new. Run a few commands (commit, checkout, etc.) and try again.

**Q: Can I use `git checkout -b` instead of `git switch -c`?**  
A: Yes! Both work. `git switch -c` is newer and clearer, but `git checkout -b` is fine.

**Q: What if I can't recover my commits?**  
A: Check your reflog carefully. The commit hash should be there. If still stuck, ask for help!

***

## 🎯 Learning Outcomes

After completing this assignment, you will be able to:
- ✅ Use `git reflog` to find lost commits
- ✅ Recover from `git reset --hard` mistakes
- ✅ Work in detached HEAD state safely
- ✅ Create branches from specific commits
- ✅ Merge recovered work back to main
- ✅ Modify old commits without losing new work
- ✅ Understand Git's safety mechanisms

***

**Good luck! Remember: Git reflog is your time machine. Use it wisely! 🚀**
