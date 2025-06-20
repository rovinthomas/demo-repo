# Demo

Create description!!!!!

## subheader

watch tutorial on youtube. 

## Local Development

1. Open index.html in your browser.

clone
add
commit
push
pull


ls -la : to view hidden files & folders (if its a git folder, there will be a hidden .git/ folder here)

git status: show all fles that were updated or created but havet been updated yet

git add .: start tracking all files listed in git status (both modified and untracked)

git add index.html: start tracking specific file

git commit -m "some title e.g. Added index.html" -m "some description"

git push: push this live to remove repo where my project is hosted

ssh-keygen -t rsa -b 4096 -C "rovin.thomas@ou
tlook.com" - for creating SSH key

ls ~/.ssh | grep id_rsa - to find my SSH key

cat ~/.ssh/id_rsa.pub | clip - to copy the key from the terminal (for Git bash on windows)

[refer to github website for steps on adding the key]

git branch : to get name of the master

git push origin master : to push updates to github repo (in this case main is the name of the master)

git init: initialise empty git repo in cwd

git remote add origin git@github.com:rovinthomas/demo-repo2.git: to connect locally created GIT folder to empty repo on my github

git remote --v: to check the above step

git push -u origin master: so that in future i just need to type git push without specifying origin and master every time

git branch: to view all existing branches (with * on current branch im on)

git checkout name_of_branch_to_switch_to: to switch between branches

git chekcout -b new_branch_name: to create a new branch with name

git diff new_branch_name: to view changes made since separation of this new branch

git merge new_branch_name: to merge the new changes from new_branch_name back with main (not commonly used?)

git pull origin master: to pull updates from github repo

## UNIQUE CHANGES 

changes 
