
#  Git Tags, Semantic Versioning & Releases

---

## 1. What is a Tag in Git?

A **Tag** is a fixed pointer that always points to one specific commit.

Once you create a tag on a commit, that tag will **never move**, even if you add 100 more commits later.

### Real-life Example:
Imagine you take a photo of your project on 10th September and write “Version 1.0” on it.  
No matter how much the project changes later, that photo will always show the project as it was on 10th September.

That photo is a **Tag**.

---

## 2. Branch vs Tag (Clear Difference)

| Point                    | Branch                              | Tag                                  |
|--------------------------|-------------------------------------|--------------------------------------|
| Nature                   | Moving pointer                      | Fixed pointer                        |
| Changes with new commits?| Yes (moves forward)                 | No (stays on the same commit)        |
| Purpose                  | Development & parallel work         | Marking important points in history  |
| Can you commit on it?    | Yes                                 | Not recommended (creates Detached HEAD) |
| Example                  | `main`, `feature/login`             | `v1.0.0`, `v2.1.3`                   |
| Used for                 | Daily development                   | Releases, milestones, versions       |

---

### Visual Diagram: Branch vs Tag

```
Commit History:

A ────── B ────── C ────── D ────── E ────── F
         │                 │
         │                 └─── v1.1.0     ← Tag (Fixed)
         │
         └─── v1.0.0                       ← Tag (Fixed)

         main ─────────────────────────────→ (keeps moving to new commits)
```

**Explanation:**
- `main` branch moves to newer commits (E → F).
- Tags `v1.0.0` and `v1.1.0` remain permanently on the commits where they were created.

---

## 3. Types of Tags

There are **two types** of tags in Git:

### 1. Lightweight Tag
- Just a simple name pointing to a commit
- Does **not** store any extra information
- Mostly used for personal/temporary marking

### 2. Annotated Tag
- Stores extra information:
  - Tag message
  - Author name
  - Date and time
- Recommended for all professional work

---

### Difference between Lightweight and Annotated Tags

| Feature                  | Lightweight Tag                  | Annotated Tag                              |
|--------------------------|----------------------------------|--------------------------------------------|
| Command                  | `git tag v1.0`                   | `git tag -a v1.0.0 -m "message"`           |
| Stores message?          | No                               | Yes                                        |
| Stores author & date?    | No                               | Yes                                        |
| Shown in `git show`      | Only commit details              | Tag message + commit details               |
| Recommended for releases?| No                               | **Yes**                                    |
| Use case                 | Personal temporary marks         | Official versions & releases               |

> **Golden Rule:**  
> In real projects and team work, **always use Annotated Tags**.

---

## 4. Git Tag Commands with Simple Examples

Assume this is your current commit history:

```
e4f5g6h (HEAD -> main) Added payment feature
c1d2e3f                Added home page
a1b2c3d                Added authentication
```

---

### 4.1 Create a Lightweight Tag

```bash
git tag v1.0
```

**Example:**
```bash
git tag trial-version
```

---

### 4.2 Create an Annotated Tag (Recommended)

```bash
git tag -a v1.0.0 -m "First stable release"
```

**Example:**
```bash
git tag -a v1.0.0 -m "Added authentication, home page and payment gateway"
```

---

### 4.3 Create Tag on an Older Commit

First find the commit hash:

```bash
git log --oneline
```

Then create tag:

```bash
git tag -a v0.9.0 a1b2c3d -m "Beta version before payment"
```

---

### 4.4 List All Tags

```bash
git tag
```

**Filter tags:**
```bash
git tag -l "v1.*"
```

---

### 4.5 See Details of a Tag

```bash
git show v1.0.0
```

This will show:
- Tag message
- Author
- Date
- The commit it points to

---

### 4.6 Push Tags to GitHub

Normal `git push` does **not** push tags.

**Push one tag:**
```bash
git push origin v1.0.0
```

**Push all tags:**
```bash
git push origin --tags
```

---

### 4.7 Delete a Tag

**Delete locally:**
```bash
git tag -d v1.0.0
```

**Delete from GitHub:**
```bash
git push origin --delete v1.0.0
```

---

### 4.8 Go to a Tag (Checkout)

```bash
git switch --detach v1.0.0
```

> Note: This puts you in **Detached HEAD** state.

**Correct way to work on old version:**
```bash
git switch -c hotfix-branch v1.0.0
```

This creates a new branch starting from that tag.

---

## 5. Semantic Versioning (How to Name Tags)

Most companies follow this standard:

```
vMAJOR.MINOR.PATCH
```

| Version     | Meaning                          | When to use                              |
|-------------|----------------------------------|------------------------------------------|
| `v1.0.0`    | First stable version             | Project is ready for users               |
| `v1.1.0`    | New feature added                | Added Dark Mode (no breaking change)     |
| `v1.1.1`    | Only bug fix                     | Fixed login bug                          |
| `v2.0.0`    | Breaking changes                 | Changed API completely                   |

---

## 6. Common Mistakes Students Make

| Mistake                              | What goes wrong                      | Correct Way                              |
|--------------------------------------|--------------------------------------|------------------------------------------|
| Using Lightweight tag for release    | No message or author stored          | Always use Annotated tag                 |
| Forgetting to push the tag           | Tag only exists on your laptop       | Run `git push origin v1.0.0`            |
| Making commits directly on a tag     | Goes into Detached HEAD              | Create a new branch from the tag         |
| Tagging wrong commit                 | Wrong code gets marked               | Delete and create tag again              |

---

## 7. Best Practices

1. Always use **Annotated Tags** in real projects.
2. Follow **Semantic Versioning** (`v1.0.0`, `v1.1.0`, etc.).
3. Create the tag **after merging** the feature into `main`.
4. Push tags separately using `git push origin <tag-name>`.
5. Create a **GitHub Release** from important tags.

---

## 8. Quick Command Cheat Sheet

```bash
# Create annotated tag
git tag -a v1.0.0 -m "First stable release"

# List tags
git tag

# Show tag info
git show v1.0.0

# Push tag
git push origin v1.0.0

# Delete local tag
git tag -d v1.0.0

# Delete remote tag
git push origin --delete v1.0.0

# Create branch from tag
git switch -c hotfix v1.0.0

# Beautiful view of branches + tags
git log --oneline --decorate --graph --all
```

---

## 9. Practice Questions

1. What is the main difference between a Branch and a Tag?
2. Which type of tag should you use when working in a team?
3. Write the command to create an annotated tag `v2.1.0` with message “Added search feature”.
4. How do you push a tag to GitHub?
5. What happens if you run `git switch v1.0.0`?

---
