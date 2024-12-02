### **Git Commands Cheatsheet**

---

#### **Basic Commands**

- **`git init`**: Initialize a new Git repository.
  ```bash
  git init                 # Create a new, empty Git repository in the current directory
  ```
- **`git clone`**: Clone a repository from a remote source.
  ```bash
  git clone https://github.com/user/repo.git  # Clone a remote repository to your local machine
  ```
- **`git status`**: shows the status of the repository
  ```bash
  git status
  ```
- **`git log`**: logs all commits
  ```bash
  git log
  ```
  different formatting options at [log doc](https://git-scm.com/docs/git-log)

#### **Staging and Committing**

- **`git add`**: Add changes to the staging area.
  ```bash
  git add filename.txt     # Stage a specific file
  git add .                # Stage all changes in the current directory
  ```
- **`git commit`**: Commit staged changes to the local repository.
  ```bash
  git commit -m "Commit message"   # Commit with a descriptive message
  ```

#### **Branching**

- **`git branch`**: Create, list, or delete branches.
  ```bash
  git branch               # List all branches
  git branch new-branch    # Create a new branch called 'new-branch'
  git branch -d branch-name  # Delete a branch called 'branch-name'
  ```
- **`git checkout`**: Switch branches or restore files.
  ```bash
  git checkout branch-name # Switch to an existing branch
  git checkout -b new-branch # Create and switch to a new branch
  ```
- **`git switch`**: Switch between branches.
  ```bash
  git switch branch-name   # Switch to an existing branch
  git switch -c new-branch # Create and switch to a new branch
  ```

#### **Merging and Rebasing**

- **`git merge`**: Merge branches together.
  ```bash
  git merge branch-name    # Merge 'branch-name' into the current branch
  ```
- **`git rebase`**: Reapply commits on top of another base tip.
  ```bash
  git rebase branch-name   # Reapply commits from the specified branch onto the current branch
  ```

#### **Pushing and Pulling**

- **`git push`**: Push changes to a remote repository.
  ```bash
  git push -u origin branch-name  # sets upstream
  git push origin branch-name  # Push local commits to the remote repository
  ```
- **`git pull`**: Pull changes from a remote repository.
  ```bash
  git pull origin branch-name  # Fetch and merge changes from the remote branch
  ```

#### **Viewing History**

- **`git log`**: View the commit history.
  ```bash
  git log                   # View the commit history
  git log --oneline         # View a condensed version of the commit history
  ```
- **`git status`**: Show the current status of the working directory and staging area.
  ```bash
  git status                # Display changes to be committed, staged changes, and untracked files
  ```

#### **Undoing Changes**

- **`git reset`**: Unstage or undo commits.
  ```bash
  git reset filename.txt    # Unstage a file
  git reset --hard          # Reset the working directory to the last commit
  ```
- **`git revert`**: Create a new commit that undoes a previous commit.
  ```bash
  git revert commit-hash    # Create a commit that reverts the changes from a specific commit
  ```

#### **Remote Repositories**

- **`git remote`**: Manage remote connections.
  ```bash
  git remote add origin https://github.com/user/repo.git  # Add a remote repository
  git remote -v           # List all configured remote repositories
  ```

#### **Tags**

- **`git tag`**: Create, list, or delete tags.
  ```bash
  git tag v1.0             # Create a tag named 'v1.0'
  git tag                  # List all tags
  git tag -d v1.0          # Delete a tag named 'v1.0'
  ```

---
