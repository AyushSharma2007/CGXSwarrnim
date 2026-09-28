# GitHub Team Collaboration — Hackathon Management System

## 1. Project Scenario

Imagine we are developing a **Hackathon Management System** as a team.

Our team has **4 developers**, and each developer is responsible for one feature.

### Project

```text
Hackathon Management System
```

### Team

| Team Member | Task           |
| ----------- | -------------- |
| Teammate 1  | Sign-up Page   |
| Teammate 2  | Login Page     |
| Teammate 3  | Home Page      |
| Teammate 4  | Dashboard Page |

The project is stored in a GitHub repository:

```text
hackathon-management-system
```

---

# 2. Create the GitHub Repository

Create a new repository on GitHub:

```text
hackathon-management-system
```

The repository will contain the complete project.

Example:

```text
hackathon-management-system/
│
├── index.html
├── signup.html
├── login.html
├── dashboard.html
├── css/
└── js/
```

The `main` branch contains the shared/stable version of the project.

---

# 3. Add Team Members

The repository owner adds the other 4 developers as collaborators.

GitHub:

```text
Repository
   ↓
Settings
   ↓
Collaborators
   ↓
Add people
```

After accepting the invitation, all team members can work on the repository according to the repository permissions.

### Team structure

```text
                Hackathon Management System
                          │
              ┌───────────┼───────────┐
              │           │           │
          Teammate 1  Teammate 2  Teammate 3  Teammate 4
              │           │           │           │
           Sign-up      Login       Home      Dashboard
```

---

# 4. Create GitHub Issues

Before developers start coding, we create **Issues** for the work that needs to be completed.

An Issue represents a **task or feature that needs to be developed**.

We create 4 issues.

---

## Issue #1 — Sign-up Page

### Title

```text
Create Sign-up Page
```

### Description

```text
Create a sign-up page for new participants.

The page should contain:
- Name
- Email
- Password
- Confirm Password
- Sign-up button
```

Assign this issue to:

```text
Teammate 1
```

---

## Issue #2 — Login Page

### Title

```text
Create Login Page
```

### Description

```text
Create a login page for participants.

The page should contain:
- Email
- Password
- Login button
- Link to Sign-up page
```

Assign this issue to:

```text
Teammate 2
```

---

## Issue #3 — Home Page

### Title

```text
Create Home Page
```

### Description

```text
Create the home page of the Hackathon Management System.

The page should contain:
- Project title
- Short introduction
- Navigation links
- Login and Sign-up options
```

Assign this issue to:

```text
Teammate 3
```

---

## Issue #4 — Dashboard Page

### Title

```text
Create Participants Dashboard
```

### Description

```text
Create a dashboard page that displays information about all participants.

The dashboard should contain:
- Participant name
- Email
- College
- Team information
```

Assign this issue to:

```text
Teammate 4
```

---

# 5. Our GitHub Issues

After creating the issues, the project may look like this:

```text
#1  Create Sign-up Page
    Assigned to Teammate 1

#2  Create Login Page
    Assigned to Teammate 2

#3  Create Home Page
    Assigned to Teammate 3

#4  Create Participants Dashboard
    Assigned to Teammate 4
```

This gives every developer a **clear task**.

---

# 6. Why Do We Use Issues?

An Issue helps the team answer:

> **What work needs to be done?**

For example:

```text
Issue #1
    ↓
Create Sign-up Page
    ↓
Teammate 1
```

So everyone knows:

* What needs to be developed
* Who is responsible
* What the feature should contain

---

# 7. Create a Branch for Each Issue

Each developer creates a separate branch for their task.

### Teammate 1

```bash
git switch -c feature/signup
```

### Teammate 2

```bash
git switch -c feature/login
```

### Teammate 3

```bash
git switch -c feature/home
```

### Teammate 4

```bash
git switch -c feature/dashboard
```

Our branches:

```text
main
│
├── feature/signup
├── feature/login
├── feature/home
└── feature/dashboard
```

### Why separate branches?

Because developers can work on their features **without directly changing the `main` branch**.

---

# 8. Developer Workflow

Every developer follows the same basic workflow:

```text
GitHub Issue
     ↓
Create Branch
     ↓
Write Code
     ↓
Commit
     ↓
Push
     ↓
Create Pull Request
     ↓
Code Review
     ↓
Fix Changes
     ↓
Merge
```

---

# 9. Example — Teammate 1

Teammate 1 is responsible for:

```text
Issue #1
Create Sign-up Page
```

### Step 1: Get the project

```bash
git clone <repository-url>
```

### Step 2: Move into project

```bash
cd hackathon-management-system
```

### Step 3: Create branch

```bash
git switch -c feature/signup
```

### Step 4: Create the page

Create:

```text
signup.html
```

Add the required fields.

### Step 5: Check changes

```bash
git status
```

### Step 6: Stage changes

```bash
git add .
```

### Step 7: Commit

```bash
git commit -m "Add sign-up page"
```

### Step 8: Push

```bash
git push -u origin feature/signup
```

---

# 10. Create Pull Request

After pushing the branch, Teammate 1 creates a Pull Request:

```text
feature/signup
       ↓
      main
```

### PR Title

```text
Add sign-up page
```

### PR Description

```text
Added the sign-up page with:
- Name
- Email
- Password
- Confirm Password
- Sign-up button

Closes #1
```

`Closes #1` connects the Pull Request with Issue #1.

When the PR is merged, GitHub can automatically close the linked issue.

---

# 11. Code Review

Another teammate reviews the Pull Request.

They check:

* Is the feature working?
* Is the code readable?
* Does it satisfy the issue?
* Are there any obvious problems?

The reviewer can leave comments.

Example:

```text
Please add a link to the Login page.
```

---

