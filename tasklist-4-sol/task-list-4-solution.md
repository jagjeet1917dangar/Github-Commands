# ***Task List: Focused on Advanced Git Operations :***
<br></br>

# <ins>**Part 1: Understanding and Using git stash :**</ins>
<br></br>

# Task 1: Save Changes Temporarily with git stash :
## 1. Make changes to a file without committing :
```
echo "Temporary changes" >> temp-file.txt
```
+ It will make the change in file temp-file without committing.

## 2. View the status of changes :
```
git status
```
+ it can show the status of the local repository but in our case it's output will be look like this.
### **Output** :
```
Changes not staged for commit:
modified:   temp-file.txt
```
## 3. Stash the changes :
```
git stash
```
+ ```git stash``` is a Git command used to temporarily save changes that are not yet ready to be committed. It allows you to "stash" your modifications (both staged and unstaged) so you can work on something else, then come back to your changes later.
## 4. View the stashed changes :
```
git stash list
```
+ The command git stash list is used to display a list of all the stashes you have saved. Each stash is shown with a name, such as stash@{0}, stash@{1}, and so on, along with the commit reference and a brief description.
+ ### **Output** :
```
stash@{0}: WIP on main: 27e5f23 Added temporary changes
```
# Task 2: Apply and Drop Stashed Changes :
## 1. Apply the most recent stash :
```
git stash apply
```
+ The command ```git stash apply``` is used to apply the changes from the most recent stash (or a specific stash) back into your working directory, without removing it from the stash list.

## 2. Drop the most recent stash after applying it :
```
git stash drop
```
+ The command git stash drop is used to remove a specific stash from the stash list. It doesn't apply the changes; it simply deletes the stash you specify.
## 3. Alternatively, to apply a specific stash :
```
git stash apply stash@{1}
```
+ The command git stash apply stash@{1} is used to apply the changes from the stash with the identifier stash@{1} to your working directory.
# Task 3: Stash Untracked Files :
## 1. Stash changes, including untracked files :
```
git stash -u
```
+ The command ```git stash -u``` (or ```git stash --include-untracked```) is used to stash not only your tracked changes but also any untracked files in your working directory.
## 2. Apply stashed changes including untracked files :
```
git stash apply
```
+ The command ```git stash apply``` is used to apply the changes from the most recent stash (or a specific stash) to your working directory without removing it from the stash list.
# <ins>**Part 2: Rewriting History with git rebase :**</ins>
<br></br>

# Task 4: Rebase Commits to a New Base :

## 1. Rebase the current branch onto main :
```
git rebase main
```
+ The command ```git rebase main``` is used to rebase the current branch onto the main branch. In simpler terms, it means you're updating your current branch with the latest changes from main, making it as if your branch was created from the current state of main.
## 2. Resolve any conflicts that may arise during rebase, and continue :
```
 git rebase --continue 
``` 
+ The command git rebase main is used to rebase the current branch onto the main branch. In simpler terms, it means you're updating your current branch with the latest changes from main, making it as if your branch was created from the current state of main.
# Task 5: Canceling a Rebase :
## 1. If a rebase goes wrong, abort it :
```
git rebase --abort
```
+ 
The command git rebase --abort is used to stop and undo a rebase operation that is currently in progress, reverting the repository back to the state it was in before the rebase began.
# <ins>**Part 3: Interactive Rebase (```git rebase -i```) :**</ins>
<br></br>

# Task 6: Use Interactive Rebase to Modify Commit History :
# 1. View the last few commits :
```
git log --oneline
```
+ The command ```git log --oneline``` is used to display a simplified, one-line summary of the commit history in your Git repository.
# 2. Start an interactive rebase for the last 3 commits :
```
git rebase -i HEAD~3
```
+ The command git rebase -i HEAD~3 is used to interactively rebase the last 3 commits in your current branch.

+ ```Interactive Rebase``` : The -i flag stands for "interactive," meaning you can choose to modify commits, reorder them, squash them, or drop them during the rebase process.

