# What is Merge vs Rebase in Git?
 * 🚀 Merge = connect       →  “Join timelines”
 * 🚀 Rebase = rearrange    →  “Reorder my commits after latest main”

## Commands (just remember these)
Merge
```hcl
git checkout main
git merge feature
```
Rebase
```hcl
git checkout feature
git rebase main
```
Rebase = `“Put my changes after the latest changes”`

## Situation
```hcl
main branch = original code
feature branch = your work
```
#### What happened
```hcl
You created feature
You made 2 commits
Someone updated main
Now Git sees two different timelines.
```
### What rebase does 
Command
```hcl
git checkout feature
git rebase main
```
Git internally does:
```hcl
1. Temporarily removes your commits
2. Updates feature branch to latest main
3. Re-applies your commits one by one
4. ✅ Code stays same
5. ❌ Commit IDs change (this is key)
```
### When YOU should use rebase ✅
```hcl
✔ Before creating a PR
✔ Cleaning commit history
✔ Your branch is only used by you
```
## Final check 👇
```hcl
If I say:
“My feature branch is only on my laptop”
Your answer should be: 👉 REBASE
```
## 1️⃣ Scenario: Feature branch is only on your laptop
### Q: You created a feature branch, made commits, and haven’t pushed it yet. main has moved ahead. What do you do?
 * ✅ Answer: I use **rebase.**
 * Why (interview logic) :
    * No one else is using this branch
    * Rebase keeps history clean
    * Safe to rewrite local commits
    * 👉 Rewriting history = changing old commits that already existed.
 * Command
```hcl
git checkout feature
git rebase main
```

## 2️⃣ Scenario: Feature branch is already shared with teammates
### Q: Two developers are working on the same feature branch. main has new commits.
* ✅ Answer: I use **merge,** not rebase.
* Why :
    * Rebasing would `rewrite commit IDs`
    * Teammates will face conflicts
    * Merge is safe for shared history
 * Command
```hcl
git checkout feature
git merge main
```

## 3️⃣ Scenario: GitHub Pull Request shows conflicts
### Q: Your PR shows conflicts because main was updated. What do you do?
 * ✅ Answer: `I rebase my feature branch on main`, resolve conflicts, and `update the PR`.
 * Why: Keeps PR clean, Easier review and No extra merge commits
 * Commands
```hcl
git fetch origin
git rebase origin/main
git push --force-with-lease
```

## 4️⃣ Scenario: CI/CD pipeline triggered multiple times
### Q: Your GitHub Actions pipeline runs many times because of merge commits. What do you suggest?
 * ✅ Answer: Use rebase before PR or Rebase and merge strategy.

## 5️⃣ Scenario: Interview trick question ⚠️
### Q: What happens to commit IDs after rebase?
 * ✅ Answer: Commit IDs change because rebase rewrites history.
 * > That’s why I never rebase shared branches.

---

## 🔀 Git Merge vs Rebase — Rapid Fire Interview Q&A

