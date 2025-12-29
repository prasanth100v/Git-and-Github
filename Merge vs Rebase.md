# What is Merge vs Rebase in Git?
### One-line memory trick 
```
Merge = connect       → “Join timelines”
Rebase = rearrange    → “Reorder my commits after latest main”
```
## Ask yourself ONE question:
```
“Did someone else pull this branch?”
YES → ❌ Don’t rebase → MERGE
NO → ✅ Safe → REBASE
```
## Commands (just remember these)
Merge
```
git checkout main
git merge feature
```
Rebase
```
git checkout feature
git rebase main
```
Rebase = “Put my changes after the latest changes”

## Situation
```
main branch = original code
feature branch = your work
```
#### What happened
```
You created feature
You made 2 commits
Someone updated main
Now Git sees two different timelines.
```
### What rebase does 
Command
```
git checkout feature
git rebase main
```
Git internally does:
```
Temporarily removes your commits
Updates feature branch to latest main
Re-applies your commits one by one
✅ Code stays same
❌ Commit IDs change (this is key)
```
### When YOU should use rebase ✅
```
✔ Before creating a PR
✔ Cleaning commit history
✔ Your branch is only used by you
```
## Final check 👇
```
If I say:
“My feature branch is only on my laptop”
Your answer should be:
👉 REBASE
```

## 1️⃣ Scenario: Feature branch is only on your laptop
Q: You created a feature branch, made commits, and haven’t pushed it yet. main has moved ahead. What do you do?

✅ Answer: I use **rebase.**

### Why (interview logic):
```
No one else is using this branch
Rebase keeps history clean
Safe to rewrite local commits
```
👉 Rewriting history = changing old commits that already existed.
### Command
```
git checkout feature
git rebase main
```

## 2️⃣ Scenario: Feature branch is already shared with teammates
Q: Two developers are working on the same feature branch. main has new commits.

✅ Answer: I use **merge,** not rebase.

### Why:
```
Rebasing would rewrite commit IDs
Teammates will face conflicts
Merge is safe for shared history
```
### Command
```
git checkout feature
git merge main
```

## 3️⃣ Scenario: GitHub Pull Request shows conflicts
Q: Your PR shows conflicts because main was updated. What do you do?

✅ Answer: I rebase my feature branch on main, resolve conflicts, and update the PR.
> Why: Keeps PR clean, Easier review and No extra merge commits

### Commands
```
git fetch origin
git rebase origin/main
git push --force-with-lease
```
## 4️⃣ Scenario: CI/CD pipeline triggered multiple times
Q: Your GitHub Actions pipeline runs many times because of merge commits. What do you suggest?

✅ Answer: Use rebase before PR or Rebase and merge strategy.

## 5️⃣ Scenario: Interview trick question ⚠️
Q: What happens to commit IDs after rebase?

✅ Answer: Commit IDs change because rebase rewrites history.
 > That’s why I never rebase shared branches.





