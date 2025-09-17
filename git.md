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
It is used to develop very feature on its on own branch and all the changes related to that feature are made in that branch and merged into  develop branch after the completion of the feature.

**Trunked based development**:
In this branching strategy we have only one branch called trunk or main branch and all the developers directly commit their changes to the main branch and deploy to production.

**Release branching strategies**:
In this branching strategy we have a separate branch for each release and all the changes are made in the release branch and merged into the main branch after the completion of the release.

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
```
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

  


## GIT REAL WORLD SCENARIO BASE QUESTIONS AND ANSWERS FOR INTERVIEW PREARATION AS 2 YEARS EXPERIENCE
1. What is Git and why is it used in software development?
   ANS: Git is a distributed version control system that allows multiple developers to collaborate on a project by tracking changes in the source code. It helps manage code versions, facilitates collaboration, and enables easy rollback to previous states if needed.

2. Explain the difference between Git and other version control systems like SVN or Mercurial.
ANS: Git is a distributed version control system, meaning each developer has a complete copy of the repository, allowing for offline work and faster operations. In contrast, SVN and Mercurial are centralized systems where developers rely on a central server for version control, which can lead to bottlenecks and limited offline capabilities.

3. What are the main components of a Git repository? 
ANS: The main components of a Git repository include the working directory (where files are edited), the staging area (where changes are prepared for commit), and the .git directory (which contains all the metadata and history of the repository).

4. How do you initialize a new Git repository?
ANS: To initialize a new Git repository, navigate to the desired project directory in the terminal and run the command `git init`. This creates a new .git directory, setting up the repository for version control.

5. What is the difference between `git clone` and `git fork`?
 ANS: `git clone` creates a local copy of an existing repository, allowing you to work on it locally. `git fork`, on the other hand, is a feature provided by platforms like GitHub that creates a personal copy of someone else's repository under your account, enabling you to make changes without affecting the original repository.

6. How do you stage changes for a commit in Git?
   ANS: To stage changes for a commit in Git, use the command `git add <file>` to add specific files or `git add .` to stage all changes in the working directory. This prepares the changes for the next commit.

7. What is the purpose of the `.gitignore` file?
   ANS: The `.gitignore` file is used to specify files and directories that should be ignored by Git. This is useful for excluding temporary files, build artifacts, and other files that should not be tracked in the repository.

8. How do you create a new branch in Git?
   ANS: To create a new branch in Git, use the command `git branch <branch_name>`. To switch to the new branch, use `git checkout <branch_name>`. Alternatively, you can create and switch to a new branch in one command using `git checkout -b <branch_name>`.

9. What is the difference between `git merge` and `git rebase`?
   ANS: `git merge` combines changes from one branch into another, creating a new merge commit. `git rebase`, on the other hand, moves or combines a sequence of commits to a new base commit, resulting in a linear commit history without merge commits.

10. How do you resolve merge conflicts in Git?
 ANS: To resolve merge conflicts in Git, first identify the files with conflicts using `git status`. Open the conflicted files and look for conflict markers (e.g., `<<<<<<<`, `=======`, `>>>>>>>`). Manually edit the files to resolve the conflicts, then stage the resolved files using `git add <file>`. Finally, complete the merge by committing the changes with `git commit`.
11. What is the difference between a fast-forward merge and a three-way merge?  
    ANS: A fast-forward merge occurs when the target branch is directly ahead of the source branch, allowing Git to simply move the pointer of the target branch to the latest commit of the source branch without creating a new commit. 
    A three-way merge, on the other hand, is used when both branches have diverged, requiring Git to create a new merge commit that combines the changes from both branches.
12. How do you view the commit history in Git?
 ANS: To view the commit history in Git, use the command `git log`. This displays a list of commits along with their commit IDs, authors, dates, and commit messages. You can also use options like `git log --oneline` for a more concise view or `git log --graph` to visualize the branch structure.
    
13. What is the purpose of `git stash` and how do you use it?
 ANS: `git stash` is used to temporarily save changes in the working directory that are not ready to be committed. This allows you to switch branches or perform other operations without losing your uncommitted changes. To stash changes, use `git stash`. To apply the stashed changes later, use `git stash apply` or `git stash pop` (which applies and removes the stash).
14. How do you revert a commit in Git?
 ANS: To revert a commit in Git, use the command `git revert <commit_id>`. This creates a new commit that undoes the changes made in the specified commit without modifying the commit history. If you want to undo multiple commits, you can specify a range of commits or use interactive rebase.
15. What is the difference between `git reset` and `git revert`?
   ANS: `git reset` is used to move the current branch pointer to a specific commit, effectively removing commits from the history. It can be used with different options (soft, mixed, hard) to control how changes are handled in the working directory and staging area. `git revert`, on the other hand, creates a new commit that undoes the changes of a specific commit without altering the commit history.
16. How do you handle large binary files in a Git repository?
   ANS: To handle large binary files in a Git repository, you can use Git Large File Storage (LFS). Git LFS replaces large files with text pointers in the repository, while the actual file content is stored on a separate server. To use Git LFS, install it and run `git lfs track <file_pattern>` to specify which files to manage with LFS. Then, commit and push the changes as usual.
17. What are some best practices for using Git in a team environment?
 ANS: Some best practices for using Git in a team environment include:
   - Use descriptive commit messages to provide context for changes.
   - Create feature branches for new features or bug fixes to keep the main branch stable.
   - Regularly pull changes from the main branch to keep your branch up to date.
   - Review and test code before merging it into the main branch.
   - Use pull requests for code reviews and collaboration.
   - Avoid committing large binary files directly to the repository; use Git LFS instead.
   - Keep the commit history clean by squashing unnecessary commits before merging.
   - Communicate with team members about changes and coordinate merges to avoid conflicts.
   - Regularly back up the repository to prevent data loss.
   - Document the branching strategy and workflow used by the team to ensure consistency.
   - Encourage the use of `.gitignore` to exclude unnecessary files from being tracked.
   - 
18. How do you handle code reviews and pull requests in Git?
. ANS: Code reviews and pull requests in Git are typically handled through platforms like GitHub, GitLab, or Bitbucket. When a developer completes a feature or bug fix, they create a pull request (PR) from their feature branch to the main branch. Team members can then review the code changes, leave comments, suggest improvements, and approve or request changes. Once the PR is approved, it can be merged into the main branch, often using a merge commit or squashing commits for a cleaner history.

19. What is the purpose of `git bisect` and how do you use it?      
. ANS: `git bisect` is a tool used to find the specific commit that introduced a bug or issue in the codebase. It uses a binary search algorithm to efficiently narrow down the range of commits. To use `git bisect`, start by running `git bisect start`, then mark a known good commit with `git bisect good <commit_id>` and a known bad commit with `git bisect bad <commit_id>`. Git will then check out a commit in the middle of the range, and you can test it to see if the issue is present. Based on the result, you mark it as good or bad, and Git will continue to narrow down the range until it finds the problematic commit. Once done, run `git bisect reset` to return to the original branch.

20. How do you manage and resolve conflicts when multiple developers are working on the same codebase?
 ANS: To manage and resolve conflicts when multiple developers are working on the same code base, follow these steps:
   - Communicate with team members to coordinate changes and avoid overlapping work.
   - Regularly pull changes from the main branch to keep your local branch up to date.
   - When a conflict occurs during a merge or rebase, use `git status` to identify the conflicted files.
   - Open the conflicted files and look for conflict markers (e.g., `<<<<<<<`, `=======`, `>>>>>>>`). Manually edit the files to resolve the conflicts by choosing which changes to keep or combining them as needed.
   - After resolving the conflicts, stage the resolved files using `git add <file>`.
   - Complete the merge or rebase process by committing the changes with `git commit` (if merging) or continuing the rebase with `git rebase --continue`.
   - Test the code thoroughly to ensure that the resolved changes work as expected.
   - Consider using code reviews and pull requests to catch potential conflicts early and ensure code quality.
   - Document the resolution process and communicate with the team to prevent similar conflicts in the future.
- 
-  21. How do you optimize Git performance for large repositories?
   ANS: To optimize Git performance for large repositories, consider the following strategies:
    - Use Git LFS (Large File Storage) to manage large binary files, reducing the size of the repository.
    - Regularly clean up the repository by removing unnecessary branches and tags.
    - Use shallow clones (`git clone --depth <depth>`) to limit the history depth when cloning large repositories.
    - Compress the repository using `git gc` (garbage collection) to optimize storage and improve performance.
    - Avoid committing large files directly to the repository; instead, use external storage solutions.
    - Split large repositories into smaller, more manageable sub-repositories if possible.  
    - Use `.gitignore` to exclude unnecessary files and directories from being tracked.
    - Monitor and analyze repository performance using tools like `git-sizer` to identify potential issues
    - Educate team members on best practices for using Git to prevent performance degradation.
    - 
22.   How do you handle versioning and releases in Git?
   ANS: To handle versioning and releases in Git, follow these practices:
   - Use semantic versioning (e.g., v1.0.0) to clearly indicate the version of the software.
   - Create a dedicated branch for releases (e.g., `release` or `main`) to keep it stable and production-ready.
   - Use tags to mark specific commits as release points (e.g., `git tag v1.0.0`).
   - Create release branches for preparing new versions, allowing for final testing and bug fixes before merging into the main branch.
   - Document changes in a changelog to provide context for each release.
   - Automate the release process using CI/CD pipelines to ensure consistency and reduce manual errors.
   - Communicate with the team about upcoming releases and coordinate deployment activities.
   - Regularly review and update the versioning strategy to align with project needs and team workflows.

23.  How do you back up and restore a Git repository?
   ANS: To back up a Git repository, you can simply clone the repository to another location using `git clone <repository_url>`. Additionally, you can create a bare repository using `git clone --bare <repository_url>` to have a complete copy of the repository without a working directory. For more robust backups, consider using remote hosting services like GitHub, GitLab, or Bitbucket, which provide built-in backup and redundancy features. To restore a Git repository, you can clone the backup repository to your desired location using `git clone<backup_repository_url>`. If you have a bare repository, you can create a new working directory by cloning it as a regular repository. Always ensure that you have multiple backups in different locations to prevent data loss.


