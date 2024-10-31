# Getting Started with Git

## Installation

1. **Check if Git is installed:**

   Open your terminal and run:
   ```bash
   git --version
   ```

2. **Download Git:**

   If Git is not installed, you can download it from the [official Git website](https://git-scm.com/).


3. **Set up your project:**

   - Open the project you want to track in your IDE or Code Editor.
   - Open the terminal and navigate to the project directory.


4. **Configure Git with your name and email:**

   This allows Git to track who made changes to the project:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```

## Initializing a Repository

A **repository (repo)** is where Git tracks all changes in a project. To start tracking a project, you need to initialize a Git repository.

1. **Initialize a Git repository:**
   ```bash
   git init
   ```

2. **Set the default branch name to `main`:**

   By convention, it’s best to name the main branch `main` instead of `master`.
   ```bash
   git config --global init.defaultBranch main
   ```

The **main** branch is the primary branch in your project.

## Checking Project File Status

To view the current status of your project files, use:
```bash
git status
```

This command shows:
- **Branch**: The branch you’re currently in.
- **Commits**: Files staged and ready for commit.
- **Untracked Files**: Files not being tracked by Git.

## Staging and Committing Changes

1. **Stage a file to be committed:**
   ```bash
   git add filename.extension
   ```
   To stage all files, use:
   ```bash
   git add ./
   ```

2. **Commit a file with a message:**
   ```bash
   git commit -m "Add a message describing the commit"
   ```

## Viewing Commit History

To see a list of all commits made:
```bash
git log
```

This shows the commit hash, author, date, and message. Press `q` to exit the log view.

## Checking Out a Git Commit

To switch to a specific commit (e.g., for bug fixes or modifications):
```bash
git checkout <commit-hash>
```

Example:
```bash
git checkout ccff4ce5dd9b29282f04da7b70dcbac7e1d0d96b
```

> **Tip:** Create a new branch before making changes to a previous commit, so you can merge changes back to the main branch when ready.

## Returning to the Main State

To return to the latest commit in the main branch:
```bash
git checkout main
```

To discard all changes in a detached head state before returning to the main branch:
```bash
git checkout -f main
```

# Using GitHub

GitHub allows you to store repositories remotely on the cloud, enabling collaboration and safeguarding against data loss.

## Setting Up GitHub

1. **Sign up or sign in to [GitHub](https://github.com/).**
2. **Create a new repository:**
   - Choose a name.
   - Select **public** or **private**.
   - Leave **Add a README file** unchecked.

3. **Copy the repository link:**
   - Switch to SSH for secure access, and copy the SSH link provided.

## Connecting Git to GitHub

1. **Set the branch name to `main` (if not done):**
   ```bash
   git branch -M main
   ```

2. **Add the remote repository link:**
   ```bash
   git remote add origin <github-link>
   ```
   > You can add multiple remote repositories by using a different name instead of `origin`, though it's best to keep only one.

3. **Push your main branch to GitHub:**
   ```bash
   git push -u origin main
   ```

Now, you can view your repository on GitHub!

> **Note:** If you encounter connection issues, you might need to add an SSH key to GitHub. Check the [GitHub Troubleshooting Guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) for assistance.

## Pushing and Pulling Changes

1. **Staging and Committing Changes:**  
   After making changes, you’ll need to stage and commit them.
   

2. **Pushing Changes to GitHub:**
   After committing locally, push the changes to GitHub:
   ```bash
   git push
   ```

3. **Updating Local Repository with Remote Changes:**  
   Keeping your local repo up-to-date with remote changes is essential when working in a team. You can pull updates with:
   ```bash
   git pull
   ```
> **Note:** Make sure there are no uncommitted changes before pulling updates on any branch. Uncommitted changes can lead to merge conflicts or prevent the pull operation from completing successfully.
   
## Best Practices with Pulling and Merging

It’s generally better to pull updates on the `main` branch, as this ensures all branches are updated with the latest changes.

```