# 🔥 Git & GitHub Interview Questions (Real Scenarios)
## 1️⃣ Scenario: You modified a file but don’t want to commit yet. What do you do?
  * I keep the changes in my working directory **or** use **git stash** if I need to `switch tasks`.
  * 🚀 Stash `temporarily saves` my work without committing.
```hcl
git stash
```

## 2️⃣ Scenario: You accidentally committed sensitive data. What’s your fix?
  * If it’s not pushed, I use **git reset** to remove the commit. If it’s already pushed,
  * 🚀 I use **git revert** to `safely undo` without rewriting history.
```hcl
git revert <commit-id>
```

## 3️⃣ Scenario: Two developers edited the same file and Git throws a conflict. What do you do?
 * I open the conflicted file, manually resolve the changes, remove conflict markers, then `add` and `commit the fix`.
```hcl
git add file.txt
git commit -m "Resolve merge conflict"
```

## 4️⃣ Scenario: You want to test a new feature without breaking production code.
 * I create a new feature branch and work there. This keeps the main branch stable.
```hcl
git checkout -b feature/new-api
```

## 5️⃣ Scenario: Your teammate pushed changes. How do you get them?
 * I pull the latest changes from the remote branch.
```hcl
git pull origin main
```

## 6️⃣ Scenario: You pushed buggy code to GitHub. Production is affected.
 * I revert the faulty commit so production returns to a stable state while keeping history intact (keep safe the entire sequence of commits).
```hcl
git revert <commit-id>
```

## 7️⃣ Scenario: You want to submit code but need approval first.
 * I push my branch and create a `Pull Request for code review` before merging.
 * 🧠 Shows teamwork and best practices.

## 8️⃣ Scenario: You want to contribute to an open-source project.
  * I fork the repository, clone my fork, make changes, then `raise a pull request`.

## 9️⃣ Scenario: You want to see who changed a specific line in a file.
 * I use git blame to track line-level history.
```hcl
git blame file.txt
```

## 🔟 Scenario: You want to undo the last commit but keep changes.
 * I use soft reset.
```hcl
git reset --soft HEAD~1
```

## 1️⃣1️⃣ Scenario: You want to remove a file from Git but keep it locally.
 * I remove it from tracking and add it to `.gitignore.`
```hcl
git rm --cached file.txt
```
## 1️⃣2️⃣ Difference between git fetch and git pull?
 * **git fetch** only downloads changes
 * **git pull** downloads and merges them into the current branch.

## 1️⃣3️⃣ Scenario: You want to mark a stable production release.
 * I create a tag for that commit.
```hcl
git tag v2.0
```

## 1️⃣4️⃣ Scenario: CI/CD should run automatically when code is pushed.
 * I configure GitHub Actions workflow to trigger on push events.

## 🟢 Scenario : You pushed code directly to main by mistake
 * Problem: Production branch got `unreviewed code`.
 * Best Practice Solution: `Revert the commit` and follow `PR process` next time.
```hcl
git revert <commit-id>
```
 * git revert — undo safely (history stays clean)
 * Why teams love git revert
    * ✅ Safe for production — doesn’t rewrite history
    * 🤝 Collaboration-friendly — no force pushes
    * 🧾 Auditable — clear “undo” commit in history

### Mental model (easy analogy)
 * ✅ git revert → “Add a correction note to the record” 📝
 * 🧾 git reset → “Erase pages from the record” ❌
### 🔑 One-line difference
 * git revert → `Undo safely` by adding a `new commit`
 * git reset → Rewrite history by `moving HEAD backward`

## revert vs reset
### Q: What do you use in production?
 * ✅ git revert, because it doesn’t rewrite history and is safe for shared branches.

## Q: When do you use git reset?
* Only for local commits that haven’t been pushed.

## 🟢 Scenario : Your PR is approved but shows merge conflicts
### Problem: Your branch is outdated compared to main.
 * Solution: Update your branch with `latest changes`.
```hcl
git checkout feature/login
git pull origin main
```
 * Resolve conflicts → commit → push again.
 * Key Interview Point: Conflicts should be resolved in the feature branch, not in main.

## 🟢 Scenario : You want to contribute to an open-source project
 ### Problem: You don’t have write access.
 * Solution Workflow:
```hcl
Fork repository
Clone your fork
Create branch
Commit changes
Open Pull Request
```

## 🟢 Scenario : You accidentally committed a .env file
#### Problem: Sensitive data pushed to GitHub.
 * Solution: Remove file and Add to **.gitignore**
```hcl
git rm --cached .env
```

## 🟢 Scenario 10: You want deployments only after PR merge
#### Problem: Prevent direct deploys from feature branches.
 * Solution: Configure GitHub Actions to trigger on `main only`.
```hcl
on:
  push:
    branches:
      - main
```
* Interview Gold Line:  “We deploy only reviewed and merged code.”

# 🌿 Feature Branches 
## ✅ What is a Feature Branch?
 * A feature branch is a temporary branch created from the `main codebase` to develop a specific feature, bug fix, or change without impacting production code.

