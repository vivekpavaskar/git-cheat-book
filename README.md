Git Cheat Sheet
====================
_A collection of useful git commands._

## Setup Repository
Commands|Description
--------|-----------
`git init`|Initialize the repository
`git clone [url]`|Clones the repository from remote server

## Staging/Tracking Files
Commands|Description
--------|-----------
`git status`|Shows the files which are/aren't stages
`git add [file_names]`|Stages the new/modified file(s) 
`git add .`|Stages all new/ modified files
`git commit -m "[message]"`|Stores snapshot of the stages file
`git commit --amend -m "[message]"`|Replaces previous snapshot with current snapshot along with message
`git commit --allow-empty -m "[message]"`|Allows you to commit without any staged files

## Working With Logs/History
Commands|Description
--------|-----------
`git log`|Shows all commits
`git log --oneline`|Shows all commits in one line mode
`git log --graph`|Shows all commits in graph mode in detail
`git log --graph --oneline`|Shows all commits in one line mode as well as in graph mode

## Publishing Local Repository
Commands|Description
--------|-----------
`git pull [remote_name] [branch_name]`|Updates local repository by downloading from remote server repository
`git push [remote_name] [branch_name]`|Updates remote server repository by uploading from local repository
`git push -f [remote_name] [branch_name]`|Force updates remote server repository by uploading from local repository

## Managing .gitignore
Commands|Description
--------|-----------
`touch .gitignore`|Creates .gitignore file
`echo '[file_path]' >> .gitignore`|Inserts the file_path into .gitignore file
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
`git remote set-url --add --push [remote_name] [second_URL]`|Adds another repository url to the same remote name(only for push).

## Managing Credential
Commands|Description
--------|----------
`git config user.name "[name]"`|Set name of the author for current repository
`git config user.email "[email]"`|Set email address of the author for current repository
`git config --global user.name "[name]"`|Set name of the author for current repository
`git config --global user.email "[email]"`|Set email address of the author for current repository
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



Visit my other repo for updated git cheat sheet

1. [Github](https://github.com/vivekpavaskar/git-cheat-sheet)
2. [Bitbucket](https://bitbucket.org/vivekpavaskar/my-git-cheat-sheet/src/master/)
3. [GitLab](https://gitlab.com/vivekpavaskar/my-git-cheat-sheet)