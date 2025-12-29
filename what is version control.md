# What is version control?
Version control is a system that tracks changes to files over time, so you can:
```
See what changed
See who changed it
Go back to any previous version
Work with others safely on the same project
```
# What is a commit?
### A commit is: A snapshot of your project at a point in time
> Each commit represents a version of the code with author, timestamp, and message.
> ## Each commit = one version of your code.

Example:
```
Commit 1: Added login page
Commit 2: Fixed login bug
Commit 3: Improved UI
```
### 👉 Version control = history
### 👉 Commit = one saved point in that history

## See the history (MOST IMPORTANT COMMAND)
```
git log
```
### (green = added, red = removed)
📌 This shows: All commits, Who made them, When they were made and Commit messages
> If you can see commits and their history, you are seeing version control.

## See what changed in a version:
```
git show a1b2c3
```

## See differences between versions and (between two commits)
```
git diff
git diff d4e5f6 a1b2c3
```
 
⭐ One-line definition (memorize this)
> Version control is the backbone of modern software development that manages code changes, collaboration, and stability.

# Rollback
Moving from recently updated code back to previous code is called a version control operation. 
In Git, this is done using rollback, revert, reset, or checkout of commits.
> Rollback is the process of restoring code to a previous stable version.

## git checkout — View old code (SAFE)
👉 Use when you just want to see or test old code
```
git checkout <commit-id>
```
> What happens: Code moves to an old version
### 📌 Interview line:
Checkout is used to inspect previous commits without changing history.

## PERMANENTLY undo changes
👉 Use when wrong code is already pushed
```
git revert a1b2c3
```
> What happens: Creates a new commit and That commit undoes the changes
## 📌 Interview line:
Revert is the safest rollback method in production because it does not rewrite history.

## DANGEROUS rollback (local only)
👉 Use only if not pushed to GitHub
```
git reset --hard d4e5f6
```
>  Deletes commits permanently
> Code goes back completely

git checkout is used to .

## One-line memory trick
### git checkout → look back [inspect previous versions]
### git revert → safely undo
### git reset → force undo (dangerous)




