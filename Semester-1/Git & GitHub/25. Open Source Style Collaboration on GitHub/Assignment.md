# Assignment: Open Source Style Collaboration on GitHub(Collaborating Without Being Added as a Collaborator)

---

### Objective

The goal of this assignment is to practice the **Fork + Pull Request** workflow in a **group**.  
Your team will **not** be added as collaborators. You must contribute to the projects by forking the repository, making changes on your own copies, and submitting Pull Requests.

---

### Group Guidelines

- Form a group of **3–4 members**
- One member can fork the repository and share it, **or** each member can fork individually
- Every member must create their own feature branch and contribute
- All changes must go through **Pull Requests**
- The **Owner / Team Leader** of the original repository will review and merge the final Pull Requests

**Branch naming example:** `feature/your-feature-name`

---

## Part A – Practical Group Projects

### Problem Statement 1: Book Catalog Website  
**(Group Project)**

**Original Repository:** `book-catalog-website`

**Problem:**  
A simple Book Catalog Website needs to be created. Currently the project is empty or incomplete. Your group has to create a basic Book Catalog page that displays a list of books.

**Group Task:**
- Fork the repository
- Create a branch named `feature/book-catalog-page`
- Create a **Book Catalog page** that shows:
  - Book Title
  - Author Name
  - Availability Status
- Different members can work on different parts (HTML structure, styling, sample data, etc.)
- Commit, push, and create a Pull Request

**Expected Outcome:**  
A working Book Catalog page should be added to the project after the PR is merged.

---

### Problem Statement 2: College Event Registration System  
**(Group Project)**

**Original Repository:** `college-event-registration`

**Problem:**  
The Event Listing page currently shows event name, date, and venue, but it does not show the **registration deadline**. Students are unable to see till when they can register.

**Group Task:**
- Fork the repository
- Create a branch named `feature/add-deadline`
- Add a **Registration Deadline** field/section on the Event Listing page
- Display a sample deadline (e.g., “Registration Deadline: 15 October 2025”)
- Team members can divide work (UI design, content, responsiveness, etc.)
- Commit, push, and create a Pull Request

**Expected Outcome:**  
Each event card/section on the listing page should clearly show the registration deadline.

---

### Problem Statement 3: Simple Todo Application  
**(Group Project)**

**Original Repository:** `simple-todo-app`

**Problem:**  
The Todo application allows users to add and delete individual tasks, but there is no option to mark a task as **Completed**.

**Group Task:**
- Fork the repository
- Create a branch named `feature/mark-completed`
- Add a **“Mark as Completed”** button (or checkbox) next to each task
- When clicked, the task should get a visual indication (e.g., strikethrough text or change color)
- Members can share responsibilities (JavaScript logic, CSS styling, testing, etc.)
- Commit, push, and create a Pull Request

**Expected Outcome:**  
Users should be able to mark tasks as completed, and completed tasks should look different from pending tasks.

---

## Part B – Theoretical Questions  
**(Individual)**

### A. One-Line Answer Questions (5)

1. What is the first step you must take to contribute to a repository if you are not added as a collaborator?
2. Which GitHub button creates a personal copy of a repository under your account?
3. Why should you never work directly on the `main` branch?
4. What is the purpose of creating a Pull Request?
5. Who reviews and merges the Pull Request in this collaboration model?

---

### B. Fill in the Blanks (5)

1. In the Fork + Pull Request method, you work on your own ________ of the repository.
2. The command used to create and switch to a new branch is `git switch -c ________`.
3. After making changes, you must ________ and then push the branch to your fork.
4. The easiest way to update your fork with the latest changes is by clicking the ________ button on GitHub.
5. The complete flow of this collaboration method is: Fork → Create Branch → Code → Commit → Push → ________ → Review → Merge.

---

### C. True / False (5)

1. You need to be added as a collaborator to contribute code to a public GitHub repository.  
2. Creating a Pull Request allows the owner to review your changes before they are added to the main project.  
3. You should always work directly on the `main` branch of your fork.  
4. The `git fetch upstream` command downloads the latest changes but does not merge them automatically.  
5. In the Fork + Pull Request method, the original repository remains safe from direct unwanted changes.

---

### D. Descriptive Answer Questions (3)

1. Explain the difference between being added as a collaborator and using the Fork + Pull Request method.
2. Why is the Fork + Pull Request method considered safer for the main repository?
3. Describe the complete step-by-step process a student should follow to contribute a small feature using the open-source style collaboration method.

---

### Submission Guidelines

**For Part A (Group Projects):**
- Group members list with roles
- Link to the forked repository
- Links to all Pull Requests created by the group
- Branch names used
- Short note explaining the contribution of each member

**For Part B (Theoretical – Individual):**
- Each student must submit their own answers

---

### Evaluation Criteria

| Section                          | Marks |
|----------------------------------|-------|
| Practical Group Projects (Part A)| 60    |
| Theoretical Questions (Part B)   | 40    |
| **Total**                        | **100** |

---

### Golden Rule

> **Fork → Create Branch → Code → Commit → Push → Open Pull Request → Get Reviewed → Merged**

Your group does **not** need collaborator access.  
Contribute like a real open-source team.