## 🔐 Managing a Private Repository (DevOps View)
### ✅ What is a Private Repository?
 * A private repository is a GitHub repo where only invited users can view or contribute to the code.

---

## ⚡ Scenario-Based Git & GitHub — Rapid Fire Q&A
| 🔢 Q#   | ❓ Question                                                    | 💡 Answer                                                                               |
| ------- | ------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| 🔹 Q1   | Developer accidentally committed wrong code — what do you do? | 👉 Use: <br><br> git revert <commit-id> <br><br> or reset if not pushed.                |
| 🔹 Q2   | Difference between revert and reset?                          | 👉 git revert → Creates new commit to undo changes <br> 👉 git reset → Moves HEAD (current branch) backward |
| 🔹 Q3   | Accidentally pushed sensitive data to GitHub — action?        | 👉 Remove commit history, rotate secrets immediately.                                   |
| 🌿 Q4   | Two developers working on same feature — best practice?       | 👉 `Use separate feature branches + Pull Requests.`                                       |
| 🌿 Q5   | Main branch broken after merge — what do you do?              | 👉 `Rollback/revert immediately.`                                                         |
| 🌿 Q6   | Why use branch protection rules?                              | 👉 `Prevent direct pushes and enforce reviews/checks.`                                    |
| ⚔️ Q7   | What causes merge conflicts?                                  | 👉 `Same lines modified in different branches.`                                           |
| ⚔️ Q8   | How to resolve merge conflict?                                | 👉 Edit conflicted files → stage → commit.                                              |
| ⚔️ Q9   | Command to see conflict status?                               | 👉 `git status `                                                                          |
| 🔀 Q10  | PR failing CI pipeline — what do you do?                      | 👉 `Check logs, fix code, push again. `                                                   |
| 🔀 Q11  | Why mandatory PR reviews?                                     | 👉 `Code quality and peer validation. `                                                   |
| 🚀 Q12  | Hotfix needed in production — approach?                       | 👉 Create hotfix branch from `main → patch → PR → merge. `                                |
| 🚀 Q13  | Wrong code deployed from GitHub Actions — what next?          | 👉 `Rollback deployment + identify bad commit.    `                                       |
| 🛠️ Q14 | Undo last local commit but keep changes?                      | 👉 `git reset --soft HEAD~1 `                                                             |
| 👥 Q17  | Another developer force-pushed branch — impact?               | 👉 History rewritten; others may face `sync issues`.                                      |
| 👥 Q18  | Why avoid force push on shared branches?                      | 👉 Can `overwrite teammates’ work`.                                                       |
| ⚙️ Q19  | What happens when code pushed to GitHub?                      | 👉 `CI/CD pipeline may trigger automatically`.                                            |
| ⚙️ Q20  | Why use GitHub Actions?                                       | 👉 Automate `build`, `test`, `deploy workflows`.                                        |
| ⚙️ Q21  | Pipeline passing locally but failing in CI — why?             | 👉 Environment differences/dependency mismatch.                                         |
| 🔐 Q22  | How to secure GitHub repositories?                            | Branch protection <br> Secrets management <br> MFA <br> Least privilege access       |
| 🔐 Q23  | Where should secrets be stored?                               | 👉 GitHub Secrets (not in code).                                                        |
| 🌿 Q24  | What is GitOps?                                               | 👉 Git as single source of truth for `infrastructure/apps`.                               |
| 🌿 Q25  | How rollback happens in GitOps?                               | 👉 `Revert Git commit`.                                                                   |
| 🏢 Q26  | Multiple environments in GitHub — how manage?                 | 👉 `Separate branches/repos/folders. `                                                    |
| 🏢 Q27  | Why use CODEOWNERS?                                           | 👉 Automatic reviewer assignment.                                                       |
| 🛠️ Q28 | Git pull rejected — why?                                      | 👉` Local changes conflict with remote. `                                                 |
| 🛠️ Q29 | Detached HEAD state means?                                    | 👉 Not on active branch.                                                                |
| 🛠️ Q30 | Repository becoming huge — reasons?                           | 👉 `Large binaries/logs committed.`                                                       |
| ☸️ Q31  | Argo CD showing OutOfSync — what do you check?                | 👉 `Git repo vs cluster manifests`.                                                       |
| ☸️ Q32  | Why store Kubernetes YAML in GitHub?                          | 👉 Version control + GitOps automation.                                                 |
| 🚨 Q33  | Developer directly pushed to main — prevention?               | 👉 `Branch protection rules. `                                                            |
| 🚨 Q35  | Accidental deletion of branch — recovery?                     | 👉 Restore using commit history/reflog.                                                 |
| 🔄 Q36  | Rebase vs merge?                                              | Merge preserves history <br> Rebase creates cleaner linear history                   |
| 🔄 Q37  | Why use squash merge?                                         | 👉 Cleaner commit history.                                                              |
| 🏢 Q38  | Why use self-hosted runners?                                  | 👉 Custom environment/control.                                                          |
| 🏆 Q40  | Best Git workflow for DevOps team?                            | 👉 Feature branches + PR reviews + CI/CD + protected main.                              |

