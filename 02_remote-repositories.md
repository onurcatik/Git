# Working with Remote Repositories: A Quick Reference

**1. Add a Remote Repository**

```bash
git remote add <remote_name> <remote_URL>
```

This command adds a new remote repository with a specified name and URL.

**2. List Remote Repositories**

```bash
git remote -v
```

This command lists all remote repositories associated with the current repository, along with their URLs.

**3. Remove a Remote Repository**

```bash
git remote remove <remote_name>
```

This command removes the specified remote repository from the list of remotes.

**4. Fetch Changes from a Remote Repository**

```bash
git fetch <remote_name>
```

This command fetches changes from the specified remote repository, but does not merge them into the local branch.

**5. Pull Changes from a Remote Repository**

```bash
git pull <remote_name> <branch_name>
```

This command fetches changes from the specified remote repository and merges them into the current branch.

**6. Push Changes to a Remote Repository**

```bash
git push <remote_name> <branch_name>
```

This command uploads committed changes from the local repository to the specified remote repository and branch.

**7. Rename a Remote Repository**

```bash
git remote rename <old_name> <new_name>
```

This command renames a remote repository from the old name to the new name.

**8. Show Information about a Remote Repository**

```bash
git remote show <remote_name>
```

This command displays detailed information about the specified remote repository, such as its URL and branches.

**9. Set Up Tracking Branches**

```bash
git branch --set-upstream-to=<remote_name>/<branch_name>
```

This command sets up a local branch to track a remote branch, enabling easier synchronization.

**10. Mirror a Repository**

```bash
git clone --mirror <repository_URL>
```

This command clones a remote repository as a mirrored copy, preserving all branches and tags.
