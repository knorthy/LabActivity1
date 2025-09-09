# Laboratory Exercise 1: Introduction to Git and GitHub

---

## Objective

By the end of this laboratory session, students will be able to:

- Clone a shared GitHub repository.
- Create and switch to a branch from `main` before making changes.
- Add and modify files.
- Stage, commit, and push changes to GitHub.
- Merge changes back into `main`.

## Prerequisites

- Git must be installed on the workstation (`git --version` to verify).
- Students must have an active GitHub account.
- A text editor or IDE (Visual Studio Code recommended).

---

## Laboratory Procedure

### Step 1: Configure Git Identity and Credential Manager

Each student must configure their Git identity **for this repository only** (not global):

```bash
git config user.name "Your Name"
git config user.email "your.email@example.com"
```

Verify your configuration:

```bash
git config --list --local
```

#### (Optional but Recommended) Configure Git Credential Manager
If you want Git to remember your credentials securely, enable the credential manager:

```bash
git config credential.helper manager
```

- On macOS, you may use the macOS Keychain:
	```bash
	git config credential.helper osxkeychain
	```
- On Windows, you may use:
	```bash
	git config credential.helper manager-core
	```

This ensures Git will prompt you for credentials only once per repository and store them securely.

---

### Step 2: Clone the Repository

Each student will clone the class repository:

```bash
cd path/to/your/workspace
git clone https://github.com/2026-DCIT26/LabActivity1.git
cd LabActivity1
```

---

### Step 3: **Create and Switch to Your Personal Branch**

Each student must create a branch named using this format:

```
feature/<your-student-number>
```

**Example:**

```bash
git checkout -b feature/201811394
```

> This ensures that every student works on their own branch without affecting `main`.

---

### Step 4: Adding and Modifying Files

#### Add a New File

Create a file named `notes.txt`:

```bash
echo "This is my notes file." > notes.txt
```

Stage and commit:

```bash
git add notes.txt
git commit -m "Add notes.txt file with initial content"
```

Push the branch to GitHub:

```bash
git push origin feature/201811394
```

#### Modify an Existing File

Edit `README.md` using an editor or terminal:

```bash
echo "\n## Additional Notes\nThis is an update." >> README.md
```

Stage, commit, and push:

```bash
git add README.md
git commit -m "Update README with additional notes"
git push origin feature/201811394
```

Students should verify changes on GitHub in their own branch.

---

### Step 5: Merging Back to Main (Optional / Instructor-led)

After everyone has pushed their branch, the instructor may demonstrate merging one branch into `main`.

```bash
git checkout main
git merge feature/201811394
git push origin main
```

---

### Step 6: Verification

Students must:

- Refresh the repository page on GitHub.
- Confirm that their branch (e.g., `feature/201811394`) exists.
- Check that their commits and files appear under their branch.

---

## Summary of Commands

| Action             | Command                                                            |
| ------------------ | ------------------------------------------------------------------ |
| Configure identity | `git config user.name` / `git config user.email` |
| Credential manager | `git config credential.helper manager` (or `osxkeychain`/`manager-core`) |
| Clone repository   | `git clone https://github.com/2026-DCIT26/LabActivity1.git`        |
| Create branch      | `git checkout -b feature/201811394`                                |
| Switch branch      | `git checkout <branch>`                                            |
| Stage file(s)      | `git add <filename>`                                               |
| Commit changes     | `git commit -m "message"`                                          |
| Push to branch     | `git push origin feature/201811394`                                |
| Merge branch       | `git merge feature/201811394`                                      |
| Check status       | `git status`                                                       |
| View changes       | `git diff`                                                         |

---

### Deliverables

Each student must:

- Submit a screenshot of their terminal showing `git log` from their personal branch.
- Provide a link to their branch in the repository.
- Ensure that `notes.txt` and README updates are visible in their branch on GitHub.
\n## Additional Notes\nThis is an update.
