Git Cheat Sheet
====================
_A collection of git commands which I frequently use._

##Frequently used
Commands|Description
--------|-----------
`git init`|Initialize the repository
`git clone [url]`|Clones the repository from github
`git status`|Shows the files which are/aren't stages
`git add [file_names]`|Stages the new/modified file(s) 
`git add .`|Stages all new/ modified files
`git commit -m "[message]"`|Stores snapshot of the current directory
`git log`|Shows all cmmits
`git branch add [branch_name]`|Creates new branch
`git pull [remote_name] [branch_name]`|Updates local repository by downloading from github repository
`git push [remote_name] [branch_name]`|Updates github repository by uploading from local repository
`git push -f [remote_name] [branch_name]`|Force updates github repository by uploading from local repository(Not Recomended)

##Ignoring files
Commands|Description
--------|-----------
`touch .gitignore`|Creates .gitignore file
`echo [file_path] >> .gitignore`|inserts the file_path into .gitignore file
`git rm -r --cached [file_name]`|To remove file which is already staged/commited

##Rarely used
Commands|Description
--------|----------
`git config --global credential.helper cache`|Stores credentials temoprory for 15 minutes
`git config --global credential.helper store`|Stores credentials permanently

##Advance
1. To merge changes only from [better_branch] to master branch and discarding the master
```
git checkout [better_branch]
git merge --strategy=ours --no-commit master
git commit 
git checkout master
git merge [better_branch]
```