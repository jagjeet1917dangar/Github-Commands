#  Part-1 : Introduction to Version Control and Git
# task-1: Introduction to Version Control and Git
# 1.Configure Git with your username and email:
```
git config --global user.name "Jagjeet Dangar"

git config --global user.email "jagjeet.dangar.cg@gmail.com"
```

## what it does:
### 1.it sets your name globally:
It sets the name you want Git to associate with your commits across all repositories on your machine. This name appears in the "Author" field of commit metadata.
### 2.Global Setting:
The --global flag ensures the name is applied universally to all Git projects on your system. If you omit --global, the configuration applies only to the current repository.
### 3.Example Use in Commits:
When you make a commit, Git uses this name along with your email (configured with git config --global user.email) to tag the commit. For instance:
# 2.View your Git configuration:

```
**git config --list**
```
## what it does:
### Displays All Git Configurations:

+ This command lists all Git configuration settings currently in effect for your system.

+ It shows settings from three levels:

1. System Level (/etc/gitconfig): Global for all users on the system.

2. Global Level (~/.gitconfig or ~/.config/git/config): Applies to the current user across all repositories.

3. Local Level (.git/config in the repository): Specific to the current Git repository.

# task-2:  Initialize a Repository
# 1.Create a new project folder and navigate to it:
```
mkdir MyProject
```
## what it does:
### Creates a directory:
+ The mkdir command stands for "make directory."

+ It creates a new directory (folder) named myproject in the current working directory.
```
cd MyProject
```
## what it does:
### Changes the Current Directory:
+ The cd command stands for "change directory."

+ This moves you into the myproject directory (a folder) that you created earlier using mkdir myproject.

# 2.Initialize it as a Git repository:
```
git init
```
## what it does:
### Initializes a empty Git Repository:
+ This command sets up a new Git repository in the current directory.

+ It creates a hidden .git folder, which contains all the metadata and version history for the repository.
# task-3: Create a File and Make Multiple Commits:
# 1.Create a new file and add content:
```
echo "My First Project" > README.md
```
## what it does:
### Writes Text to a File:
+ The echo command outputs the text "My First Project".

+ The > operator redirects this output into a file named README.md.

+ If the file README.md doesn’t exist, it is created. If it already exists, its contents are overwritten.
# 2.Stage the file:
```
git add README.md
```
## what it does:
### Stages the File:
+ Adds the file README.md to the staging area in Git.

+ The staging area is where changes are prepared for a commit.
# 3. Commit the file:
```
git commit -m "Initial commit: Added README.md"
```
## what it does:
### Commits Changes to the Repository:
+ The git commit command saves the changes in the staging area (files added with git add) to the Git repository..

+ This message helps document what changes were made in the commit.
# 4. Make changes to the file:
```
echo "Added a description" >> README.md
```
## what it does:
### Appends Text to a File:
+ The echo command outputs the text "Added a description".

+ The >> operator appends this text to the end of the file README.md without overwriting its existing content.
# 5.Stage and commit the changes:
```
git add README.md
git commit -m "Updated README with a description"
```
## what it does:
### Adds a file and adds a commit to the staging area:
+ This will add the README file to the staging area and then it will commmit to the staging area with the message which we have written.
# Task-4:Check Status and Log:
# 1.Check the repository's current status:
```
git status
```
## what it does:
### Shows the Current State of the Repository:
+ It provides detailed information about the status of the working directory and staging area.

+ It shows:

Untracked files: Files that are new or not added to the Git repository yet.

Changes not staged for commit: Files that have been modified but not added to the staging area.

Changes to be committed: Files that have been staged and are ready to be committed.
# 2.View commit history in detail:
```
git log --oneline --graph --decorate
```
## what it does:
### 1. ```git log:```
+ Displays the commit history of the current branch.
### 2. ```--oneline:```
+ Shows each commit on a single line, simplifying the log output.

+ It displays the commit hash (shortened) and the commit message, making it easier to view multiple commits at once.
### 3. ```--graph:```

+ Displays a graphical representation of the commit history in a branching structure.

+ It shows how branches and merges relate to each other by using ASCII characters (like |, *, /, etc.).
### 4. ```--decorate:```

+  Shows references (like branches and tags) associated with commits.

### Example Output :
```
* 2f8d6a2 (HEAD -> main) Updated README with a description
* d3c4b21 Initial commit: Added README.md
```
# Task 5: Create and Clone a Repository:
# 1. Create a repository on GitHub named example-repo.
+ Create a repository in github named example-repo.
# 2. Clone it locally:
```
git clone http://codinggita.com/example-repo
```
- The command git clone http://codinggita.com/example-repo is used to create a local copy of a Git repository from a remote URL. Here's a breakdown of the command:

- ```git clone:``` This is the Git command used to create a local copy of a remote repository.

