#  Git Stash : Save Your Work Without Committing

***

## 🎯 Learning Goals

By the end of this session, you will be able to:

- Define `git stash` and explain why we use it.  
- Use core stash commands confidently in real workflows.  
- Handle untracked and ignored files with `-u` and `-a`.  
- Use meaningful stash messages for better hygiene.  
- Visualize how the stash stack changes with `apply`, `pop`, and `drop`.

***

## 🧠 1. What Is `git stash`? (Definition + Big Idea)

**Definition:**  
`git stash` is a Git command that **temporarily saves your uncommitted changes** (tracked, and optionally untracked/ignored) into a hidden storage area called the **stash stack**, so you can switch branches or pull updates with a clean working tree, and later reapply those changes.

**In short:**

- Acts like a **temporary storage** or **hidden commit**.  
- Stores:
  - Staged changes  
  - Unstaged changes in tracked files  
  - (Optionally) untracked and ignored files  
- Organized as a **stack**: `stash@{0}` (latest), `stash@{1}`, `stash@{2}`, …

**When to use:**

- You’re mid-work on a feature and need to:
  - Switch branches urgently.
  - Pull latest changes.
  - Test something else without committing incomplete work.

***

## 🧪 2. Why Stash? (Live Demo on `main`)

### Scenario setup (what you already did in class)

1. Created a GitHub repo: `git-stash`.
2. Cloned it locally → initial commit `c0` with `README.md`.
3. On `main`:
   - Created `index.html`:
     ```html
     <h1>Hi all, Good morning</h1>
     ```
     → **untracked file**.
   - Modified `README.md`:
     > "This repo created for learning purpose of Git Stash."
     → **modified tracked file**.

Current state before stashing:

```bash
git status
```

You see:

- `README.md` – modified (tracked)
- `index.html` – untracked

***

### Step 1: First stash (tracked changes only)

```bash
git stash
# or
git stash push
```

**What happens?**

- Git saves changes in `README.md` into `stash@{0}`.
- Working directory reverts `README.md` to last committed version.
- `index.html` remains **untracked** (still visible).

```bash
git status
git stash list
```

You see:

- Clean working tree for tracked files.
- One stash entry:
  ```text
  stash@{0}: WIP on main: <auto message>
  ```

**Visual:**

```text
Before:
Working Dir: [README.md (modified), index.html (untracked)]
Stash Stack: []

After `git stash`:
Working Dir: [index.html (untracked)]
Stash Stack: [stash@{0} → README.md changes]
```

***

### Step 2: Second stash (include untracked file)

Now you want to stash `index.html` too.

```bash
git stash -u
# or
git stash --include-untracked
```

**What happens?**

- Git creates a **new** stash `stash@{0}` containing:
  - Previously stashed `README.md` changes (from working tree state at that time).
  - Plus `index.html` (untracked).
- Now both files “disappear” from your working directory.

```bash
git status
git stash list
```

Now you have:

```text
stash@{0}: WIP on main: <auto message>   ← includes index.html + README
stash@{1}: WIP on main: <auto message>   ← only README changes
```

**Key point to explain:**

- `stash@{0}` = latest stash
- `stash@{1}` = previous stash

**Visual:**

```text
After `git stash -u`:
Working Dir: []  (clean)
Stash Stack:
  stash@{0} → README + index.html
  stash@{1} → README only
```

***

## 📋 3. Inspecting Stashes: `git stash list` & `git stash show`

### `git stash list`

```bash
git stash list
```

Shows:

```text
stash@{0}: WIP on main: ...
stash@{1}: WIP on main: ...
```

Explain:

- Indexing: `0` is latest, `1` is before that, etc.

***

### `git stash show`

```bash
# Show latest stash (stash@{0})
git stash show

# Show a specific stash
git stash show stash@{0}
git stash show stash@{1}
```

Output (example):

```text
stash@{0}:
 README.md  | 2 ++
 index.html | 1 +

stash@{1}:
 README.md  | 2 ++
```

**Question:**  
Which stash contains `index.html`? How can you tell from `git stash show`?

***

## ♻️ 4. Bringing Changes Back: `apply` vs `pop`

### `git stash apply` — “Reapply, keep stash”

```bash
# Apply latest stash
git stash apply

# Apply a specific stash
git stash apply stash@{0}
git stash apply stash@{1}
```

**Behavior:**

- Reapplies the changes to your working directory.
- **Does NOT delete** the stash from the list.

Use when:

- You want to test changes but keep the stash as backup.
- You want to apply the same stash to multiple branches.

**After `git stash apply stash@{1}`:**

```bash
git status
git stash list
```

You’ll see:

- Files from `stash@{1}` are back in working directory.
- `stash@{0}` and `stash@{1}` still exist.

***

### `git stash pop` — “Reapply, remove stash”

```bash
# Pop latest stash
git stash pop

# Pop a specific stash
git stash pop stash@{0}
```

**Behavior:**

- Reapplies the stash.
- **Deletes** that stash from the list (if successful).

**Important visual: stack re-indexing**

Suppose you have:

