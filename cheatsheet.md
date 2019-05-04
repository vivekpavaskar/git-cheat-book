Quick Cheet Sheet For Reference
===================================

## Setting Up git Repository
Commands|Description
--------|-----------
`git init`|Initialize the repository
`git clone [url]`|Clones the repository from remote server

## Tracking/Staging Files
Commands|Description
--------|-----------
`git status`|Shows the files which are modified in detail
`git status -s`|Shows the files which are modified in one line
`git add [file_names]`|Stages the new/modified file(s) 
`git add .`|Stages all new/ modified files
`git reset head [file_names]`|Unstages the file
`git checkout -- [file_name]`|Unmodifies the modified file

## Ignoring Files
Commands|Description
--------|-----------
`touch .gitignore`|Creates .gitignore file
`echo '[file_path]' >> .gitignore`|Inserts the file_path into .gitignore file
`git rm -r --cached [file_name]`|To remove file which is already staged/commited

## Commiting Changes
Commands|Description
--------|-----------
`git commit -m "[message]"`|Stores snapshot of the stages file
`git commit --amend -m "[message]"`|Replaces previous snapshot with current snapshot along with message
`git commit --allow-empty -m "[message]"`|Allows you to commit without any staged files

## Viewing Commit History
Commands|Description
--------|-----------
`git log`|Shows all commits
`git log --oneline`|Shows all commits in one line mode
`git log --graph`|Shows all commits in graph mode in detail
`git log --graph --oneline`|Shows all commits in one line mode as well as in graph mode
`git log --pretty=oneline`|Shows all commit in oneline with complete commit number
`git log -p`|Shows all commits with diff

## Working With Remotes
Commands|Description
--------|-----------
`git remote`|Shows all Remotes
`git remote -v`|Shows all Remotes in detail
`git remote add [remote_name] [url]`|Adds new remote branch
`git remote remove [remote_name]`|Removes the remote branch
`git remote rename [old_remote_name] [new_remote_name]`|Renames the remote branch
`git remote set-url --add --push [remote_name] [second_URL]`|Adds another repository url to the same remote name(only for push)
`git remote show [remote_name]`|Shows all branch names present in remote

## Tagging
Commands|Description
--------|----------
`git tag`|Lists all tags
`git tag -l "[pattern]"`|Lists all tags of perticular pattern
`git tag [pattern]`|Creates new tag (Lightweight tag)
`git tag -a [pattern] -m "[message]"`|Creates new tag with message for last commit (-a : Annotated tag)
`git tag -a [pattern] -m "[message]" [commit checksum]`|Creates new tag with message for perticular commit of that checksum
 `git push [remote] [tag pattern]`|Publishes perticular tag to remote branch
 `git push [remote] --tags`|Publishes all tags to remote branch

## Working With Branch
Commands|Description
--------|----------
`git branch [branch_name]`|Creates new branch
`git checkout [branch_name]`|Switches to existing branch
`git checkout -b [branch_name]`|Creates and switches new branch
`git branch -d [branch_name]`|Delete fully merged branch
`git branch -D [branch_name]`|Delete branch (even if not merged)
`git branch -m [new_branch_name]`|Rename the current branch name to new branch name
`git merge [branch_name]`|Merges other branch specified to current branch

## Pushing/Pulling Branch To Remotes
Commands|Description
--------|-----------
`git push [remote_name] [branch_name]`|Pushes(uploads) your commits from Local Branch to Remotes
`git fetch [remote_name] [branch_name]`|Fetches(downloads) your commits from Remotes to Local Branch as new branch
`git pull [remote_name] [branch_name]`|Fetches(downloads) your commits from Remotes to Local Branch as new branch and merges to your current branch
`git push -f [remote_name] [branch_name]`|Force updates remote server repository by uploading from local repository

## Configuring git 
Commands|Description
--------|----------
`git config --global user.name "[name]"`|Set name of the author for current repository
`git config --global user.email "[email]"`|Set email address of the author for current repository
`git config user.name "[name]"`|Set name of the author for current repository
`git config user.email "[email]"`|Set email address of the author for current repository
`git config --global credential.helper cache`|Stores credentials temoprory for 15 minutes
`git config --global credential.helper store`|Stores credentials permanently
`git config -l`|Lists all configurations
`git config --global http.proxy http://[proxy_username]:[proxy_passeord]@[proxy_server]:[proxy_port]`|Enables git to access remote server via proxy network
`git config --global --unset http.proxy`|Unset the proxy settings


## Advance git
1. To merge changes only from [better_branch] to master branch and discarding the master
```
git checkout [better_branch]
git merge --strategy=ours --no-commit master
git commit 
git checkout master
git merge [better_branch]
```