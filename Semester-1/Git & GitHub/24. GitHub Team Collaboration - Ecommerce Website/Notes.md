# E-commerce Website — GitHub Team Collaboration Workflow

----

## 1. Project Scenario

Imagine we are developing an **E-commerce Website** as a team.

Our team has **4 developers**, and each developer is responsible for one page/feature.

### Project

```text
E-commerce Website
```

### Team

```
| Team Member | Task              |
| ----------- | ----------------- |
| Teammate 1  | Product Page      |
| Teammate 2  | Cart Page         |
| Teammate 3  | Checkout Page     |
| Teammate 4  | User Profile Page |
```

The project is stored in a GitHub repository:

```text
ecommerce-website
```

---

# 2. Create the GitHub Repository

Create a new repository on GitHub:

```text
ecommerce-website
```

The repository will contain the complete project.

Example structure:

```text
ecommerce-website/
│
├── index.html
├── product.html
├── cart.html
├── checkout.html
├── profile.html
├── css/
└── js/
```

The `main` branch contains the shared/stable version of the project.

---

# 3. Add Team Members

The repository owner adds the other developers as collaborators.

GitHub path:

```text
Repository → Settings → Collaborators → Add people
```

After accepting the invitation, all team members can work on the repository according to the granted permissions.

### Team structure

```text
E-commerce Website
│
┌───────────┼───────────┐
│           │           │
Teammate 1  Teammate 2  Teammate 3  Teammate 4
│           │           │           │
Product     Cart        Checkout    User Profile
```

---

# 4. GitHub Project Management Concepts (Short Descriptions)

Before creating issues, understand these three key features:

| Concept     | Simple Meaning |
|-------------|----------------|
| **Issue**   | A single task or feature that needs to be completed (e.g., “Create Product Page”). It tracks what work is required, who is responsible, and the status of that work. |
| **Milestone** | A group of related issues that together represent a larger goal or deadline (e.g., “Project MVP”). It helps organize work into phases and track overall progress toward a release. |
| **Project (Kanban Board)** | A visual board that organizes issues into columns (Todo → In Progress → Done). It gives the whole team a real-time overview of what is planned, being worked on, and finished. |

---

# 5. Create Milestones

We create **two milestones**:

### Milestone 1 — Project MVP

```text
Title: Project MVP
Description: Deliver the core shopping experience (Product, Cart, and Checkout pages).
Due date: (set a realistic date)
```

### Milestone 2 — Final Project

```text
Title: Final Project
Description: Complete the remaining features (User Profile page) and polish the application.
Due date: (set a later date)
```

---

# 6. Create GitHub Issues

We create **4 issues** and link them to the appropriate milestones.

---

## Issue #1 — Product Page

**Title**

```text
Create Product Page
```

**Description**

```text
Create a product listing/detail page.

The page should contain:
- Product name
- Product image
- Price
- Description
- Add to Cart button
```

**Milestone:** Project MVP  
**Assign to:** Teammate 1

---

## Issue #2 — Cart Page

**Title**

```text
Create Cart Page
```

**Description**

```text
Create a shopping cart page.

The page should contain:
- List of added products
- Quantity controls
- Subtotal / total price
- Proceed to Checkout button
```

**Milestone:** Project MVP  
**Assign to:** Teammate 2

---

## Issue #3 — Checkout Page

**Title**

```text
Create Checkout Page
```

**Description**

```text
Create a checkout page for completing the purchase.

The page should contain:
- Shipping address form
- Payment method selection
- Order summary
- Place Order button
```

**Milestone:** Project MVP  
**Assign to:** Teammate 3

---

## Issue #4 — User Profile Page

**Title**

```text
Create User Profile Page
```

**Description**

```text
Create a user profile page.

The page should contain:
- User name and email
- Order history
- Edit profile option
- Logout button
```

**Milestone:** Final Project  
**Assign to:** Teammate 4

---

# 7. Our GitHub Issues After Creation

```text
#1 Create Product Page          → Milestone: Project MVP     → Teammate 1
#2 Create Cart Page             → Milestone: Project MVP     → Teammate 2
#3 Create Checkout Page         → Milestone: Project MVP     → Teammate 3
#4 Create User Profile Page     → Milestone: Final Project   → Teammate 4
```

