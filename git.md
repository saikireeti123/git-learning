## GIT 
Git is an open source  distributed version control system.
It is used to track the changes in the source code during software development.
It is designed to handle everything from small to very large projects with speed and efficiency.
It allows multiple developers to work on the same project simultaneously without overwriting each other's changes.

### Basic Git Commands
- `git init`: Initializes a new Git repository.
- `git clone <repository_url>`: Clones an existing repository from a remote server.
- `git add <file_name>`: Stages changes for the next commit.
- `git commit -m "commit message"`: Commits the staged changes with a descriptive message.
- `git status`: Displays the status of the working directory and staging area.
- `git push`: Pushes the committed changes to a remote repository.
- `git pull`: Fetches and merges changes from a remote repository to the local repository.
- `git branch`: Lists all branches in the repository.
- `git checkout <branch_name>`: Switches to the specified branch.
- `git merge <branch_name>`: Merges the specified branch into the current branch.
- `git log`: Displays the commit history for the repository.
- `git diff`: Shows the differences between the working directory and the staging area or between commits.
- `git remote -v`: Lists the remote repositories associated with the local repository.
- `git fetch`: Downloads objects and refs from another repository.
- `git reset <file_name>`: Unstages the specified file.
- `git rm <file_name>`: Removes the specified file from the working directory and stages the removal for the next commit.
- `git restore <file_name>`: Discards changes in the working directory.
- `git stash`: Temporarily saves changes that are not ready to be committed.
- `git stash pop`: Applies the most recent stash and removes it from the stash list.
- `git stash list`: Lists all stashes.
- `git stash apply <stash_id>`: Applies a specific stash without removing it from the stash list.
- `git tag <tag_name>`: Creates a tag for the current commit.
- `git show <commit_id>`: Displays detailed information about a specific commit.
- `git reflog`: shows the history of all the changes made in the repository including the commits that are not reachable from any branch.

## git branching strategies
- **Git Flow**: A branching model that defines a strict branching structure for managing feature, development,release,hot fixes and master branches.
- 
- **GitHub Flow**: It is a simple branching strategy that involves creating a new branch from master to develop any feature or fix any bug and merge them into the master branch by raising the pull request.

**main only strategies**: in this strategies we only have main branch and all the changes are directly made in the main branch and deployed to production.

**Feature branching strategies**:
It is used to develop very feature on its on own branch and merged into  develop branch after the completion of the feature.

**Trunked based development**:
In this strategies the developer create a branch from the main branch and work on the feature and merge it back to the main branch frequently to avoid the merge conflicts.

**Release branching strategies**:
In the this branching strategies the release branch is created from the develop branch when the develop branch is stable with the completion all tests to release the code to production.

## git merge:
git merge is the concept that combines the one branch into another branch by raising the pr.
in the merge concept we have three ways to merge them 
1. fast forward merge: it is the concept that directly moves the pointer of the target branch to the latest commit of the source branch
example:
```git merge feature-branch
```
2. Non fast forward: it is the concept that creates a new commit in the target branch that combines the changes from both branches.
   example:
```git merge --no-ff feature-branch
3.merge conflict:it occurs when the two developers changes same line the same file in their branches try to merge them into main branch or develop branch.
    example:
    ```git merge feature-branch
    ```
In the above example if both the developers changes same line in the same file then it will show the merge conflict and we have to resolve them manually by editing the file and removing the conflict markers and then stage the file and commit it.   

## git rebase:
git rebase is the concept that reapplies the commits on the tip of the latest commit of the target branch.it is used to showcase the linear history .
it is of two types
1. interactive rebase: it is used to edit,delete,squash or reword the commits.
   example:
```git rebase -i HEAD~3
```
2. non interactive rebase: it is used to reapply the commits on the tip of the latest commit of the target branch.
example:
```git rebase main
``` 


# git squash:
It is the concept that combines the multiple commits into single commit to make the history clean and in the linear structure.It is done by the interactive rebase method.
Example:
```git rebase -i HEAD~3
```
In the above command HEAD~3 means last three commits will be shown to squash.
In the interactive mode we can see the list of commits with the pick option in front of them.we can change the pick option to squash or s to combine the commits.
After saving and closing the editor it will show another editor to edit the commit message for the squashed commit.we can edit the message or keep it as it is and save and close the editor to complete the squash process.

## git cherry-pick:
it is the concept that applies the changes when we need pick a specific commit to add to the current branch. By using commit id.
example:
```git cherry-pick <commit_id>
```

## git revert:
it is the concept that creates a new commit that undoes the changes made in a specific commit
example:
```git revert <commit_id>
```
it is used to undo the changes in a commit without modifying the commit history.

  



