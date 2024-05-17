# Git Commands Quick Reference

**1. Initialize a Repository**

```bash
git init
```

This command initializes a new Git repository in the current directory.

**2. Clone a Repository**

```bash
git clone <repository_URL>
```

This command clones a remote repository onto your local machine.

**3. Check Status**

```bash
git status
```

This command displays the current status of the repository, showing which files are modified, staged, or untracked.

**4. Stage Changes**

```bash
git add <file_name>
```

This command stages changes in the specified file to be committed.

**5. Commit Changes**

```bash
git commit -m "commit_message"
```

This command commits staged changes to the repository with a descriptive message.

**6. Pull Changes**

```bash
git pull
```

This command fetches and merges changes from the remote repository to the local branch.

**7. Push Changes**

```bash
git push
```

This command uploads committed changes from the local repository to the remote repository.

**8. View Commit History**

```bash
git log
```

This command displays a log of commit history, showing commit messages, authors, dates, and commit IDs.

**9. Create a New Branch**

```bash
git branch <branch_name>
```

This command creates a new branch based on the current branch.

**10. Switch Branches**

```bash
git checkout <branch_name>
```

This command switches to the specified branch.

**11. Merge Branches**

```bash
git merge <branch_name>
```

This command merges changes from the specified branch into the current branch.

**12. Discard Changes**

```bash
git checkout -- <file_name>
```

This command discards changes in the specified file, reverting it to the last committed state.

**13. Remove Untracked Files**

```bash
git clean -f
```

This command removes untracked files from the working directory.

**14. Configure User Information**

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

These commands configure your name and email address to be associated with your Git commits.
