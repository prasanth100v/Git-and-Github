# 🔥 Git & GitHub Interview Questions (Real Scenarios)
## 1️⃣ Scenario: You modified a file but don’t want to commit yet. What do you do?
  I keep the changes in my working directory **or** use **git stash** if I need to switch tasks. 
     Stash temporarily saves my work without committing.
```
git stash
```
## 2️⃣ Scenario: You accidentally committed sensitive data. What’s your fix?
 If it’s not pushed, I use **git reset** to remove the commit. If it’s already pushed, 
     I use **git revert** to safely undo without rewriting history.
```
git revert <commit-id>
```
## 3️⃣ Scenario: Two developers edited the same file and Git throws a conflict. What do you do?
 I open the conflicted file, manually resolve the changes, remove conflict markers, then add and commit the fix.
```
git add file.txt
git commit -m "Resolve merge conflict"
```
## 4️⃣ Scenario: You want to test a new feature without breaking production code.
I create a new feature branch and work there. This keeps the main branch stable.
```
git checkout -b feature/new-api
```
## 5️⃣ Scenario: Your teammate pushed changes. How do you get them?
I pull the latest changes from the remote branch.
```
git pull origin main
```
## 6️⃣ Scenario: You pushed buggy code to GitHub. Production is affected.
I revert the faulty commit so production returns to a stable state while keeping history intact.
```
git revert <commit-id>
```
## 7️⃣ Scenario: You want to submit code but need approval first.
 I push my branch and create a Pull Request for code review before merging.
> 🧠 Shows teamwork and best practices.

## 8️⃣ Scenario: You want to contribute to an open-source project.
 I fork the repository, clone my fork, make changes, then raise a pull request.

## 9️⃣ Scenario: You want to see who changed a specific line in a file.
I use git blame to track line-level history.
```
git blame file.txt
```
## 🔟 Scenario: You want to undo the last commit but keep changes.
I use soft reset.
```
git reset --soft HEAD~1
```
## 1️⃣1️⃣ Scenario: You want to remove a file from Git but keep it locally.
I remove it from tracking and add it to .gitignore.
```
git rm --cached file.txt
```
## 1️⃣2️⃣ Difference between git fetch and git pull?
 **git fetch** only downloads changes, while **git pull** downloads and merges them into the current branch.

## 1️⃣3️⃣ Scenario: You want to mark a stable production release.
I create a tag for that commit.
```
git tag v2.0
```
## 1️⃣4️⃣ Scenario: CI/CD should run automatically when code is pushed.
I configure GitHub Actions workflow to trigger on push events.


## 🟢 Scenario : You pushed code directly to main by mistake
Problem: Production branch got unreviewed code.

Best Practice Solution: Revert the commit and follow PR process next time.
```
git revert <commit-id>
```
> git revert — undo safely (history stays clean)
Why teams love git revert

✅ Safe for production — doesn’t rewrite history

🤝 Collaboration-friendly — no force pushes

🧾 Auditable — clear “undo” commit in history

### Mental model (easy analogy)
```
git revert → “Add a correction note to the record” 📝
git reset → “Erase pages from the record” ❌
```
🔑 One-line difference
```
git revert → Undo safely by adding a new commit
git reset → Rewrite history by moving HEAD backward
```
## revert vs reset
### Q: What do you use in production?
> “git revert, because it doesn’t rewrite history and is safe for shared branches.”

## Q: When do you use git reset?
> “Only for local commits that haven’t been pushed.”

## 🟢 Scenario : Your PR is approved but shows merge conflicts
### Problem: Your branch is outdated compared to main.
Solution: Update your branch with latest changes.
```
git checkout feature/login
git pull origin main
```
Resolve conflicts → commit → push again.
> Key Interview Point: Conflicts should be resolved in the feature branch, not in main.

## 🟢 Scenario : You want to contribute to an open-source project
Problem: You don’t have write access.
#### Solution Workflow:
```
Fork repository
Clone your fork
Create branch
Commit changes
Open Pull Request
```
## 🟢 Scenario : You accidentally committed a .env file
#### Problem: Sensitive data pushed to GitHub.
 Solution: Remove file and Add to **.gitignore**
```
git rm --cached .env
```
## 🟢 Scenario 10: You want deployments only after PR merge
#### Problem: Prevent direct deploys from feature branches.
Solution: Configure GitHub Actions to trigger on main only.
```
on:
  push:
    branches:
      - main
```
Interview Gold Line:  “We deploy only reviewed and merged code.”

# 🌿 Feature Branches 
## ✅ What is a Feature Branch?
A feature branch is a temporary branch created from the main codebase to develop a specific feature, bug fix, or change without impacting production code.

## 🔐 Managing a Private Repository (DevOps View)
### ✅ What is a Private Repository?
A private repository is a GitHub repo where only invited users can view or contribute to the code.