This gives every developer a clear task and shows which phase the work belongs to.

---

# 8. Create a GitHub Project (Kanban Board)

Create a new Project board linked to the repository.

**Board columns:**

```text
Todo  |  In Progress  |  Done
```

### How the board is used

1. Newly created issues start in **Todo**.
2. When a developer begins work, the issue is moved to **In Progress**.
3. After the Pull Request is merged, the issue is moved to **Done**.

This gives the entire team a visual overview of progress toward both milestones.

---

# 9. Why We Use Issues, Milestones & Projects Together

- **Issue** → answers “What exact work needs to be done?”
- **Milestone** → answers “Which larger goal does this work belong to?”
- **Project board** → answers “What is the current status of all work?”

Example:

```text
Issue #1 (Create Product Page)
↓
Belongs to Milestone: Project MVP
↓
Currently sitting in the “In Progress” column of the Kanban board
↓
Assigned to Teammate 1
```

---

# 10. Create a Branch for Each Issue

Each developer creates a separate feature branch.

### Teammate 1
```bash
git switch -c feature/product
```

### Teammate 2
```bash
git switch -c feature/cart
```

### Teammate 3
```bash
git switch -c feature/checkout
```

### Teammate 4
```bash
git switch -c feature/profile
```

Branch structure:

```text
main
│
├── feature/product
├── feature/cart
├── feature/checkout
└── feature/profile
```

### Why separate branches?

Developers can work on their features **without directly changing the `main` branch**.

---

# 11. Developer Workflow (Same for Everyone)

```text
GitHub Issue
↓
Move issue to “In Progress” on the Project board
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
Fix requested changes
↓
Approve & Merge
↓
Move issue to “Done” on the Project board
```

---

# 12. Example — Teammate 1 (Product Page)

Teammate 1 is responsible for:

```text
Issue #1 → Create Product Page (Milestone: Project MVP)
```

### Step-by-step

```bash
# 1. Clone the repository
git clone <repository-url>
cd ecommerce-website

# 2. Create and switch to the feature branch
git switch -c feature/product

# 3. Create the page (product.html) and add the required fields

# 4. Check status
git status

# 5. Stage changes
git add .

# 6. Commit
git commit -m "Add product page"

# 7. Push the branch
git push -u origin feature/product
```

---

# 13. Create Pull Request

After pushing, Teammate 1 opens a Pull Request:

```text
feature/product  →  main
```

**PR Title**

```text
Add product page
```

**PR Description**

```text
Added the product page with:
- Product name
- Product image
- Price
- Description
- Add to Cart button

Closes #1
```

`Closes #1` links the Pull Request to Issue #1. When the PR is merged, GitHub can automatically close the issue.

---

# 14. Code Review

Another teammate reviews the Pull Request and checks:

- Does the feature work?
- Is the code readable?
- Does it satisfy the issue requirements?
- Are there any obvious problems?

Example review comment:

```text
Please add a “Back to Home” link on the product page.
```

---

# 15. Make Changes After Review

Teammate 1 fixes the requested change:

```bash
git add .
git commit -m "Add back-to-home link on product page"
git push
```

The **same Pull Request is updated automatically**. No new PR is needed.

---

# 16. Approve and Merge

```text
Pull Request
↓
Review
↓
Approved
↓
Merge into main
↓
Issue automatically closed (if “Closes #1” was used)
↓
Move the card to “Done” on the Project board
```

The Product Page is now part of the stable `main` branch.

---

# 17. Other Team Members Follow the Same Workflow

### Teammate 2 — Cart Page (MVP)
```text
Issue #2 → feature/cart → cart.html → Commit → Push → PR → Review → Merge
```

```bash
git switch -c feature/cart
git add .
git commit -m "Add cart page"
git push -u origin feature/cart
```

### Teammate 3 — Checkout Page (MVP)
```text
Issue #3 → feature/checkout → checkout.html → Commit → Push → PR → Review → Merge
```

```bash
git switch -c feature/checkout
git add .
git commit -m "Add checkout page"
git push -u origin feature/checkout
```

### Teammate 4 — User Profile Page (Final Project)
```text
Issue #4 → feature/profile → profile.html → Commit → Push → PR → Review → Merge
```

```bash
git switch -c feature/profile
git add .
git commit -m "Add user profile page"
git push -u origin feature/profile
```