```text
Before pop:
stash@{0} → README + index.html
stash@{1} → README only
```

Run:

```bash
git stash pop stash@{0}
```

Now:

```text
After pop:
stash@{0} → README only   (previously stash@{1})
```

Explanation:

- `stash@{0}` is removed.
- `stash@{1}` shifts up and becomes the new `stash@{0}`.

**Student exercise:**

1. Run `git stash list`.
2. Run `git stash pop stash@{0}`.
3. Run `git stash list` again.
4. Ask: What happened to the indices?

***

## 🗑️ 5. Removing Stashes: `drop` and `clear`

### `git stash drop`

```bash
# Drop latest
git stash drop

# Drop specific
git stash drop stash@{1}
```

Use when:

- A particular stash is no longer needed.

### `git stash clear`

```bash
git stash clear
```

⚠️ Deletes **all** stashes permanently.

**Visual lifecycle:**

```text
[Uncommitted Changes]
        |
        | git stash / git stash push [-u] [-a] [-m "msg"]
        v
   [Stash Stack]
        |
        | git stash list
        v
   [View Stash List]
        |
        +---> git stash show [stash@{n}]       → preview
        |
        +---> git stash apply [stash@{n}]      → reapply, keep
        |
        +---> git stash pop [stash@{n}]        → reapply, remove
        |
        +---> git stash drop [stash@{n}]       → delete one
        |
        +---> git stash clear                  → delete all
```

***

## 🌿 6. Real-Life Scenario: Working on `feature/login` and `feature/sign-up`

### Setup: `feature/login` branch

You are on `feature/login`:

- Created:
  - `login.html` → already committed.
  - `login.css` → added to staging area.
  - `login.js` → only in working directory (untracked or modified).

Example:

```bash
git switch -c feature/login

# login.html already committed

# login.css staged
git add login.css

# login.js untracked / modified
echo "// WIP: validation logic" > login.js
```

Now an urgent requirement comes:

> “We must implement Sign-up first. Without registration, login is useless.”

You need to:

- Save your half-done login work.
- Switch to a new branch `feature/sign-up`.

***

### Stashing half-done login work

Check status:

```bash
git status
```

You see:

- `login.css` – staged
- `login.js` – untracked/modified

Stash staged + working directory tracked changes:

```bash
git stash
# or
git stash push
```

This saves:

- `login.css` (staged)
- Any tracked modifications in working directory

But `login.js` (if untracked) is still there.

Now stash untracked too:

```bash
git stash -u
```

Now your working directory is clean.

```bash
git stash list
```

You might have:

```text
stash@{0}: WIP on feature/login: ...   ← includes login.js
stash@{1}: WIP on feature/login: ...   ← login.css + other tracked changes
```

**Visual:**

```text
Before stash:
Working Dir: [login.css (staged), login.js (untracked)]
Stash Stack: []

After `git stash` + `git stash -u`:
Working Dir: []
Stash Stack:
  stash@{0} → login.css + login.js
  stash@{1} → earlier login changes
```

***

### Switch to `main`, update, then create `feature/sign-up`

```bash
git switch main
git pull

git switch -c feature/sign-up
```

Now create sign-up files:

- `sign-up.html`
- `sign-up.css`
- `sign-up.js`

Do some work and stage them:

```bash
git add sign-up.html sign-up.css sign-up.js
```

Now you think:

> “Let’s check if login + sign-up work together.”

You want to temporarily bring back your login work.

***

### Applying previous login stashes on `feature/sign-up`

Check stashes:

```bash
git stash list
```

Apply one or both:

```bash
git stash apply stash@{0}
git stash apply stash@{1}
```

Now you have:

- Sign-up files (staged/committed as per your work).
- Login files back in working directory for testing.

**Why `apply` here?**

- You may want to:
  - Test multiple times.
  - Keep the stash for later use on another branch.

After testing, you decide:

- Login files are not needed right now.
- You want to focus only on sign-up.

Remove login files:

```bash
rm login.html login.css login.js
git rm login.html login.css login.js   # if tracked
```

Your sign-up work remains.

***

## 🧼 7. Better Stash Hygiene: Meaningful Messages

Problem:

- Default stash messages are vague:
  ```text
  stash@{0}: WIP on feature/sign-up: ...
  stash@{1}: WIP on feature/login: ...
  ```
- Hard to know which stash is which.

Solution:

- Use custom messages:

```bash
git stash push -m "WIP: login CSS + JS (staging + working)"
git stash push -m "WIP: sign-up HTML structure"
```

Now:

```bash
git stash list
```

Example:

```text
stash@{0}: On feature/sign-up: WIP: sign-up HTML structure
stash@{1}: On feature/login: WIP: login CSS + JS (staging + working)
```

**Best practices for messages:**

- Start with a tag:
  - `WIP:` work in progress
  - `BUGFIX:` quick fix
  - `EXPERIMENT:` experimental change
- Mention feature/file:
  - `WIP: login form validation`
  - `WIP: sign-up HTML structure`

**Student exercise:**

1. Create two different sets of changes.
2. Stash each with a clear message:
   ```bash
   git stash push -m "WIP: feature A"
   git stash push -m "WIP: feature B"
   ```
