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

Remove from index: `git reset <file_path>`

## Info / details

Check status:  `git status`

List commit: `git log --oneline` option 

Show changes: `git diff`

Show also index changes: `git diff --cached`

Show specific commit `git show <commit_SHA-1>`

Show master commit `git show master`

## Commit

Add to local repository: `git commit -m "<commit_message>"`

Add to local repository keep same commit: `git commit --amend"`


## Tag definition

tag `master` last commit of a given branch

tag `head` current commit on which we are

tag `origin/master` last commit of the remote repository


## Move

Move to commit `git checkout <commit_SHA-1>`

Move to master `git checkout master`

Move to tag `git checkout <tag_name>`

## Custom tags

Custom tags are linked to one commit

Create tag `git tag <tag_name>`

Other option `git tag <tag_name> -m"<tag_message>"`

Delete tag `git tag --delete <tag_name>`

List tags `git tag`

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

# Branches

## 

```
big code
```

