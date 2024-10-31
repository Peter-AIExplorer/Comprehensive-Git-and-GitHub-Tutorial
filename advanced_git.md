# Advanced Git

The following advanced concepts allow you to make changes, undo them, and delete changes when needed.

## 1. Checkout to a Specific Commit

```bash
git checkout <commit-hash>
```

This command is used to check out a particular commit before modifying or deleting every commit after it.

## 2. Git Reset

Suppose you want to delete a series of commits after checking out a commit. This command helps you remove the series of commits while keeping the changes implemented in them.

### 2.1. Soft Reset

```bash
git reset --soft <commit-hash>
```

Moves to a commit in history and keeps the changes made after that commit staged in the working directory.

### 2.2. Mixed Reset (Default)

```bash
git reset <commit-hash>
```

Moves to a commit in history, unstages the changes made after the commit, but keeps them in the working directory.

### 2.3. Hard Reset

```bash
git reset --hard <commit-hash>
```

Moves to the commit in history, unstages the changes, and also removes them from the working directory.

## 3. Git Revert

This command is used to undo changes by going back to a commit in history while still maintaining the log.

### Usage

```bash
git revert <commit-hash>
```

Once this command is executed, a merge conflict may pop up. You just need to clear the code you want to remove.

### Staging the Commit

```bash
git add ./
```

### Continuing the Revert

```bash
git revert --continue
```

A new terminal will pop up, requesting a message to be added. You can enter a message or exit by typing `:qa!` and pressing Enter to close.

## 4. Git Stash

Suppose you have changes that are yet to be staged and committed, but you need to temporarily work on another modification (like adding a feature to another commit) before returning to the changes you were making. You can use `git stash` to save staged or unstaged changes without committing them.

### To Do This:

#### Save Changes

```bash
git stash
```

#### Carry Out Other Modifications

You can stage, commit, and push them if necessary.

#### List the Stashes

```bash
git stash list
```

#### Apply Stash

```bash
git stash apply stash{index-of-the-stash}
```

For example, to apply the first stash:

```bash
git stash apply stash{0}
```
```