# Awesome Git Cheatsheet

## Create ssh-key

`cd ~`<br>
`ssh-keygen -t ed25519 -C "email binded with github"` or `ssh-keygen -t rsa -b 4096 -C "email binded with github"`<br>
Enter + Enter + Enter<br>
`cat ~/.ssh/id_ed25519.pub` or `cat ~/.ssh/id_rsa.pub`<br>
Insert to github -> settings -> SSH and GPG keys -> New SSH key<br>
`ssh -T git@github.com`<br>

## Other useful commands

`cd projects/project1`<br>
`git init` # make the project1 directory a repository<br>

`rm -rf .git` # make a repository back to the directory<br>
`-r` # means **r**ecursive, i.e. recursively delete all files and directories<br>
`-f` # means **f**orce<br>

`git remote add origin https://github.com/%Username%/project1.git` # bind a local repository to a remote repository with a SSH link<br>
`git remote -v` # check that the repositories are actually linked<br>
`-v` # means **v**erbose<br>

`git push -u origin main` # for the first time, upload all commits from the local repository to the remote repository named `origin`<br>
`-u` # means **u**pstream; is used to establish an upstream connection between a local branch and a remote branch<br>
`git push` # upload commits to the remote repository after it has been bound using the `-u` flag<br>

`git add file1.txt` # prepare the `file1.txt` file for commit<br>
`git add file1.txt main.py` # prepare some files for commit<br>
`git add --all` or `git add .` # prepare all files that have been changed and all new files for commit at once<br>

`git commit` # make a commit and leave a comment in Vim or Nano<br>
Exit the Vim editor: press `Esc`, type `:qa!`, press `Enter`<br>
`git commit -m "Commit comment"` # make a commit and leave a comment<br>
`-m` # means **m**essage<br>

`git status` # show the current state of the repository<br>
`git log` # pull up a detailed commit history<br>
`git log --oneline` # show brief information about commits: abbreviated hash and message<br>

`git commit --amend --no-edit` # add the changes to the last commit and leave the message the same<br>
`git commit --amend -m "New message"` # add the changes to the last commit and leave a new message<br>

`git restore --staged file1.txt` # move the `file1.txt` file from **staged** to **untracked** or **modified**<br>
`git restore file1.txt` # revert the `file1.txt` file to the latest version that was saved via `git commit` or `git add`<br>
`git reset --hard b576d89` # remove all uncommitted changes from staging and the workspace up to the specified commit<br>

`git diff` # show the changes in the "workspace", i.e. in the modified files<br>
`git diff --staged` # show the changes that are added to the **staged** files<br>
`git diff a9928ab 11bada1` # show the difference between the two commits<br>

`git clone git@github.com:%Username%/project1.git` # clone the repository with the URL `project1.git` from **%Username%** account to my local computer<br>

## Undoing changes

### Working directory

`git checkout -- file1.txt`<br>
`git checkout .`<br>
`git clean -xdf`<br>

### Staging area (Index)

`git reset -- file1.txt`<br>

### Local branch

`git reset HEAD^^ (HEAD~2)`<br>
`git commit --amend -m "Commit message"`<br>

### Remote repository

`git revert <sha1>`<br>

## Git reset

`git reset --soft`<br>
`git reset --mixed`<br>
`git reset --hard`<br>

## Conflict solving

`git merge --abort` # abort merge<br>
`git checkout --Xours --Xtheirs` # resolve by selecing version<br>
`git diff` # resolve manually<br>
`git revert 09fe472` # undo merge<br>

## Tags

`git tag ver1` # mark commit with tag<br>
`git tag -list` # view tags<br>
`git push --tags` # push<br>
`git checkout ver1` # check it out<br>

## Stash

`git stash save "description"` # save working directory<br>
`git stash list` # view stashes<br>
`git stash pop` # bring them back and remove from stash<br>
`git stash apply` # bring them back, leave in stash<br>
`git stash drop` # remove<br>

## Remotes

`git remote add <name> <url>`<br>
`git remote add origin git@github.com:user/repo.git` # add<br>

`git remote -v`<br>
`git remote show <name>` # view<br>