---

# 18. How the Team Works in Parallel

All four developers can work at the same time:

```text
main
│
┌───────────────────┼───────────────────┐
│                   │                   │
feature/product     feature/cart        feature/checkout
│                   │                   │
PR                  PR                  PR
│                   │                   │
└───────────────────┼───────────────────┘
                    ↓
                   main
                    ↑
              feature/profile (Final Project)
```

Issues 1–3 belong to **Project MVP**.  
Issue 4 belongs to **Final Project**.

---

# 19. What Happens When a PR Is Merged?

Example: Product Page PR is merged.

```text
feature/product → Merge → main
```

Other developers should update their local `main` before continuing:

```bash
git switch main
git pull origin main
```

Then they can create or update their feature branches based on the latest code.

---

# 20. What If Two Developers Change the Same Code?

If two people edit the same part of a file, Git may create a **merge conflict**:

```text
<<<<<<< HEAD
<h1>Shop Now</h1>
=======
<h1>Welcome to Our Store</h1>
>>>>>>> feature/product
```

The developers must decide the correct final version, then:

```bash
git add .
git commit
```

---

# 21. Complete Team Workflow

```text
E-commerce Website
│
↓
Create GitHub Repository
│
↓
Add Team Members
│
↓
Create Milestones (Project MVP + Final Project)
│
↓
Create Issues (#1–#4) and assign to milestones
│
↓
Create GitHub Project board (Todo | In Progress | Done)
│
↓
Assign Issues to teammates
│
┌─────────────────┼─────────────────┐
↓                 ↓                 ↓
Issue #1          Issue #2          Issue #3
Product           Cart              Checkout
(MVP)             (MVP)             (MVP)
↓                 ↓                 ↓
Branch            Branch            Branch
↓                 ↓                 ↓
Code → Commit → Push → PR → Review → Merge
└─────────────────┼─────────────────┘
                  ↓
                 main
                  ↑
            Issue #4 (Final Project)
            User Profile
```

---

# 22. Important GitHub Concepts (Quick Reference)

```
| Concept       | Simple Meaning                                      |
|---------------|-----------------------------------------------------|
| Repository    | Complete project                                    |
| Team Member   | Developer working on the project                    |
| Issue         | Single task/feature that needs to be completed      |
| Milestone     | Group of issues that form a larger goal/phase       |
| Project Board | Visual Kanban (Todo → In Progress → Done)           |
| Branch        | Separate workspace for a feature                    |
| Commit        | Saved change                                        |
| Push          | Send local changes to GitHub                        |
| Pull Request  | Request to merge changes into another branch        |
| Review        | Check another developer’s code                      |
| Merge         | Add approved changes into the target branch         |
| Conflict      | Git cannot automatically combine changes            |
```

---

# 23. Golden Rule for Team Projects

```text
Don’t develop directly on main
↓
Create a feature branch
↓
Do your work
↓
Commit with a clear message
↓
Push the branch
↓
Create a Pull Request
↓
Get a review
↓
Fix any requested changes
↓
Merge into main
↓
Update the Project board (move card to Done)
```

### Remember the full cycle

> **Issue → Milestone → Project Board → Branch → Code → Commit → Push → Pull Request → Review → Merge**

---

# 24. E-commerce Team Checklist

Before starting the project, make sure the team has completed:

- [ ] Create one GitHub repository (`ecommerce-website`)
- [ ] Add all teammates as collaborators
- [ ] Create two milestones: **Project MVP** and **Final Project**
- [ ] Create four issues and link them to the correct milestones
- [ ] Create a GitHub Project board with columns: Todo | In Progress | Done
- [ ] Assign issues to teammates
- [ ] Create a separate feature branch for each issue
- [ ] Use meaningful commit messages
- [ ] Push feature branches to GitHub
- [ ] Create Pull Requests (link them with `Closes #X`)
- [ ] Review teammates’ code
- [ ] Fix requested changes
- [ ] Merge approved Pull Requests into `main`
- [ ] Move cards to **Done** on the Project board
- [ ] Keep local `main` up to date (`git pull`)
- [ ] Resolve merge conflicts when necessary

**Main idea:**

> Git helps developers manage their code.  
> GitHub helps the team collaborate, plan, and track that code through Issues, Milestones, and Project boards.