3. Run `git stash list` and discuss which messages are clearer and why.

***

## 🧳 8. Untracked & Ignored Files: `-u` vs `-a` (with `.env` example)

### Scenario: `feature/payment` branch with secrets

You switch:

```bash
git switch main
git pull
git switch -c feature/payment
```

You create:

- `.env` with secrets:
  ```bash
  PASSWORD=supersecret
  JWT_SECRET_KEY=abc123
  MONGO_URI=mongodb://...
  ```
- Dummy `node_modules/` folder.
- Add both to `.gitignore`:
  ```bash
  echo ".env" >> .gitignore
  echo "node_modules/" >> .gitignore
  ```

Now these files are **ignored**.

You’ve also made some tracked changes in payment-related files.

You want to stash **everything**: tracked + untracked + ignored.

***

### Using `-u` and `-a` together

```bash
git stash -u -a -m "WIP: payment + secrets (.env, node_modules)"
```

Explanation:

- `-u` / `--include-untracked`:
  - Includes new files not yet tracked.
- `-a` / `--all`:
  - Also includes ignored files (`.env`, `node_modules/`).
- `-m`:
  - Adds a meaningful message.

Now:

```bash
git stash list
```

You see:

```text
stash@{0}: On feature/payment: WIP: payment + secrets (.env, node_modules)
...
```

Working directory is clean.

**Visual:**

```text
Files:
- payment.js       (tracked, modified)
- config.js        (untracked)
- .env             (ignored)
- node_modules/    (ignored)

git stash          → payment.js only
git stash -u       → payment.js + config.js
git stash -u -a    → payment.js + config.js + .env + node_modules/
```

⚠️ Warn students:

- Don’t routinely use `-a` if you have large ignored directories (e.g., build artifacts).
- Use it only when you truly need to stash ignored files.

***

## 🖼️ 9. Visual Summary: Stash Stack & Core Commands

### Stash stack as a vertical stack

```text
Top (newest)
┌─────────────────────────────────────────────┐
│ stash@{0}                                   │
│ "WIP: payment + secrets (.env, node_modules)"│
├─────────────────────────────────────────────┤
│ stash@{1}                                   │
│ "WIP: sign-up HTML structure"               │
├─────────────────────────────────────────────┤
│ stash@{2}                                   │
│ "WIP: login CSS + JS (staging + working)"   │
└─────────────────────────────────────────────┘
Bottom (oldest)

Operations:
- git stash list      → show all
- git stash show      → inspect top
- git stash apply     → reapply top, keep
- git stash pop       → reapply top, remove
- git stash drop      → delete one
- git stash clear     → delete all
```

### Flow diagram of a typical workflow

```text
[Uncommitted Changes]
(tracked + untracked + ignored)
        |
        | git stash [push] [-u] [-a] [-m "msg"]
        v
   [Stash Stack]
        |
        | git stash list
        v
   [View Stash List]
        |
        +---> git stash show [stash@{n}] [-p]
        |        (preview changes)
        |
        +---> git stash apply [stash@{n}]
        |        (restore changes, keep stash)
        |
        +---> git stash pop [stash@{n}]
        |        (restore changes, remove stash,
        |         re-index remaining stashes)
        |
        +---> git stash drop [stash@{n}]
        |        (delete specific stash)
        |
        +---> git stash clear
                 (delete all stashes)
```

***

## 🧩 10. Mini Lab for Students (Hands-on)

**Goal:** Practice the full workflow with branches and hygiene.

1. On `main`:
   - Modify a tracked file.
   - Create an untracked file.
   - Stash with a message:
     ```bash
     git stash push -m "WIP: main changes"
     ```
2. Create `feature/login`:
   - Add `login.html`, `login.css`, `login.js`.
   - Stage some, leave some untracked.
   - Stash with:
     ```bash
     git stash -u -m "WIP: login CSS + JS"
     ```
3. Switch to `main`, pull, then create `feature/sign-up`:
   - Create sign-up files, do some work.
   - Apply login stashes:
     ```bash
     git stash apply stash@{0}
     git stash apply stash@{1}
     ```
   - Test, then remove login files.
4. Create `feature/payment`:
   - Add `.env`, `node_modules/`, ignore them.
   - Stash everything:
     ```bash
     git stash -u -a -m "WIP: payment + secrets"
     ```
5. At each step, run:
   - `git status`
   - `git stash list`
   - `git stash show` / `git stash show -p`

***

## 📝 11. Quick Command Cheat Sheet

**Core commands:**

```bash
git stash
git stash push
git stash list
git stash show
git stash show -p
git stash apply
git stash apply stash@{n}
git stash pop
git stash pop stash@{n}
git stash drop
git stash drop stash@{n}
git stash clear
```

**With options:**

```bash
git stash -u
git stash --include-untracked
git stash -a
git stash --all
git stash push -m "meaningful message"
git stash -u -a -m "WIP: feature + ignored files"
```

**Inspect specific stashes:**

```bash
git stash show stash@{0}
git stash show stash@{1} -p
```

***
