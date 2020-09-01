## Git Cheat Sheet
A few handy git commands for quick lookup.

### Create new Branch and Push to Remote

```
# Create branch and checkout to it
git checkout -b NEW_BRANCH_NAME

# Push New Branch to remote
git push origin NEW_BRANCH_NAME
```


### Delete Branch from Local and Remote

```
# Delete branch locally
git branch -d BRANCH_NAME

# Push delete to remote
git push origin --delete BRANCH_NAME
```


### Recover Dangling Commits

```
# Shows all commits HEAD pointed to.
git reflog

# Checkout to the dangling commit, if available
git checkout COMMIT_SHA1_VALUE
```


### Branch Merges

```
# Merge into current branch
git merge FEATURE_BRANCH_NAME
```

1. Fast Forward Meger:
	Moves (fast forwards) base branch label to the tip of the feature branch.
	Only possible if no other commits exists on the base branch.
	Results in a linear commit history.

2. Merge Commit (NO ff):

Done via some merge strategy.
	
```
# Merge into current branch, without FastForward even when possible
git merge --no-ff FEATURE_BRANCH_NAME
```
