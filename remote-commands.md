## Commands for Remotes

   ```

   1. List all your remote repositories and show their URLs:
   
   > origin  https://github.com/zanut/git-commands.git (fetch)
   > origin  https://github.com/zanut/git-commands.git (push)

   ```
   ```
   2. View details about a remote repo named `origin`, including all the remote branches and local tracking branches for `origin`:
   > git remote show origin
   > git branch -rvv 
   ```
   ```
   3. (Pushing a new branch) You commit some files to the `dev-foo` branch and try to "push" them to Github, but it fails as shown here:

   > git push origin dev-foo
   
   > error: src refspec dev-foo does not match any
   > error: failed to push some refs to 'https://github.com/zanut/git-commands.git'
   ```
   cmd>  git checkout dev-foo  
   cmd>  git push  
   fatal:  The current branch dev-foo has no upstream branch. 
   ```
   Explain this error.
   > The branch name dev-foo doesn't exist yet, so when we use git checkout, we can't go to an unexisting branch.
   
   4. The command to push `dev-foo` to `origin` as a **new remote branch** on `origin` is:
   > git push origin dev-foo:dev-foo

   5. (Create a local tracking branch for a remote branch) The remote repository (`origin`) has a branch named `e2e-test` that you don't have in your local repository.   
   The command to create a new local branch as a copy of the remote `e2e-test` branch that **tracks** the remote branch is:
   > git checkout -b e2e-test origin/e2e-test

   ```
   ```

   6. The command to change the URL of the remote "origin" to a new URL, such as `https://hostname/newuser/new-repo-name`, is:
   > git remote set-url origin https://hostname/newuser/new-repo-name

   ```
   ```
   This situation occurs when:
   - you change the name of a repo on Github
   - you transfer ownership of a Github repo to someone else
   - you move from Github to another hosting site, like Bitbucket
   - you want to switch from the https to the ssh protocol (the remote URL is different)    

   8. To create a *second* remote repository for your local repo, the command to add a remote named "bitbucket" with the URL "https://bitbucket.org/your-username/git-commands" is:
   > git remote add bitbucket https://bitbucket.org/your-username/git-commands

   ```
   ```
   - Note: you must **create** an empty repo on Bitbucket. This command just adds it as a remote, it won't create the remote repo.
   
