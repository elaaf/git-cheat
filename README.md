## Git Cheat Sheet
A few handy git commands for quick lookup.
  
  
### Create new Branch and Push to Remote
  
```
# Create branch and checkout to it
git checkout -b NEW_BRANCH_NAME
```
  
```
# Push New Branch to remote
git push origin NEW_BRANCH_NAME
```
  
  
  
### Delete Branch from Local and Remote
  
```
# Delete branch locally
git branch -d BRANCH_NAME
```
  
```
# Push delete to remote
git push origin --delete BRANCH_NAME
```
  
  
  
### Branch Merges
  
1. Fast Forward merge:
	Moves (fast forwards) base branch label to the tip of the feature branch.
	Only possible if no other commits exists on the base branch.
	Results in a linear commit history.
  
2. Merge Commit (NO ff):
	Done via some merge strategy.
  
  
```
# Merge FEATURE_BRANCH into current branch
git merge FEATURE_BRANCH_NAME
```
  
  
```
# Merge into current branch, without FastForward even when possible
git merge --no-ff FEATURE_BRANCH_NAME
```
  
##### Squash Merge
  
```
# To rebase merge FEAT_BRANCH into current branch (Can also use `rebase`).
git merge --squash FEAT_BRANCH
```
  
  
  
### Amending a commit
  
```
# To modify the last commit (work and message).
# Add new changes to staging area
git add FILE_NAME
```
  
```
# Modify the previous commit.
git commit --amend
```
  
```
# Modify the previous commit, reusing the previous commit message.
git commit --amend --no-edit
```
  
  
### Recover Dangling Commits
  
```
# Shows all commits HEAD pointed to.
git reflog
```
  
```
# Checkout to the dangling commit, if available
git checkout COMMIT_SHA1_VALUE
```
  
  
  
### Rebasing
  
Changes the history i.e. parents (base) of commits in a repository.
Similar to `git merge`.
  
  
1. ##### Regular Rebase
  
```
# Checkout to the branch you want to rebase onto another.
git checkout BRANCH_TO_REBASE
```
  
```
# Rebase current branch onto a base branch.
git rebase BASE_BRANCH_NAME
```
  
```
# OR combined
git rebase BASE_BRANCH_NAME BRANCH_TO_REBASE
```
  
```
# Continue rebase 
git rebase --continue
```
  
```
# Abort rebase
git rebase --abort
```
  
  
2. ##### Interactive Rebase
  
WARNING ! DO NOT USE FOR SHARED COMMITS !
  
```
# To change the commit history (after a specific commit) of current branch.
git rebase -i AFTER_THIS_COMMIT
```
  
Rebase Options:  
  
```
pick: 		use commit  
reword: 	use commit, modify message  
edit:		use commit, but stop to modify/ammend commit  
squash:		use commit, but squash into previous commit  
fixup:		use commit, but squash into previous commit and drop its message  
drop:		remove commit  
exec:		run shell command (rest of the line)  
```  
  
Save the file, to begin rebase.
Continue after commit edits using `git rebase --continue`.