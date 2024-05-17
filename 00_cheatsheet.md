# Git Commands - Cheat Sheet

## Setting Up a Repository

### Git init & clone

- `git init`: Creates a new repository in a directory.
- `git clone [url] [new directory name]`: Clones a repository into a new directory.
- `git clone [url]`: Clones a repository into the current directory.

## Saving Changes

### Adding Files to Staging Area

- `git add [file name]`: Adds specified files to the staging area.
- `git add .`: Adds all changed files to the staging area.
- `git add '*[file type]'`: Example: `git add *.txt` adds only text files to the staging area.
- `git add [directory]`: Stages changes of files in a directory.

### Resetting Changes

- `git reset HEAD [file name]`: Resets a file in the working directory to be the same as the HEAD (last) commit.
- `git reset [commit ID]`: Resets files in the working directory to be the same as the specified commit.

### Committing Changes

- `git commit`: Opens Atom for adding a commit message on the top line. Remember to save.
- `git commit -m ["commit message"]`: Adds a commit message using the command line.
- `git commit -a -m ["commit message"]`: Commits changed tracked files.

### Viewing Changes

- `git diff`: Displays changes to files in the working directory (not staged).
- `git diff --staged`: Displays changes to staged files.
- `git diff [commit id 1] [commit id 2]`: Compares two commits.
- `git diff HEAD`: Displays changes between staged and unstaged file changes.

## Undoing Changes

### git clean

**Dry Run**

- `git clean -n`: Performs a dry run. It does not delete files but shows which files would be deleted.

**Actual Deletion**

- `git clean -f`: Initiates the actual deletion of untracked files.

**Removing Untracked Directories**

- `git clean -d`: Removes any untracked directories. Use in combination with the previous commands above.

### git revert

**Reversing Commits**

- `git commit HEAD`: Reverses the most recent commit.
- `git commit [commit ID]`: Reverses changes made associated with a specific commit ID.

**Customizing Commit Behavior**

- `git commit [commit ID] --no-edit`: Does not open the editor. The default command will open the editor.

## Reverting History

### Editing Commit Message

- `git commit --amend m [new commit message]`: Edits the commit message on the last commit.

### Adding Forgotten Staged Files

- `git commit --amend --no-edit`: Adds forgotten staged files to the most recent commit without changing the commit message.

### Adding New Staged Changes to Recent Commit

- `git commit --amend`: Takes the most recent commit and adds new staged changes to it.

## Collaborating and Syncing - GitHub

### Git Remote Commands

**Checking Remote Repositories**

- `git remote`: Checks if you have any remote repositories. Exception: If you have cloned a repo, the command will return the original repo as a remote repo.

**Displaying Remote Repository Details**

- `git remote -v`: Displays the full path to the remote repository.

**Adding Remote Repository**

- `git remote add origin [github url]`: Adds a remote repository. "Origin" is the name of the remote repo. You can add an alternative name instead of "origin".

**Pointing Remote Branch**

- `git remote [url] [branch name]`: Points a remote branch to the correct URL.

**Removing Remote Connection**

- `git remote rm [remote repo name]`: Removes the connection to the specified remote repository.

**Renaming Remote Repository**

- `git remote rename [remote repo name] [new name]`: Renames a remote repository.

### Git Fetch Commands

**Retrieving Branches**

- `git fetch [remote repo name]`: Retrieves all branches from the remote repo.

**Retrieving Specific Commits**

- `git fetch [remote repo name] [branch]`: Retrieves all commits on the remote's (origin) specified branch. Use when both local and remote have changes the other does not have.

**Previewing Changes**

- `git fetch --dry-run`: See changes to the remote repo before pulling into the local repo.

### Git Pull Commands

**Pulling Changes**

- `git pull [remote repo]`: Pulls changes from the remote repo to your local repo. It performs a fast-forward merge. An alternative is `git fetch`.

**Pulling Specific Branch**

- `git pull [remote repo]/[branch name]`: Pulls changes from the remote repo branch to your local repo.

**Pulling and Merging**

- `git pull --rebase [remote repo]`: Pulls and merges remote changes into the local repository using rebase.

### Git Push Commands

**Pushing Commits**

- `git push [remote repo] [branch name]`: Pushes commits from the local repo to the remote repo. Example: `git push origin master`.

**Pushing All Branches**

- `git push [remote repo] --all`: Pushes commits from all local branches to the remote repo.

**Pushing Tags**

- `git push [remote repo] --tags`: Sends all of your local tags to the remote repository.

## Inspecting a Repository

### Git Log Commands

**Listing Commits**

- `git shortlog`: Alphabetical list of names and commit messages made by each person.
- `git shortlog -s -n`: Displays the number of commits made next to each person's name.
- `git log`: Shows all commits made. Full history.
- `git log --stat`: Displays names of files changed during the commits.
- `git log --graph`: Visual representation of branches, including commits.
- `git log --graph --oneline`: Condensed visual representation of branches, including commits.
- `git log -n [number]`: Displays the specified number of commits only.
- `git log -p [commit id]` or `git log --patch [commit id]`: Displays changes made to the file(s).
- `git log -p -w`: Ignores whitespace changes.
- `git log -p [file/directory]`: Displays change history of file or directory.
- `git log --author=[name]`: Filter by author name. Show only their commits.
- `git log --author="[full name]"`: Filter by author's full name. Show only their commits.
- `git log --author="[person 1]\|[person 2]"`: Show commits by either person 1 or person 2.
- `git log --grep="Search term"`: Show commits which contain the search term only in the commit message.
- `git log --after="[date]"`: Display commits made after a certain date.
- `git log --before="[date]"`: Display commits made before a certain date.
- `git log --after="[date]" --before="[date]"`: Display commits made after but before a certain date.
- `git log -- [file name 1] [file name 2]`: Display history related to file or files.
- `git log --branches=*`: View commits across all branches.

###

 Git Status Command

- `git status`: Lists which files are staged, unstaged, and untracked.

### Git Show Command

- `git show`: Display changes made in the last commit.
- `git show [commit id]`: Display changes made in a specific commit.
- `git show HEAD`: Show details of the commit HEAD is currently pointing at.

## Using Branches

### Git Branch Commands

**Listing Branches**

- `git branch`: Lists all branches in the repository.
- `git branch [new branch name]`: Creates a new branch.
- `git branch [new branch name] [commit id]`: Creates a new branch and points it to the specified commit.
- `git branch -d [branch name]`: Deletes a branch. Use `-D` to force delete.
- `git branch -m [new name]`: Renames an existing branch.
- `git branch -a`: Lists all remote branches.

### Git Checkout Commands

**Switching Branches**

- `git checkout [branch name]`: Switches to working on another branch.
- `git checkout -b [new branch name]`: Creates a new branch and switches to it.
- `git checkout [commit id]`: Views how files were when the commit was created.
- `git checkout HEAD [filename]`: Restores the file in the working directory to how it is at the last commit.

### Git Merge Command

- `git merge [branch name]`: Merges the specified branch into the receiving branch (where HEAD is currently pointing to).

## Other

### Git Tag Commands

**Displaying Tags**

- `git tag`: Displays all current tags.

**Creating Tags**

- `git tag -a [new tag name]`: Creates a new tag at the current commit.
- `git tag -a [new tag name] [7 digits of commit id]`: Creates a new tag at a previous commit.

**Deleting Tags**

- `git tag -d [tag name]`: Deletes a tag.

### Git Rebase Command

**Interactive Rebase**

- `git rebase -i HEAD~[num]`: Merges a number `[num]` of commits interactively. Creates a new commit id.