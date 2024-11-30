
#  ~ <a href="https://git-scm.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git" height="32"/></a> Git and GitHub ~

---
### **Basic Git and GitHub Terminologies**

---

#### **Git Basics**
- **Repository (Repo)**: A directory tracked by Git, containing all project files, history, and branches.
- **Commit**: A snapshot of changes made to files in the repository.
- **Branch**: A separate line of development within a repository.
- **Merge**: Combining changes from one branch into another.
- **Staging Area**: A place to prepare changes before committing.
- **HEAD**: Refers to the current branch or the latest commit in the branch.
- **Remote**: A version of your repository stored on a server (e.g., GitHub, GitLab).

---

#### **GitHub Basics**
- **Fork**: A personal copy of another user's repository on GitHub.
- **Pull Request (PR)**: A request to merge changes from one branch or fork into another.
- **Clone**: A local copy of a remote repository.
- **Upstream**: The original repository that a fork is derived from.
- **Origin**: The default name for your remote repository.
- **Issue**: A GitHub feature for tracking bugs, tasks, or suggestions.
- **Star**: A way to bookmark a repository you find interesting.

---

#### **File States in Git**
1. **Untracked**: Files not yet added to Git.
2. **Staged**: Files added to the staging area using `git add`.
3. **Modified**: Files with unsaved changes.
4. **Committed**: Files saved as part of a commit.

---

#### **Repository Basics**  
- Initialize a repository:  
  ```bash
  git init
  ```

- Clone a repository:  
  ```bash
  git clone [github_url]
  ```

- Add a remote:  
  ```bash
  git remote add origin [github_url]
  ```

- Check remote connections:  
  ```bash
  git remote -v
  ```

---

#### **Tracking Changes**  
- View file status:  
  ```bash
  git status
  ```

- Stage changes:  
  ```bash
  git add [file_name]  # Add specific file
  git add .            # Add all changes
  ```

- Commit changes:  
  ```bash
  git commit -m "Short message" -m "Detailed description"
  ```

---

#### **Pushing and Pulling**  
- Push changes:  
  ```bash
  git push origin main
  git push -u origin main  # Set default upstream
  ```

- Pull updates:  
  ```bash
  git pull origin main
  git pull  # Simplified if upstream is set
  ```

---

#### **Branching**  
- View branches:  
  ```bash
  git branch
  ```

- Create a new branch:  
  ```bash
  git checkout -b [branch_name]
  ```

- Switch branches:  
  ```bash
  git checkout [branch_name]
  ```

- Merge branches:  
  ```bash
  git merge [branch_name]
  ```

---

#### **Viewing Commit History**  
- View history:  
  ```bash
  git log
  git log --oneline
  ```

- View a specific commit:  
  ```bash
  git show [commit_hash]
  ```

---

#### **Undoing Changes**  
- Unstage changes:  
  ```bash
  git reset HEAD [file_name]
  ```

- Revert a commit:  
  ```bash
  git revert [commit_hash]
  ```

- Discard changes:  
  ```bash
  git checkout -- [file_name]
  ```

---

#### **Working with `.gitignore`**  
- Create a `.gitignore` file in the root directory and specify files/folders to ignore.  
  Example:  
  ```bash
  echo *.log >> .gitignore
  echo node_modules/ >> .gitignore
  ```

- Remove a tracked file from Git but keep it locally:  
  ```bash
  git rm --cached [file_name]
  ```

---

#### **Deleting a Branch**  
- Locally:  
  ```bash
  git branch -d [branch_name]
  ```

- Remotely:  
  ```bash
  git push origin --delete [branch_name]
  ```

---

#### **Additional Tools**  
- View concise history:  
  ```bash
  git log --oneline --graph --all
  ```

- View the status of staged changes:  
  ```bash
  git diff --staged
  ```  
---