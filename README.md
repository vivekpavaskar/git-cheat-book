Git Cheat Sheet
====================
_A collection of useful git commands._

## Frequently used
Commands|Description
--------|-----------
`git init`|Initialize the repository
`git clone [url]`|Clones the repository from remote server
`git status`|Shows the files which are/aren't stages
`git add [file_names]`|Stages the new/modified file(s) 
`git add .`|Stages all new/ modified files
`git commit -m "[message]"`|Stores snapshot of the current directory
`git commit --amend -m "[message]"`|Replaces previous snapshot with current snapshot along with message
`git log`|Shows all commits
`git pull [remote_name] [branch_name]`|Updates local repository by downloading from remote server repository
`git push [remote_name] [branch_name]`|Updates remote server repository by uploading from local repository
`git push -f [remote_name] [branch_name]`|Force updates remote server repository by uploading from local repository

## Managing .gitignore
Commands|Description
--------|-----------
`touch .gitignore`|Creates .gitignore file
`echo [file_path] >> .gitignore`|Inserts the file_path into .gitignore file
`git rm -r --cached [file_name]`|To remove file which is already staged/commited

## Managing Branch
Commands|Description
--------|----------
`git branch [branch_name]`|Creates new branch
`git branch -d [branch_name]`|Delete fully merged branch
`git branch -D [branch_name]`|Delete branch (even if not merged)

## Managing Remote Branch
Commands|Description
--------|----------
`git remote add [remote_name] [url]`|Adds new remote branch
`git remote remove [remote_name]`|Removes the remote branch
`git remote rename [old_remote_name] [new_remote_name]`|Renames the remote branch

## Managing Credential
Commands|Description
--------|----------
`git config --global credential.helper cache`|Stores credentials temoprory for 15 minutes
`git config --global credential.helper store`|Stores credentials permanently

## Advance
1. To merge changes only from [better_branch] to master branch and discarding the master
```
git checkout [better_branch]
git merge --strategy=ours --no-commit master
git commit 
git checkout master
git merge [better_branch]
```