- ```http://codinggita.com/example-repo:``` This is the URL of the repository you want to clone. In this case, it's a repository hosted at codinggita.com.
# Task 6: Understanding the Git Workflow:
## Example Overflow :
### i.Make changes to a file in the working directory:
```
echo "Workflow example" > workflow.md
```
+ it will edit the file means it will append in file.
### ii.Stage the file :
```
git add workflow.md
```
+ it will add the file to the staging area.
### iii.Commit the file to the repository :
```
git commit -m "Added workflow example"
```
+ it will commit the message to the staging area.
# Part 2 : Working with Repositories :
# Task 7: Branching and Merging
## 1. Create a new branch for a feature :
```
git branch feature-login
git checkout feature-login
```
## what it does:
### 1. ```git branch feature-login```:
+ This creates a new branch named feature-login.
### 2. ```git checkout feature-login```:
+ This switches to the feature-login branch, making it the active brnahc for further work.
## or :
```
git checkout -b feature-login
```
+ This command can directly create a branch and can directly switch to branch.
## 2. Add a new file and commit changes :
```
echo "Login Page" > login.html
git add login.html
git commit -m "Added login page"
```
## what it does:
### 1. ```echo "Login Page" > login.html```
+ This creates a file named login.html with the content "Login Page".
### 2. ```git add login.html```
+ This stages the login.html file, preparing it to be committed to the Git repository.
### 3. ```git commit -m "Added login page"```
+ This commits the staged file to the repository with the message "Added login page".
## 3. Merge the feature branch into ```main```:
```
git checkout main
git merge feature-login
```
## what it does:
### 1. ```git checkout main``` :
+ This switches to the main branch, which is the branch you want to merge changes into.

### 2. ```git merge feature-login``` :
+ This merges the feature-login branch into the main branch, bringing in the changes you made in feature-login.
# Task-8 : Handling Merge Conflicts : 
## 1. Create two branches : 
```
git branch branch-A
git branch branch-B
```
### 1. ```git branch branch-A``` :
+  This creates a new branch named branch-A but does not switch to it.
### 2. ```git branch branch-B``` :
+   This creates another new branch named branch-B but does not switch to it either.
## 2. Modify the same line in  ```README.md``` in both branches.
## 3. Merge ```branch-A``` into ```main``` :
```
git checkout main
git merge branch-A
```
## what it does :
### 1. ```git checkout main``` :
+  Switches your working directory to the main branch. If you're not already on the main branch, this ensures that main is the branch into which the changes will be merged.
### 2. ```git merge brnach-A``` :
+  Merges the changes from branch-A into the main branch. Git will attempt to combine the changes from branch-A with those in main.
## 4. Attempt to merge branch-B into main:
```
git merge branch-B
```
### Command Overview :
+ git merge branch-B: Merges the changes from branch-B into the main branch.
## 5. Resolve the conflict manually in README.md, then:
```
git add README.md
git commit -m "Resolved merge conflict between branch-A and branch-B"
```
## what it does :
### 1. ```git add README.md```
+ After resolving the merge conflict in the README.md file, this command stages the resolved file, marking it as ready to be included in the next commit. This tells Git that the conflicts in this file have been resolved.
### 2. ```git commit -m "Resolved merge conflict between branch-A and branch-B"```
+ Creates a new commit with the message "Resolved merge conflict between branch-A and branch-B". This commit finalizes the merge process and includes the resolved changes.
# Task-9 : Renaming and Deleting Branches :
## 1. Rename a branch :
```
git branch -m old-branch-name new-branch-name
```
## what it does :
### 1. ```git branch``` :
+ Command for branch operations.
### 2. ```-m``` :
+ Stands for "move" and is used to rename a branch.
### 3. ```old-branch-name``` :
+ The current name of the branch you want to rename.
### 4. ```new-branch-name``` :
+  The new name you want to give to the branch.
## 2.Delete a branch :
```
git branch -d feature-login
```
## what it does :
### 1. ```git branch``` :
+ The command for managing branches.
### 2. ```-d``` :
+  Stands for "delete" and removes the branch only if it has been fully merged into the branch you're currently on.
# Part-3 : Advanced Git Options :
# Task 10 : Using Git Stash :
# 1. Make changes to a file but don't commit :
```
echo "Temporary work" >> temp.md
```
## what it does :
+ It will create a md file with a text "Temporary work" in it.   

# 2.Stash the changes :
```
git stash
```
## what it does :
+ ```git stash``` is a command in Git used to temporarily save changes in your working directory without committing them. This allows you to switch branches or work on something else without losing or committing your incomplete work.
# 3.View stashed changes :
```
git stash list
```
+ The command ```git stash``` list displays a list of all stashed changes in your repository. Each stash entry is shown with an identifier and a brief description.
# 4.Apply the stashed changes:
```
git stash apply
```
## what it does :
+ The ```git stash apply``` command is used to apply the changes stored in a stash back to your working directory. This lets you restore your saved changes without removing them from the stash list.
# 5. Drop the stash after applying:
```
git stash drop
```
+ The ```git stash``` drop command is used to remove a specific stash from the stash list in Git. This is useful when you no longer need a particular stash and want to clean up the list of stashes.