+ ```HEAD~3``` : This specifies the starting point for the rebase. HEAD~3 means "the commit three steps before the current HEAD," i.e., the last three commits you made in your current branch.
# 3. Modify the commits by changing pick to one of the following :
+ ```squash``` (combine commits)

+ ```reword``` (edit commit message)

+ ```edit```(edit commit content)

+ ```drop``` (remove commit)
# 4. Example of squashing two commits :
+ Change the second commit from pick to squash and save.

+ Git will combine the commit messages for the squashed commit.
# Task 6: Complete Interactive Rebase :
## 1. After modifying the commits, save and close the editor.
## 2. Resolve any conflicts if prompted, then continue the rebase:
```
git rebase --continue
```
+ The command git rebase --continue is used to continue a rebase process after resolving any conflicts during an interactive rebase or a regular rebase.
# <ins>**Part 4: Cherry-Picking Commits (```git cherry-pick```) :**</ins>
<br></br>

# Task 8: Pick a Specific Commit :
## 1. View the commit history to find the commit hash you want to cherry-pick :
```
git log --oneline
```
+ The command ```git log --oneline``` is used to display a simplified, one-line summary of the commit history in your Git repository.

## 2. Cherry-pick a specific commit by its hash :
```
git cherry-pick <commit-hash>
```
+ The command ```git cherry-pick <commit-hash>``` is used to apply a specific commit from one branch onto your current branch. It allows you to bring in a single commit (identified by its commit hash) from another branch into your current working branch.
## 3. Resolve conflicts if any, then commit the changes :
```
git add .
git cherry-pick --continue
```
+ The commands git add . and git cherry-pick --continue are used together during the process of resolving conflicts while performing a git cherry-pick.

# <ins>**Part 5: Tagging Commits (```git tag```) :**</ins>
<br></br>

# Task 9: Tag a Commit :
## 1. Tag the current commit with a version number :
```
git tag -a v1.0 -m "Initial release"
```
+ The command git tag -a v1.0 -m "Initial release" is used to create an annotated tag in Git with the name v1.0 and a message "Initial release".
## 2. List all tags :
```
git tag
```
+ The command git tag is used to list, create, or manage tags in a Git repository. Tags are a way to mark specific points in the Git history, typically used for marking release versions.
# Task 10: Tag a Specific Commit :
## 1. Tag a specific commit by its hash :
```
git tag -a v1.1 <commit-hash> -m "Bug fix"
```
+ The command ```git tag -a v1.1 <commit-hash> -m "Bug fix"``` is used to create an annotated tag named ```v1.1``` on a specific commit identified by ```<commit-hash>```, and it includes a message ```"Bug fix"```.
# Task 11: Push Tags to Remote :
## 1.Push a specific tag to the remote repository :
```
git push origin v1.0
```
+ The command git push origin v1.0 is used to push a specific tag (in this case, v1.0) to a remote repository (typically named origin).
## 2. Push all tags to the remote repository :
```
git push --tags
```
+ The command git push --tags is used to push all local tags to the remote repository.

# <ins>**Part 6: Working with Remote Repositories :**</ins>
<br></br>

# Task 12: Add a Remote Repository :
## 1. Add a remote repository URL to the project :
```
git remote add origin https://github.com/username/repo.git
```
+ 
The command git remote add origin ```https://github.com/username/repo.git``` is used to add a remote repository (called origin) to your local Git repository.
# Task 13: Fetch Changes from Remote :
## 1. Fetch changes from the remote repository without merging them :
```
git fetch origin
```
+ The command ```git fetch origin``` is used to fetch the latest changes from the remote repository (```origin``` in this case) without merging them into your current branch. It downloads new data, such as commits, branches, and tags, from the remote repository, but it does not modify your working directory or automatically merge any changes.
## 2. View fetched branches :
```
git branch -r
```
+ 
The command ```git branch -r``` is used to list remote branches in a Git repository.
# Task 14: Pull Changes from Remote :
## 1. Pull the latest changes from the remote repository and merge them into the local branch :
```
git pull origin main
```
+ The command ```git pull origin main``` is used to fetch changes from the remote repository (origin in this case) and merge them into your local main branch.
# Task 15: Push Changes to Remote :
## 1. Push local changes to the remote repository :
```
git push origin main
```
+ The command git push origin main is used to push changes from your local main branch to the remote repository (origin).
## 2. Push a new branch to the remote repository :
```
git push origin feature-branch
```
+ The command ```git push origin feature-branch``` is used to push your local branch (in this case, feature-branch) to the remote repository (origin), making it available to others.
# Task 16: Delete Remote Branch :
## 1. Delete a remote branch :
```
git push origin --delete feature-branch
```
+ The command git push origin --delete feature-branch is used to delete a branch from the remote repository (origin in this case).

