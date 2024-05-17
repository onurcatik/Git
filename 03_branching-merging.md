# Branching & Merging: A Quick Reference

**1. Create a New Branch**

```bash
git branch <branch_name>
```

This command creates a new branch with the specified name based on the current branch.

**2. Switch to a Branch**

```bash
git checkout <branch_name>
```

This command switches to the specified branch.

**3. Create & Switch to a New Branch**

```bash
git checkout -b <branch_name>
```

This command creates a new branch with the specified name and switches to it in one step.

**4. List Branches**

```bash
git branch
```

This command lists all branches in the repository, indicating the current branch with an asterisk.

**5. Merge Changes from Another Branch**

```bash
git merge <branch_name>
```

This command merges changes from the specified branch into the current branch.

**6. Delete a Branch**

```bash
git branch -d <branch_name>
```

This command deletes the specified branch. Use `-D` instead of `-d` to force deletion, even if changes are not merged.

**7. Rename a Branch**

```bash
git branch -m <old_name> <new_name>
```

This command renames the specified branch.

**8. View Merged Branches**

```bash
git branch --merged
```

This command lists branches that have been merged into the current branch.

**9. View Unmerged Branches**

```bash
git branch --no-merged
```

This command lists branches that have not been merged into the current branch.

**10. Abort a Merge**

```bash
git merge --abort
```

This command aborts the current merge operation and restores the state before the merge began.

**11. Resolve Merge Conflicts**

Merge conflicts occur when Git cannot automatically merge changes from different branches. Here's how to resolve them:

- **Identify Conflicted Files**: Git will mark conflicted files with conflict markers (`<<<<<<<`, `=======`, and `>>>>>>>`). Open these files in your code editor.

- **Review Changes**: Examine the conflicting sections in the file. Git presents both versions of the conflicting code and markers to indicate the conflict.

- **Resolve Conflicts**: Manually edit the conflicted sections, keeping the changes you want to keep and removing the conflict markers. Ensure the final version makes sense and preserves the intended functionality.

- **Save Changes**: Once conflicts are resolved, save the file(s) in your code editor.

- **Add Resolved Files**: After resolving conflicts, stage the resolved files using the `git add` command. For example:
   ```bash
   git add <resolved_file1> <resolved_file2> ...
   ```

- **Commit Changes**: Commit the resolved changes with a descriptive message:
   ```bash
   git commit -m "Resolved merge conflicts"
   ```

- **Continue Merge**: After resolving conflicts and committing changes, you can continue the merge process using:
   ```bash
   git merge --continue
   ```

- **Alternative Method**: If you want to abort the merge operation entirely and start over, you can use:
   ```bash
   git merge --abort
   ```