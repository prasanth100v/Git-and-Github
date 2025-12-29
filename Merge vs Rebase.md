What is rebase in Git and GitHub?
🟦 Merge
 > Connect histories without changing the past
### One-line memory trick 🧠
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
### Situation
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
