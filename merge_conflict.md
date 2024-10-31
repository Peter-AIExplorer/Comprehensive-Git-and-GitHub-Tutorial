# Merge Conflicts

When two or more developers edit the same line of code, Git gets confused. This situation is called a **merge conflict**. When this happens, Git will ask you to choose whose changes to keep. It indicates that Git is uncertain about what part to merge.

## Fixing Merge Conflicts

### 1. Checkout to the Main Branch

```bash
git checkout main
```

### 2. Pull Updates

```bash
git pull
```

### 3. Checkout to Your Branch

```bash
git checkout <branch-name>
```

### 4. Merge the Main Branch

This command tries to merge the main branch together with your branch, which may trigger the conflict for you to resolve.

```bash
git merge main
```

#### Error Message:
```
CONFLICT (content): Merge conflict in readme.md
Automatic merge failed; fix conflicts and then commit the result.
```

### 5. Resolving Merge Conflicts

Depending on your IDE, you should be able to view the list of merge conflicts within an inbuilt versioning system. Locate this to display the list of conflicts.

- The arrows pointing to the left represent the changes from your branch.
- The arrows pointing to the right represent the conflicting changes coming from the main branch.

To resolve them, you can manually choose which changes to keep or remove by editing the lines. However, the usual way is to use the resolve option from the version control system:

1. **Select the Resolve Option**  
   On the pop-up tab, you are provided with three options:
   - Choose the other team member's changes.
   - Keep your changes.
   - Perform an advanced merge.  
   It is advisable to utilize the advanced merge option to maintain all changes without having to choose one.


2. **Select the Merge Option**  
   This opens the merge revision tab, where you can see changes from both team members (yours and the modifications made by the other team member now in the main branch). 


3. **Select the Changes to Keep**  
   Go through the changes and select the ones to keep in a hierarchical structure as you want them to be made. Once done, delete all other changes you are not maintaining.


4. **Select Apply.**

### 6. Committing the Changes

You now have the conflict resolved. It's time to commit these changes:

- **Stage Changes**

```bash
git add ./
```

- **Commit Changes**

```bash
git commit -m "Resolve merge conflict"  # You can choose a preferred message
```

- **Push Changes**

```bash
git push
```

You can now return to GitHub to merge the pull request.
```