# 12. Make Changes After Review

Teammate 1 fixes the requested change.

```bash
git add .
git commit -m "Add login link to sign-up page"
git push
```

The **same Pull Request gets updated automatically**.

There is no need to create another Pull Request.

---

# 13. Approve and Merge

After the changes are reviewed:

```text
Pull Request
     ↓
Review
     ↓
Approved
     ↓
Merge
     ↓
main
```

Now the Sign-up Page becomes part of the main project.

---

# 14. Other Team Members Follow the Same Workflow

## Teammate 2 — Login Page

```text
Issue #2
   ↓
feature/login
   ↓
login.html
   ↓
Commit
   ↓
Push
   ↓
Pull Request
   ↓
Review
   ↓
Merge
```

Command example:

```bash
git switch -c feature/login

git add .
git commit -m "Add login page"

git push -u origin feature/login
```

---

## Teammate 3 — Home Page

```text
Issue #3
   ↓
feature/home
   ↓
index.html
   ↓
Commit
   ↓
Push
   ↓
Pull Request
   ↓
Review
   ↓
Merge
```

Command example:

```bash
git switch -c feature/home

git add .
git commit -m "Add home page"

git push -u origin feature/home
```

---

## Teammate 4 — Dashboard Page

```text
Issue #4
   ↓
feature/dashboard
   ↓
dashboard.html
   ↓
Commit
   ↓
Push
   ↓
Pull Request
   ↓
Review
   ↓
Merge
```

Command example:

```bash
git switch -c feature/dashboard

git add .
git commit -m "Add participants dashboard"

git push -u origin feature/dashboard
```

---

# 15. How the Team Works in Parallel

All four developers can work at the same time:

```text
                         main
                          │
          ┌───────────────┼───────────────┐
          │               │               │
          ↓               ↓               ↓
   feature/signup   feature/login   feature/home
          │               │               │
          ↓               ↓               ↓
        PR              PR              PR
          │               │               │
          └───────────────┼───────────────┘
                          ↓
                         main
```

And:

```text
feature/dashboard
       ↓
      PR
       ↓
     main
```

Each developer works on their own feature and later integrates it into `main`.

---

# 16. What Happens When a PR Is Merged?

Suppose the Sign-up PR is merged.

GitHub:

```text
feature/signup
      ↓
     Merge
      ↓
     main
```

Other developers should update their local `main` before starting new work:

```bash
git switch main
git pull origin main
```

Then they can create or update their feature branches based on the latest project version.

---

# 17. What If Two Developers Change the Same Code?

Sometimes two developers modify the same part of a file.

For example:

### Teammate 1

```html
<h1>Hackathon Management System</h1>
```

### Teammate 3

```html
<h1>Hackathon 2026</h1>
```

Git may not know which change should be kept.

This can create a **merge conflict**.

```text
<<<<<<< HEAD
<h1>Hackathon Management System</h1>
=======
<h1>Hackathon 2026</h1>
>>>>>>> feature/home
```

The developers must decide what the correct final code should be.

Then:

```bash
git add .
git commit
```

or, depending on where the conflict occurs, use the appropriate continuation command.

---

# 18. Complete Team Workflow

The complete workflow for our Hackathon Management System is:

```text
              Hackathon Management System
                         │
                         ↓
                  Create GitHub Repo
                         │
                         ↓
                  Add Team Members
                         │
                         ↓
                  Create GitHub Issues
                         │
       ┌─────────────────┼─────────────────┐
       ↓                 ↓                 ↓
   Issue #1          Issue #2          Issue #3
   Sign-up             Login             Home
       ↓                 ↓                 ↓
    Branch             Branch            Branch
       ↓                 ↓                 ↓
     Code              Code              Code
       ↓                 ↓                 ↓
    Commit            Commit            Commit
       ↓                 ↓                 ↓
     Push              Push              Push
       ↓                 ↓                 ↓
      PR                PR                PR
       ↓                 ↓                 ↓
    Review            Review            Review
       ↓                 ↓                 ↓
     Merge             Merge             Merge
       └─────────────────┼─────────────────┘
                         ↓
                        main
                         ↑
                    Dashboard PR
```

---

# 19. Important GitHub Concepts

| Concept      | Simple Meaning                           |
| ------------ | ---------------------------------------- |
| Repository   | Complete project                         |
| Team Member  | Developer working on the project         |
| Issue        | Task that needs to be completed          |
| Branch       | Separate workspace for a feature         |
| Commit       | Saved change                             |
| Push         | Send local changes to GitHub             |
| Pull Request | Request to merge changes                 |
| Review       | Check another developer's code           |
| Merge        | Add approved changes to another branch   |
| Conflict     | Git cannot automatically combine changes |

---

# 20. Golden Rule for Team Projects

When working in a team:

```text
Don't directly develop on main
              ↓
Create a feature branch
              ↓
Do your work
              ↓
Commit
              ↓
Push
              ↓
Create Pull Request
              ↓
Get review
              ↓
Merge
```

### Remember

> **Issue → Branch → Code → Commit → Push → Pull Request → Review → Merge**

# 21. Hackathon Team Checklist

Before starting your hackathon project, make sure your team knows:

* [ ] Create one GitHub repository
* [ ] Add all teammates
* [ ] Create Issues for features
* [ ] Assign Issues to teammates
* [ ] Create a separate branch for each feature
* [ ] Use meaningful commit messages
* [ ] Push feature branches to GitHub
* [ ] Create Pull Requests
* [ ] Review teammates' code
* [ ] Fix requested changes
* [ ] Merge approved Pull Requests
* [ ] Update local `main`
* [ ] Resolve conflicts when necessary

**Main idea:**

> Git helps developers manage their code.
> GitHub helps the team collaborate on that code.