# <ins>**Part 7: Forking and Contributing to Open-Source Projects :**</ins>
<br></br>

# Task 17: Fork a Repository on GitHub :
## 1. Go to a repository on GitHub and click Fork in the top right corner to create your own copy of the repository.
## 2. Clone the forked repository to your local machine:
```
git clone https://github.com/your-username/repo.git
```
+ The command ```git clone https://github.com/your-username/repo.git``` is used to create a local copy of a remote repository. It downloads the repository from the specified URL to your local machine and initializes it as a Git repository.
# Task 18: Make Changes and Commit :
## 1. Create a new branch for your changes :
```
git checkout -b fix-typo
```
+ The command git checkout -b fix-typo is used to create a new branch named fix-typo and switch to it immediately.
## 2. Make changes to the code (e.g., fix a typo in README.md), stage, and commit them :
```
git add README.md
git commit -m "Fixed typo in README.md"
```
1. ```git add README.md``` :
This stages the changes made to the README.md file. It tells Git to include this file in the next commit.

2. ```git commit -m "Fixed typo in README.md"``` :
This creates a commit with the staged changes. The -m flag allows you to include a commit message directly, in this case, "Fixed typo in README.md."
# Task 19: Push Changes to Your Fork :
## 1. Push the changes to your remote fork :
```
git push origin fix-typo
```
# Task 20: Create a Pull Request :
## 1. Go to your forked repository on GitHub, click on Compare & Pull Request.

## 2. Write a description of your changes and submit the pull request to the original repository.
# Task 21: Sync Your Fork with the Original Repository :
## 1. Add the original repository as a remote source :
```
git remote add upstream https://github.com/original-owner/repo.g
```
+ This sets up a connection to the original repository (referred to as upstream). You would typically use this in a forked repository to pull updates from the original repo.
## 2. Fetch changes from the original repository :
```
git fetch upstream
```
+ **Fetch Updates** :
It downloads all the changes (commits, branches, and tags) from the upstream remote repository.

+ **No Merge** :
The changes are not applied to your working directory or current branch. They are stored in your local repository under the upstream remote references.
## 3. Merge changes from the original repository into your local branch:
```
git checkout main
git merge upstream/main
```
+ The commands ```git checkout main``` and ```git merge upstream/main``` update your local ```main``` branch with the latest changes from the original repository (```upstream```). First, ```git checkout main``` switches to your ```main``` branch. Then, ```git merge upstream/main``` merges the latest updates from ```upstream/main``` (fetched earlier using ```git fetch upstream```) into your branch. This process ensures your local branch is synchronized with the original repository, incorporating any new changes or updates. If there are conflicts, you'll need to resolve them before completing the merge.
## 4. Push the changes to your fork :
```
git push origin main
```
+ The command ```git push origin main``` uploads the changes from your local ```main``` branch to the remote repository named ```origin```.
# **Consolidated Summary :**
## 1. **Stashing** : Saving and applying uncommitted changes temporarily.

## 2. **Rewriting History :**  Using git rebase and interactive rebase to modify and clean up commit history.

## 3. **Cherry-Picking :** Selecting specific commits from another branch.

## 4. **Tagging :** Labeling commits for versioning.

## 5. **Working with Remote Repositories :** Managing remotes, pushing, pulling, and fetching changes.

## 6. **Working with Remote Repositories :** Managing remotes, pushing, pulling, and fetching changes.







































































































































































