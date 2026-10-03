# Open Source Style Collaboration on GitHub (Collaborating on a GitHub Repository Without Being Added as a Collaborator)

---

### 1. Title- How to Collaborate on GitHub Using Fork + Pull Request

---

### 2. What is this method?

In many projects (especially open-source), the owner does **not** add you as a collaborator.  
This means you **cannot** push code directly to the original repository.

Instead, you follow this safe method:

```text
Fork the repository
↓
Work on your own copy
↓
Create a Pull Request
↓
Owner reviews and merges
```

This way the original project stays protected, and your work can still be added after review.

---

### 3. Why do we use this method?

- The main repository remains safe
- Every change is reviewed before merging
- No one can accidentally break the main code
- This is how real open-source projects work (React, VS Code, Linux, etc.)

---

### 4. Step-by-Step Process (Very Important)

#### Step 1: Fork the Repository
1. Go to the original repository on GitHub
2. Click the **Fork** button (top-right corner)
3. GitHub will create a copy of the project under **your account**

#### Step 2: Clone Your Fork
Open terminal and run:

```bash
git clone https://github.com/YOUR-USERNAME/repository-name.git
cd repository-name
```

#### Step 3: Create a New Branch
Never work directly on the `main` branch.

```bash
git switch -c feature/your-feature-name
```

Example:
```bash
git switch -c feature/add-clear-button
```

#### Step 4: Make Your Changes
- Edit the files
- Add new features or fix bugs

#### Step 5: Commit Your Work
```bash
git add .
git commit -m "Add clear all button"
```

#### Step 6: Push to Your Fork
```bash
git push -u origin feature/add-clear-button
```

#### Step 7: Create a Pull Request
1. Go to your fork on GitHub
2. Click **Compare & pull request**
3. Write a clear title and description
4. Click **Create pull request**

#### Step 8: Wait for Review
- The **Owner of the main repo (or Team Leader)** will review your code
- They may ask for small changes
- After approval, they will **merge** your Pull Request

---

### 5. Simple Example

**Original Repository:** `simple-ecom-website` (Meeshoo)  
**Your Task:** Add a “Clear All” button on the cart page

1. Fork the repository `simple-ecom-website` (Meeshoo)
2. Clone your fork
3. Create branch → `feature/clear-button`
4. Add this line in the cart page (example):
   ```html
   <button>Clear All</button>
   ```
5. Commit and push
6. Open a Pull Request
7. **Owner of the main repo (or Team Leader)** reviews and merges it

Now your button is part of the original project!

---

### 6. Important Rules to Remember

| Rule                              | Why it matters                              |
|-----------------------------------|---------------------------------------------|
| Always fork first                 | You work on your own copy                   |
| Never push to the original repo   | You don’t have write permission             |
| Always create a new branch        | Keeps work organized                        |
| Write clear commit messages       | Helps reviewers understand your changes     |
| Open a Pull Request               | This is how your code gets into the project |
| Respond to review comments        | Shows good teamwork                         |

---

### 7. Useful Commands (Keep these handy)

```bash
# Clone your fork
git clone https://github.com/YOUR-USERNAME/repo-name.git

# Create feature branch
git switch -c feature/my-feature

# Stage and commit
git add .
git commit -m "Meaningful message"

# Push to your fork
git push -u origin feature/my-feature
```

---

### Optional but Recommended – Keep your fork updated

You should regularly update your fork with the latest changes from the original repository.

**Option 1: Using the Sync button (Easiest)**
1. Go to your forked repository on GitHub
2. Click the **Sync fork** button
3. Click **Update branch**

**Option 2: Using Git commands**
```bash
git remote add upstream https://github.com/ORIGINAL-OWNER/repo-name.git
git fetch upstream
git switch main
git merge upstream/main
```

---

### 8. Difference: Collaborator vs Fork Method

| Point                  | Added as Collaborator     | Fork + Pull Request          |
|------------------------|---------------------------|------------------------------|
| Can push directly?     | Yes                       | No                           |
| Need owner’s approval? | Optional                  | Always required              |
| Risk to main branch    | Higher                    | Very low                     |
| Used in open source?   | Rarely                    | Very common                  |

---

### 9. One-Line Summary

> **Fork → Create Branch → Code → Commit → Push → Open Pull Request → Get it Reviewed → Merged**

---

**Remember:**  
You do **not** need to be added as a collaborator to contribute.  
Just fork the project and send a Pull Request. This is professional and safe collaboration.
