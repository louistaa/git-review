# Louis's INFO340 git review
common git commands for INFO 340. Literally all the git commands you ever need to use for this class.

## sanity check
```git status```: check what files have been changed since the last commit and what branch you are on.

## pushing to git trifecta

```git add .```: add all files that have been changed since the last commit to the staging area. It tells git that you want to include updates in the next commit. 

```git commit -m "what you did"```: captures a snapshot of the project's currently staged changes. Saves your changes to the _local repository_ (your machine only). Note: the -m flag takes a string of what you did / what the commit will update!

```git push```: upload local repository content to a remote repository. Pushing is how you transfer commits from your local repository to a remote repo.

## working with branches

```git checkout -b your-new-branch-name```: create a new branch in the repo. Note: the -b flag takes a name of the new branch name!

```git checkout existing-branch-name```: switch to an existing branch.

## merging to main
### Golden rule: you always merge onto yourself!
### Golden rule 2: all changes come to main already committed, so just need to do a push!


if you're on louis-branch (or any branch that is not on main)
```bash
git add . # add my changes to staging area
git commit -m "message" # save snapshot of updates locally
git push # upload all my local changes to the repo
```

switch to main to make it up to date with your branch

```bash
git checkout main
git merge louis-branch # you merge onto yourself
git push # because you are changing your local version of main, you need to push upload it for everyone on the repo
```

NOW YOU ARE DONE :DDDDDDDDD


## merging from main
so you have updates from main that you need locally
if you're on louis-branch (any branch that is not on main)

```bash
git status . # check if you are in the correct branch you want to recieve changes in
git pull # pull the changes that someone else has pushed
git checkout louis-branch # switch to the branch you want to apply changes to
git merge main
```

Simple 4-step process, unless you get a merge conflict. To avoid merge conflicts:

1. Always pull before you push
2. More often than not, you will 'Accept Incoming Change' to resolve merge conflicts
3. Confirm with your teammates on how to resolve the conflicts just incase you lose code (THIS HAS HAPPENED TO ME BEFORE)
4. Use VSCode to help you with merge conflicts!

## "i fked up" git solutions

```git stash```: remove all changes to the files you did and revert to the old state of since the last commit. Useful when you have been working on code that no longer has a use.

```:wq```: how to exit vim. Sometimes you'll enter vim, the text-editor that git uses. 