# Task 11: Rewriting History with Interactive Rebase
# 1. Create multiple commits :
```
echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
```
## what it does :
+ These commands create three files (```file1.txt```, ```file2.txt```, ```file3.txt```), each with unique content (Commit 1, Commit 2, Commit 3). Each file is added to the Git staging area and committed with corresponding messages. The result is three separate commits in the repository, each reflecting the addition of a new file.
# 2. Squash commits into one :
```
git rebase -i HEAD~3
```
+ The command git rebase -i HEAD~3 is used to interactively rebase the last three commits in your Git history. Here's what it does:

+ ```-i``` (interactive): Opens an editor to let you edit, reorder, squash, or drop commits.

+ ```HEAD~3```: Specifies the range, meaning the last three commits from the current branch.
+ if we write 5 in HEAD instead of 3 then we can edit last 5 commit instead of 3.means we can chane it with any number.
# Task 12: Cherry-Picking Commits :
## 1.Create a new branch :
```
git checkout -b cherry-pick-example
```
+ it will create a new branch and also switches to it.
## 2.Cherry-pick a specific commit from another branch :
```
git cherry-pick <commit-hash>
```
+ The ```command git cherry-pick <commit-hash>``` applies the changes from a specific commit (identified by ```commit-hash```) onto your current branch. Here's how it works:

1. ```<commit-hash>```: The unique identifier of the commit you want to pick.

2. **Result** : Git creates a new commit in the current branch with the same changes as the specified commit, preserving its content but with a new hash.

# Task 13: Tagging Commits :

## 1. Tag the current commit :
```
git tag -a v1.0 -m "Version 1.0 release"
```
The command ```git tag -a v1.0 -m "Version 1.0 release"``` creates an annotated tag in Git. Here's what it does :

1. ```-a v1.0``` : Creates a tag named v1.0.

2. ```-m "Version 1.0 release"``` : Adds a message to the tag, describing its purpose or significance (similar to a commit message).

## 2. Push the tag to the remote repository :
```
git push origin v1.0
```
1. ```origin``` : Refers to the remote repository's default name.

2. ```v1.0``` : Specifies the tag you want to push.
# Task 14 : Working with Remote Repositories :
# 1. Add a remote repository :
```
git remote add origin <repository-url>
```
## what it does :
+ The command git remote add origin ```repository-url``` is used to link your local Git repository to a remote repository, typically hosted on platforms like GitHub, GitLab, or Bitbucket. Here's what each part does:
# 2. Push your changes to the remote repository :
```
git push origin main
```
+ The command ```git push origin main``` is used to upload the commits from your local ```main``` branch to the ```main``` branch of the remote repository (typically the one named ```origin```).
# Task 15: Forking and Contributing :
# 1. Fork a repository on GitHub :
# 2. Clone the fork locally :
```
git clone <forked-repo-url>
```
+ The command git clone ```forked-repo-url``` is used to create a local copy of a remote repository on your machine. If you have forked a repository (e.g., on GitHub), this command allows you to clone the forked version to work on it locally.
# 3. Create a new branch, make changes, and push : 
```
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git add README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
## **Commands and Explanations :**
### 1. ```git checkout -b fix-typo``` :
+ Creates a new branch named fix-typo and switches to it.

+ This is useful when you want to make changes without affecting the main branch.
### 2. ```echo "Typo fixed" >> README.md``` :
+ Appends the text Typo fixed to the file README.md.

+ If the file doesn't exist, it will be created.
### 3. ```git add README.md``` :
+ Stages the changes made to README.md, preparing it for the next commit.
### 4. ```git commit -m "Fixed a typo``` :
+ Commits the staged changes with the message "Fixed a typo".

+ The commit message should ideally describe the purpose of the change.
### 5. ```git push origin fix-typo``` :
+ Pushes the fix-typo branch to the remote repository (origin).
+ This makes your changes available for collaboration or review.
# 4.Open a pull request on GitHub :

# Part 4: Additional Practice :
# Task 16: Simulate Team Collaboration :
1. Create a repository and share it with a friend.
2. Both make changes to the same file simultaneously.
3. Practice resolving merge conflicts and pushing changes.
# Task 17: Git Ignore :
# 1. Create a ```.gitignore``` file :
```
echo "node_modules/" > .gitignore
```
+ The command echo "node_modules/" > .gitignore is used to create (or overwrite) a .gitignore file and add the entry node_modules/ to it. Here's what it does:
### **Command Breakdown :**
+ ```echo "node_modules/"```: Outputs the text node_modules/.

+ ```>```: Redirects the output to the file .gitignore, overwriting any existing content.

+ ```.gitignore``` : A special file used by Git to specify files or directories that should be ignored by version control.
# 2.Add files and ensure ignored files are not staged :
```
git add .
```
+ adds the file to the staging area.

































