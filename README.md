# Git
Mastering

-------------------------------------*Check and remove remote*-----------------------------------

# Check Remote Origin
To check the current remote origin of your Git repository, use the following command:

# bash
git remote -v
# Updating Remote Repository URL

If you need to change the remote URL for your Git repository, follow these steps:

1. View existing remotes:
    ```bash
    git remote -v
    ```

2. Remove the existing remote (replace `<remote-name>` with the actual remote name, e.g., "origin"):
    ```bash
    git remote remove <remote-name> 
    ```

3. Add a new remote (replace `<new-remote-name>` and `<new-remote-url>` with the desired remote name and URL):
    ```bash
    git remote add <new-remote-name> <new-remote-url>
    ```

4. Verify the changes:
    ```bash
    git remote -v
    ```

-------------------------------------*Simple steps to Upload project*-----------------------------------


## Basic Steps to Upload Project or Files into GitHub

1. Initialize a new Git repository:
    ```bash
    git init
    ```

2. Add all files to the staging area:
    ```bash
    git add .
    ```

3. Commit the changes:
    ```bash
    git commit -m "Add existing project files to Git"
    ```

4. Add a remote named 'origin' with the URL of your GitHub repository:
    ```bash
    git remote add origin https://github.com/cameronmcnz/example-website.git
    ```

-------------------------------------*Change The Branch*-----------------------------------

## If You Want to Change Branch from 'master' to 'main' or 'main' to 'master'

1. Check the Current Branch:
    ```bash
    git branch
    ```

2. Switch to Main Branch (if needed):
    ```bash
    git checkout main
    ```

3. Rename the Local Branch (change the local branch):
    ```bash
    git branch -m master main
    ```

4. Push the changes to the remote repository:
    ```bash
    git push -u origin main or git push -u origin master
    ```

5. Push the changes to the 'main' branch on GitHub:
    ```bash
    git push -u origin main
    ```

-------------------------------------*Undo Recent Commits*-----------------------------------
## Undoing Recent Commits and Removing Changes

If you want to undo recent commits and remove changes, follow these steps:

### Scenario 1: Files not pushed to the remote repository

If the changes have not been pushed to a remote repository, use the following commands:

1. Undo the Last Commit (Soft Reset), Unstage Changes, and Remove Untracked Files:
    ```bash
    git reset --soft HEAD^
    git reset --mixed
    git clean -fd
    ```

### Scenario 2: Files already pushed to the remote repository

If the changes have been pushed to a remote repository and you're certain no one else has pulled these changes, use the following commands:

1. Undo the Last Commit (Soft Reset) and Force Push the Changes:
    ```bash
    git reset --soft HEAD^
    git push -f origin branch-name
    ```
    Replace `branch-name` with the name of your branch. Be cautious with force pushes, as they rewrite the commit history.

Always communicate with your team before making such changes, especially if you're collaborating with others. Additionally, be careful with the `git clean` command, as it permanently removes untracked files. Use it only if you are sure you want to discard those files.