# Assignment — GitHub Team Collaboration Workflow

## Problem Statement

You are working in a team of **4 developers** to build an **E-Commerce Website** using GitHub.

The team needs to develop different parts of the website separately and then combine the work into the `main` branch through Pull Requests.

### Project

```text
E-Commerce Website
```

### Team Tasks

| Developer   | Feature           |
| ----------- | ----------------- |
| Developer 1 | Product Page      |
| Developer 2 | Cart Page         |
| Developer 3 | Checkout Page     |
| Developer 4 | User Profile Page |

Create a GitHub repository and use GitHub Issues, branches, commits, pushes, Pull Requests, code reviews, and merging to manage the project.

---

# Q1. Project Setup and Issues

Create the GitHub repository:

```text
e-commerce-website
```

Then:

1. Add 4 teammates to the repository.
2. Create **4 GitHub Issues** for the four features.
3. Assign each Issue to the appropriate developer.
4. Create a separate feature branch for each Issue.

Use meaningful branch names such as:

```text
feature/product
feature/cart
feature/checkout
feature/profile
```

---

# Q2. Develop Features and Create Pull Requests

Each developer should work on their assigned feature.

For each feature:

1. Create the required HTML/CSS/JS files.
2. Check the changes using `git status`.
3. Stage the changes.
4. Create a meaningful commit.
5. Push the feature branch to GitHub.
6. Create a Pull Request from the feature branch to `main`.
7. Add a short description to the Pull Request.
8. Link the Pull Request with the related Issue.

Example:

```text
Issue #1
    ↓
feature/product
    ↓
Commit
    ↓
Push
    ↓
Pull Request
    ↓
main
```

---

# Q3. Code Review and Merge

Work as a team to complete the Pull Request process.

1. Review at least **one teammate's Pull Request**.
2. Add one useful review comment.
3. Ask the developer to make a small change.
4. Developer commits and pushes the change.
5. Review the updated Pull Request.
6. Approve the Pull Request.
7. Merge it into `main`.
8. Update the local `main` branch after the merge.

Finally, show the GitHub repository containing all four features.

### Expected Workflow

```text
Issue
  ↓
Branch
  ↓
Code
  ↓
Commit
  ↓
Push
  ↓
Pull Request
  ↓
Code Review
  ↓
Changes
  ↓
Approval
  ↓
Merge
  ↓
main
```

## Submission Checklist

* [ ] GitHub repository created
* [ ] 4 teammates added
* [ ] 4 Issues created and assigned
* [ ] 4 feature branches created
* [ ] Features implemented
* [ ] Commits created
* [ ] Branches pushed to GitHub
* [ ] Pull Requests created
* [ ] Code review completed
* [ ] Changes made after review
* [ ] Pull Requests merged into `main`
* [ ] Local `main` updated
