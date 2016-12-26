# Git Fundamentals

## Config git

Some git basic config

```shell
git config --global user.name Nguyen Van A
git config --global user.email nguyen_van_a@example.com
git config --global core.editor notepad++
git config --global help.autocorrect 1
git config --global core.autocrlf false

# list all global config
git config --global --list
```

## Working locally with git

### init - status - add - commit - log

 Create a local repo

`git init`

 See untracked files

`git status`

 Add (stage) a file to commit it

`git add file_name`

 Commit the file

`git commit -m message`

 See commit log

`git log`

---


 Add (stage) all modified (updated) files to commit

`git add -u`

 Then commit it to local repo

`git commit -m message`

---

 Add (stage) all changed files (including new files)

`git add -A`

 Then commit them

`git commit -m message`

---

### diff - show

 See changes between 2 commits

`git diff 1st_commit_number..2nd_commit_number`

Or

`git diff HEAD~1..[HEAD]` (see diff of HEAD and 1 commit before it)

---

 Add (stage) a file to commit

`git add file_name`

 See staged changes

`git diff --cached`

---

 See changes of a commit

`git show commit_number`

Or

`git show HEAD`

---

### add - reset soft

 Add (stage) a file to commit

`git add file_name`

But want to unstage it after that

`git reset --soft`

---

### checkout - branch

 Create a new branch from the current branch

`git checkout -b new_branch_name`

 See available branches at local

`git branch`

 Checkout to another local branch

`git checkout a_branch`

 Rename the current branch

`git branch -m new_name

 Delete a local branch

`git branch -d branch_to_delete`


### checkout - reset hard

 Checkout to remove uncommitted changes of a file to HEAD 
 
`git checkout file_name`

 Reset to remove all uncommitted changes (of all files)

`git reset --hard`

 Move the HEAD back 1 commit

`git reset --hard HEAD~1`

---

### merge

 Merge a branch to the current branch

`git merge the_branch_to_merge_to_current_branch`

 After that delete the merged branch

`git branch -d the_branch_merged_to_current_branch`

---

### ignore files directories

 Create a .gitignore file
 Write what you want to be ignored inside the file. e.g

```
logs             (ignore any log directories in the application)
logs             (ignore any log directories below the rootpath)
logs.txt
logs.log
logs             (ignore anything in logs directory)
```

 Then commit .gitignore, push them into a shared repo, so the ignorance is updated for other developers when they pull the application.


## Working remotely with git

 Clone a repo

`git clone url_of_the_repo`

 See commit history of the project

```shell
cd to_the_cloned_project
git log 
```

 Check what is remoted

`git remote -v`

 fetch new branches... from remote repo

`git fetch`

 View remote branches

`git branch -r`

 Create a local branch from a remote branch

`git checkout remote_branch`
  Will create a local branch that tracks the remote branch

 Make some changes then commit to the local branch (see Working locally with git)

 Push committed content back to the remote branch

`git push`

 Pull changes of the remote branch to the local branch

`git pull`

 Clean remote branches that have been deleted from the remote repo

`git remote prune [remote_repo_name]`
  remote_repo_name is something like `origin`

## Further git

### stash

 You are working on a branch
 You have some uncommited changes
 And the changes are not ready to commit
 Then you have to checkout another branch to fix something (that is urgent)
? You can `stash` the changes for later commit

`git stash`
  modified content will be saved into stash

`git stash list`
  view what is being stashed

`git stash apply stash_number`
  take out a stash to your code, but not remove from the stash list

`git stash pop stash_number`
  take out a stash to your code, also remove it from the stash list

`git stash drop stash_number`
  delete a stash

### cherry-pick

 You have commitA on a branchA
 You want to apply that commit onto another branchB (with the same changes)
? You can `cherry-pick` commitA of branchA to branchB

```shell
git checkout branchB
git cherry-pick commit_number_of_commitA
```
