| 🔢 Q#  | ❓ Question                                                           | 💡 Answer                                                                        |
| ------ | -------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| 🔹 Q1  | What is merge in Git?                                                | 👉 `Combines histories of two branches. `                                          |
| 🔹 Q2  | What is rebase in Git?                                               | 👉 `Reapplies commits on top of another branch. `                                  |
| 🧠 Q3  | One-line memory trick for merge?                                     | 👉 Merge = `connect timelines `                                                    |
| 🧠 Q4  | One-line memory trick for rebase?                                    | 👉 Rebase = `rearrange commits  `                                                  |
| 🔹 Q5  | Main difference between merge and rebase?                            | 👉 Merge `preserves history`; rebase `rewrites history`.                          |
| 🔹 Q6  | Which command connects timelines?                                    | 👉 git merge                                                                     |
| 🔹 Q7  | Which command rewrites commit history?                               | 👉 git rebase                                                                    |
| 🌿 Q8  | Command to merge feature branch into main?                           | 👉 git checkout main <br> 👉 git merge feature                                   |
| 🌿 Q9  | What happens during merge?                                           | 👉 Git combines both branch histories.                                           |
| 🌿 Q10 | Does merge change commit IDs?                                        | 👉 No.                                                                           |
| 🌿 Q11 | Is merge safe for shared branches?                                   | 👉 Yes.                                                                          |
| 🌿 Q12 | Why is merge preferred for shared branches?                          | 👉 It preserves shared history safely.                                           |
| 🌿 Q13 | What commit is often created during merge?                           | 👉 Merge commit.                                                                 |
| 🌿 Q14 | Main advantage of merge?                                             | 👉 `No history rewriting. `                                                        |
| 🔄 Q15 | Command to rebase feature branch onto main?                          | 👉 git checkout feature <br> git rebase main                                     |
| 🔄 Q16 | What does rebase do internally?                                      | 👉 Temporarily removes commits <br> Updates branch <br> Reapplies commits        |
| 🔄 Q17 | Main purpose of rebase?                                              | 👉 `Keep history linear and clean. `                                               |
| 🔄 Q18 | Does rebase change commit IDs?                                       | 👉 Yes.                                                                          |
| 🔄 Q19 | Why do commit IDs change after rebase?                               | 👉 Rebase rewrites commit history.                                               |
| 🔄 Q20 | Is code content changed during rebase?                               | 👉 `Usually no, only history changes.  `                                           |
| ⚠️ Q21 | Important question before rebasing?                                  | 👉 Did someone else pull this branch?                                            |
| ⚠️ Q22 | If branch is shared with others, should you rebase?                  | 👉 `No.  `                                                                         |
| ⚠️ Q23 | If branch exists only locally, should you rebase?                    | 👉` Yes. `                                                                         |
| ⚠️ Q24 | Why avoid rebasing shared branches?                                  | 👉 Teammates may face `conflicts/history mismatch`.                                |
| 🚀 Q25 | Best time to use rebase?                                             | 👉 `Before creating a Pull Request`.                                               |
| 🚀 Q26 | Why use rebase before PR?                                            | 👉 `Cleaner commit history.`                                                       |
| 🚀 Q27 | Good use case for rebase?                                            | 👉 `Personal/local feature branches.   `                                           |
| 🚀 Q28 | Why do teams prefer clean history?                                   | 👉 `Easier debugging and code review.  `                                           |
| 🚀 Q29 | Rebase helps avoid what?                                             | 👉 `Extra merge commits.  `                                                        |
| 👥 Q30 | Best use case for merge?                                             | 👉 `Shared branches/team collaboration.    `                                       |
| 👥 Q31 | Why is merge safer in teams?                                         | 👉 History remains unchanged.                                                    |
| 👥 Q33 | Merge is ideal when?                                                 | 👉 Multiple developers work on same branch.                                      |
| 🎯 Q34 | Your feature branch exists only on your laptop. What should you use? | 👉 `Rebase.   `                                                                    |
| 🎯 Q35 | Why is rebase safe locally?                                          | 👉 No one else depends on the branch.                                            |
| 🎯 Q36 | Two developers share a branch. What should you use?                  | 👉 Merge.                                                                        |
| 🎯 Q37 | Why avoid rebase on shared branch?                                   | 👉 `Commit IDs change.`                                                            |
| 🎯 Q38 | PR shows conflicts because main changed. What do you do?             | 👉 `Rebase feature branch on latest main.`                                         |
| 🎯 Q39 | Commands to update PR branch cleanly?                                | 👉 git fetch origin <br> git rebase origin/main <br> git push --force-with-lease |
| 🎯 Q40 | Why use --force-with-lease after rebase?                             | 👉 `Remote history changed after rewriting commits. `                              |
| 🎯 Q41 | Why is --force-with-lease safer than --force?                        | 👉 `Prevents overwriting others’ changes accidentally.  `                          |
| ☸️ Q42 | Why can merge commits trigger CI/CD multiple times?                  | 👉 `Every merge commit triggers pipeline again.  `                                 |
| ☸️ Q43 | How to reduce unnecessary pipeline runs?                             | 👉 `Use rebase before PR. `                                                        |
| ☸️ Q44 | Which strategy gives cleaner CI/CD history?                          | 👉 `Rebase and merge.`                                                             |
| ☸️ Q45 | Why do DevOps teams prefer linear history?                           | 👉 `Easier tracking and rollback. `                                                |
| ⚔️ Q46 | What is a merge conflict?                                            | 👉 `Conflict when same code changed differently.     `                             |
| ⚔️ Q47 | Can conflicts happen during rebase?                                  | 👉 Yes.                                                                          |
| ⚔️ Q48 | What must be done after resolving rebase conflicts?                  | 👉 `Continue rebase.  `                                                            |
| ⚔️ Q49 | Command to continue rebase?                                          | 👉 `git rebase --continue   `                                                      |
| ⚔️ Q50 | Command to cancel rebase?                                            | 👉 `git rebase --abort  `                                                          |
| 📜 Q51 | Which operation preserves branch history?                            | 👉 `Merge.`                                                                        |
| 📜 Q52 | Which operation creates linear history?                              | 👉 `Rebase. `                                                                      |
| 📜 Q53 | Which operation rewrites history?                                    | 👉 `Rebase.`                                                                       |
| 📜 Q54 | Which operation is non-destructive?                                  | 👉 `Merge.`                                                                        |
| 📜 Q55 | Why do some teams avoid merge commits?                               | 👉 `Git history becomes noisy.`                                                    |
| 🧠 Q56 | What happens to commit hashes after rebase?                          | 👉 `They change. `                                                                 |
| 🧠 Q57 | Why do hashes change after rebase?                                   | 👉 Commits are recreated.                                                        |
| 🧠 Q58 | Is rebase dangerous?                                                 | 👉 `Only on shared branches.`                                                      |
| 🧠 Q59 | One-line interview answer for rebase?                                | 👉 `Rebase creates clean linear history by replaying commits. `                    |
| 🧠 Q60 | One-line interview answer for merge?                                 | 👉 `Merge safely combines branch histories without rewriting commits. `            |
| ✅ Q61  | Best practice before PR?                                             | 👉 `Rebase local feature branch with latest main.   `                              |
| ✅ Q62  | Best practice for team/shared branches?                              | 👉 `Use merge.    `                                                                |
| ✅ Q63  | Best practice after rebase and push?                                 | 👉` Use --force-with-lease.  `                                                     |
| ✅ Q64  | Best branch update strategy for production?                          | 👉 `Merge for safety.  `                                                           |


