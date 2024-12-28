# GIT Reference


## Configuration

Git has 3 Configurations
1. System - this is system level for all users
   1. On WSL/Ubuntu it's `/etc/gitconfig`
   2. On Mac it's at `/private/etc/gitconfig`
   3. On Windows it's at `<GITROOT>\etc\gitconfig`
2. Global - This is for local logged in user
   1. On WSL/Ubuntu it's `/root/.gitconfig` or `~/.gitconfig`
   2. On Mac it's at `~/.gitconfig`
   3. On Windows it's at `%USERPROFILE%\.gitconfig`
3. Local - You have to be within a repo
   1. For all systems it will be at `.git/config`

```
#edit
git config --global --edit

git config --local --list

```


## Line Ending
for Windows which has a CRLF ending use
    `git config --local core.autocrlf true`  

for linux/mac which uses LF ending
    `git config --local core.autocrlf input`  