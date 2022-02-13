# git-cheatsheet-
Cheatsheet for git

# Index
1. [Basics](#basic)
2. [Branches](#branches)


# Basics


## Configuration

Set name: `git config --global user.name "<your_name>"`
Set email: `git config --global user.email <your_email>`
List config: `git config --global --list`
remove `--global` to make a change in local git repository

## New project

Initialisation: `git init`

Initialisation + add repository: `git init <repository_name>`

## Manage files

Index file:  `git add <file_path>`

Index all files:  `git add .`

Remove from index: `git restore --staged <file_paths>` or (old) `git reset HEAD <file_paths>`

Remove all changes:  `git restore <file_paths>` or (old) `git checkout  <file_paths>` also add `origin/master` optionnal argument

## Info / details

Check status:  `git status`

List commit: `git log --oneline` option 

Show changes: `git diff`

Show also index changes: `git diff --cached`

Show specific commit `git show <commit_SHA-1>`

Show master commit `git show master`

Show history within file (from line 10 to line 20) `git blame -L 10,20 <file_name>` ou `-L 10`

## Commit

Add to local repository: `git commit -m "<commit_message>"`

Add to local repository keep same commit: `git commit --amend"`


## Tag definition

tag `master` last commit of master branch

tag `head` current commit on which we are

tag `origin/master` last commit of the remote repository


## Move

Move to commit `git checkout <commit_SHA-1>`

Move to master `git checkout master`

Move to tag `git checkout <tag_name>`

When `HEAD` points to a commit (not a branch) state is 'detached HEAD'

## Custom tags

Custom tags are linked to one commit

Create tag `git tag <tag_name>`

Other option `git tag <tag_name> -m"<tag_message>"`

Delete tag `git tag --delete <tag_name>`

List tags `git tag`

## Copy a commit

Copy commit: `git cherry-pick <commit_SHA-1>`


# Github

Clone git repository from github (remote origin created automatically) `git clone <repository_url> <new_folder_name>`

List remotes: `git remote -v`

Show remote details: `git remote show <remote_name>`

Add remote: `git remote add <remote_name> <repository_url>`

Push commits: `git push -u <remote_name> <branch_name>`
example `git push -u origin master`
`<remote_name>` is optionnal defaul is `origin`

Push tag: `git push <remote_name> <tag_name>`

Push all tags: `git push <remote_name> --tags`

Fetch changes `git fetch` get the commits + tags + moves tag `origin/master`

Pull changes `git pull` perform `git fetch` + moves tag `master`

use .gitignore
example
```
tmp/todo.txt
tmp/*
*.txt
```

## Temporay change

Cut current changes `git stash`

Paste changes `git stash pop`

Cut and save current changes `git stash save "<stash_message>"`

Paste saved changes `git stash pop <stash_index>`

List changes `git stash list`

Details change `git stash show <stash_index>`


## Merge commit

Commist list (remote repository) : A-B-C-D-E
Commits list (local repository) : A-B-C-D-F

Does not working : `git push`
Must update local repository

NOT RECOMMANDED
Update local repository start merge automatically : `git pull`
If conflit, manage conflicts in file then: `git add .`
Create merge commit: `git commit -m "merge of files"`
Push changes: `git push`

RECOMMANDED
Update local repository : `git pull --rebase`
If conflit, manage conflicts in file then: `git add .` + `git rebase --continue`
Push changes: `git push`

# Branches

## Merge branch

Master branch: A-B-C-D-E
Feature branch (branch_name): A-B-C-D-1-2-3


NOT RECOMMANDED
Move to master : `git switch master` or (old) `git checkout master`
Start merge: `git merge <branch_name>`
If conflit, manage conflicts in file then: `git add .` + `git commit -m "merge of files"`
Push changes: `git push`

RECOMMANDED
Move to feature branch : `git switch <branch_name>` or (old) `git checkout <branch_name>`
Update local repository : `git rebase master`
While conflit, manage conflicts in files then: `git add .` + `git rebase --continue`
Move to master : `git switch master` or (old) `git checkout master`
Start merge: `git merge <branch_name>`

List branches: `git branch`
List branches on remote repository: `git branch -a`

Create new branche: `git branch <branch_name>`

Move branche: `git switch <branch_name>` or `git checkout <branch_name>`

Create + move to branche: `git switch -c <branch_name>` or `git checkout -b <branch_name>`

Logs in branch: `git log <branch_name>`

## Delete branch

Delete branch locally: `git branch -d <branch_name>`

Delete branch on remote repository: `git push origin --delete <branch_name>`

```
big code
```

