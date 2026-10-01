**Assignment: Team Collaboration using GitHub**

**Title:** Development of a College Event Registration System using GitHub Team Workflow

---

### 1. Problem Statement

College events (workshops, seminars, cultural fests, and technical competitions) currently face difficulties in registration management. Students register through scattered Google Forms, WhatsApp groups, or paper forms. This leads to:

- Duplicate registrations  
- Missing participant details  
- No central list of registered students  
- Difficulty in tracking event capacity  
- Lack of a proper participant dashboard for organizers  

There is a need for a simple web-based **College Event Registration System** that allows students to view events, register for them, and lets organizers manage participant information efficiently.

Your team of **4 developers** must design and develop this system collaboratively using **GitHub** following proper team workflow practices (Issues, Milestones, Project Board, Branches, and Pull Requests).

---

### 2. Project Overview

**Project Name:** College Event Registration System  

**Repository Name:** `college-event-registration`

**Main Pages / Features to be developed:**

| Feature                  | Description                                      | Assigned To   |
|--------------------------|--------------------------------------------------|---------------|
| Event Listing Page       | Display all upcoming college events              | Teammate 1    |
| Event Registration Page  | Form for students to register for an event       | Teammate 2    |
| Participant Dashboard    | View and manage list of registered participants  | Teammate 3    |
| Student Profile Page     | Show student’s registered events and details     | Teammate 4    |

---

### 3. Project Management Requirements

You must set up and use the following GitHub features:

#### A. Issues (4 Issues)
Create the following issues:

1. **Create Event Listing Page**  
2. **Create Event Registration Page**  
3. **Create Participant Dashboard**  
4. **Create Student Profile Page**

#### B. Milestones (2 Milestones)
- **Milestone 1: Project MVP**  
  Contains Issues 1, 2, and 3 (Event Listing, Registration, and Participant Dashboard)

- **Milestone 2: Final Project**  
  Contains Issue 4 (Student Profile Page)

#### C. GitHub Project Board (Kanban)
Create a Project board with exactly **3 columns**:
- **Todo**
- **In Progress**
- **Done**

All issues must be added to this board and moved across columns as work progresses.

---

### 4. Team Workflow Requirements

Every team member must follow this workflow:

```text
Issue → Assign → Create Feature Branch → Develop → Commit → Push → Create Pull Request → Code Review → Fix Changes → Merge into main → Move card to Done
```

**Branch naming convention:**
- `feature/event-listing`
- `feature/registration`
- `feature/dashboard`
- `feature/profile`

**Important Rules:**
- Do **not** push code directly to the `main` branch.
- Every feature must be developed on its own branch.
- Every Pull Request must reference the related issue using `Closes #IssueNumber`.
- At least one teammate must review each Pull Request before merging.
- Keep the local `main` branch updated regularly using `git pull`.

---

### 5. Expected Deliverables

1. A public or private GitHub repository named `college-event-registration`
2. Properly created **Issues**, **Milestones**, and **Project Board**
3. Four feature branches corresponding to the four issues
4. Meaningful commit messages
5. Pull Requests with proper titles and descriptions
6. Code reviews (visible as comments on PRs)
7. All approved changes merged into the `main` branch
8. Final working website containing all four pages

---

### 6. Suggested Page Content

**Event Listing Page**
- Event name
- Date & time
- Venue
- Short description
- “Register” button

**Event Registration Page**
- Student Name
- Email / Roll Number
- Department
- Event selection
- Submit button

**Participant Dashboard**
- List of registered students
- Event name
- Registration date
- Basic filters or search (optional)

**Student Profile Page**
- Student name and details
- List of events the student has registered for
- Logout option

---

### 7. Evaluation Criteria

| Criteria                              | Marks |
|---------------------------------------|-------|
| Proper repository setup & collaborators | 10    |
| Correct creation of Issues & Milestones | 15    |
| Proper use of Project Board (Kanban)    | 10    |
| Feature branches & meaningful commits   | 15    |
| Pull Requests + Code Reviews            | 20    |
| Working pages & code quality            | 20    |
| Overall team collaboration & documentation | 10 |
| **Total**                             | **100** |

---

### 8. Submission Guidelines

Submit the following:
1. Link of GitHub repository
2. Link of GitHub Project board
3. Short report (1–2 pages) explaining:
   - How issues and milestones were used
   - How the team collaborated using branches and Pull Requests
   - Any merge conflicts faced and how they were resolved

---

**Golden Rule to Remember:**

> **Issue → Milestone → Project Board → Feature Branch → Code → Commit → Push → Pull Request → Review → Merge**
