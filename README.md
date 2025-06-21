*: specific steps for adding code via the github interface
**: specific steps for adding code locally

## GENERAL:

*git clone SSH_link: to clone a repo from github to my local machine

**git init: initialise empty git repo in cwd of local machine

ls -la : to view hidden files & folders (if its a git folder, there will be a hidden .git/ folder here)

git status: shows the status of the working directory and staging area — which files are modified, untracked or staged

git add .: start tracking all files listed in git status (both modified and untracked), therby moving changes from cwd into the staging area (which indicats that i want to include these changes in the next commit)

git add index.html: start tracking specific file

git commit -m "some title e.g. Added index.html" -m "some description": commit staged changes with a message (title + description)

git commit -am "some title" - to add and commit together (only works for files that already been tracked/committed previously)

**git remote add origin git@github.com:rovinthomas/demo-repo2.git: to connect locally created GIT folder to empty repo created on my github

**git remote -v: to check any remote Githubs repos connected to this repo on my local machine

git push -u origin master (or git push): to push updates live to the REMOTE github repo where my project is hosted (-u is to set upstream, to set the location to push it to by default, then in future i can just call git push)

git pull -u origin master (or git pull): to pull updates live from the REMOTE master branch (over the network) and merge into my LOCAL current branch (-u is to set upstream, to set the location to pull from by default, then in future i can just call git pull)

====================================================================
## BRANCHING:
git branch: to view all existing branches (with * on current branch im on)

git checkout name_of_branch_to_switch_to: to switch between branches

git checkcout -b new_branch_name: to create a new branch with name

git diff other_branch_name: to compare current branch with other_branch_name

git diff: to compare cwd and staging area (= the changes ive made that i havent yet ADDed to the next commit)

git diff new_branch_name (or git diff): to view changes made since separation of this new branch from its parent branch

git merge other_branch_name: to merge the new changes from the LOCAL other_branch_name (no network involved) into my current branch

git branch -vv: to view summary of branch upstream info for all branches

git branch -d branch_name: to delete a branch only if it has been fully merged into another branch i.e. main branch

NOTE:
- git merge main (to feature branch): to keep feature branch up-to-date while still taking time to develop the feature
- git merge feature_branch (to main branch): to integrate completed feature into main codebase

('git merge feature_branch' updates local main branch with new feature, after which 'git push' updates the remote main branch, but this method of 'git merge feature_branch && git push' only works if you have direct write access to the remote main branch, i.e. without review process, which is less common in software dvlp team. The standard practice for most teams would be to 'git push' from the local feature branch to remote feature branch and then create GitHub pull request. When PR is accepted, GitHub performs 'git merge feature_branch' automatically in the backend.)

====================================================================
## UNDO:

git log: to view logs of all previous commits

git reset filename (or git reset) : to unstage a specific file from the last git add

git reset: to unstage all files from the last git add

git reset HEAD: to unstage all files till the last commit

git reset HEAD~1: to unstage all files till the last last commit

git reset commit_number: to unstage till a specific commit from logs

git reset --hard commit_number: to both unstage and undo all code changes till a specific commit from log

====================================================================
## OVERALL WORKFLOW (simplified)

- Github (web): write code -> commit changes -> make PR
- Local Git: write code -> stage changes (add) -> commit changes -> push changes -> make PR

====================================================================
## TO GENERATE AND ADD SSH KEY (FIRST TIME):
ssh-keygen -t rsa -b 4096 -C "email@outlook.com" - for creating SSH key

ls ~/.ssh | grep id_rsa - to find my SSH key

cat ~/.ssh/id_rsa.pub | clip - to copy the key from the terminal (for Git bash on windows)

[refer to github website for steps on adding the key].
====================================================================
## SAMPLE PROJECT FULL WORKFLOW:

On Friday:
1) Create local copy of Github repo
-> git clone SSH_link

Following Monday:
2) Update local main for any changes from Fri-Mon:
-> cd repo-folder/
-> git checkout main
-> git pull

3) Create and track a new feature branch:
-> git checkout -b feature/login
-> git push -u origin feature/login

4) Start developing the feature branch:
-> Edit code and use git status/add/commit

On Tuesday:
5) Re-update local main and local feature branch for any changes from Mon-Tue:
-> git checkout main
-> git pull
-> git checkout feature/login
-> git merge main

6) Continue developing the feature branch:
-> Edit code and use git status/add/commit

On Wednesday:
7) Re-update local main and local feature branch for any changes from Tue-Wed:
-> git checkout main
-> git pull
-> git checkout feature/login
-> git merge main

8) Continue developing the feature branch:
-> Edit code and use git status/add/commit

9) After done with my feature development and ready to go, re-update local main and local feature branch for any new recent changes today:
-> git checkout main
-> git pull
-> git checkout feature/login
-> git merge main
-> Test and ensure that my feature branch code is working correctly

10) Push fully developed and verified feature to remote repo
-> git push
-> Create pull request on github

By Friday, once supervisor has checked and approved feature to be fully implemented onto the main codebase:
-> He will accept the pull request, and the feature branch can subsequently be deleted.
