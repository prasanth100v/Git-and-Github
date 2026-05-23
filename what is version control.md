# What is version control?
 * Version control is a system that tracks changes to files over time, so you can see what changed, who changed it, and roll back if needed.
 * Key capabilities :
    * 📌 Track every change (`line by line`)
    * 👥 Multiple developers work together safely
    * ⏪ Roll back to any previous version
    * 🌿 Work on branches separately
    * 🔍 See who changed what and why

# What is a commit?
 * A commit is : A `snapshot of your project` at a point in time
 * 📌 Each commit represents a `version of the code` with `author`, `timestamp`, and `message`.
 * 📌 Each commit = `one version of your code`.

Example:
```hcl
Commit 1: Added login page
Commit 2: Fixed login bug
Commit 3: Improved UI
```
### 👉 Version control = history
### 👉 Commit = one saved point in that history

## See the history 
```hcl
git log
```
### (green = added, red = removed)
 * 📌 This shows: All commits, Who made them, When they were made and Commit messages
 * If you can see `commits` and their `history`, you are `seeing version control`.

## See what changed in a version:
```hcl
git show a1b2c3
```

## See differences between versions and (between two commits)
```hcl
git diff
git diff d4e5f6 a1b2c3
```
 
⭐ One-line definition (memorize this)
> 🌿 Version control is the backbone of modern software development that manages code changes, collaboration, and stability.

# Rollback
 * 📌 Moving from recently updated code back to previous code is called a version control operation.
 * 📌 In Git, this is done using `rollback`, `revert`, `reset`, or `checkout of commits`.
 * 📌 Rollback is the process of restoring code to a previous stable version.

## git checkout — View old code (SAFE)
 👉 Use when you just want to see or test old code
```hcl
git checkout <commit-id>
```
> What happens: Code moves to an old version

### 📌 Interview line:
Checkout is used to inspect previous commits without changing history.

## PERMANENTLY undo changes
👉 Use when wrong code is already pushed
```hcl
git revert a1b2c3
```
> What happens: Creates a new commit and That commit undoes the changes

## 📌 Interview line:
Revert is the `safest rollback method` in production because it does not `rewrite history`.

## DANGEROUS rollback (local only)
👉 Use only if not pushed to GitHub
```hcl
git reset --hard d4e5f6
```
* 👉 Deletes commits permanently
* 👉 Code goes back completely

## One-line memory trick
 * 📌 git checkout → look back [`inspect previous versions`]
 * 📌 git revert → `safely undo`
 * 📌 git reset → force undo (`dangerous`)

---

## 🌿 Git & Version Control — Rapid Fire Interview Questions & Answers
| 🔢 Q#  | ❓ Question                                            | 💡 Answer                                                                                                   |
| ------ | ----------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| 🔹 Q1  | What is version control?                              | 👉 A system that `tracks file changes over time`.                                                            |
| 🔹 Q2  | Why is version control important?                     | 👉 Helps `collaboration`, `rollback`, and `tracking changes`.                                                |
| 🔹 Q3  | Main advantages of version control?                   | 👉 ✅ Track changes <br> ✅ Team collaboration <br> ✅ Rollback support <br> ✅ Branching <br> ✅ Change history |
| 🔹 Q4  | What does version control track?                      | 👉 Who changed `what`, `when`, and `why`.                                                                         |
| 🔹 Q5  | One-line definition of version control?               | 👉 Manages `code changes`, `collaboration`, and `stability`.                                                      |
| 🔹 Q6  | Which tool is most commonly used for version control? | 👉 `Git`                                                                                                      |
| 🔹 Q7  | Difference between Git and GitHub?                    | 👉 Git is a version control tool; GitHub stores `Git repositories online`.                                    |
| 🔹 Q8  | What is a repository?                                 | 👉 A `storage location for project code` and `history`.                                                         |
| 🔹 Q9  | What is a local repository?                           | 👉 Repository stored `on your machine`.                                                                       |
| 🔹 Q10 | What is a remote repository?                          | 👉 Repository hosted on platforms like `GitHub`.                                                              |
| 📸 Q11 | What is a commit?                                     | 👉 `A snapshot of project code at a specific time`.                                                           |
| 📸 Q12 | What information does a commit contain?               | 👉 `Author` <br> `Timestamp` <br> `Commit message` <br> `Code changes `                                     |
| 📸 Q13 | Why are commits important?                            | 👉 They create project history.                                                                             |
| 📸 Q14 | One commit represents what?                           | 👉 `One version of the code`.                                                                                 |
| 📸 Q15 | Example of commit messages?                           | 👉 Added login page <br> Fixed login bug <br> Improved UI                                                   |
| 📸 Q16 | Best practice for commit messages?                    | 👉 Clear and meaningful messages.                                                                           |
| 📸 Q17 | Command to create a commit?                           | 👉 `git commit -m "message"  `                                                                                |
| 📸 Q18 | What does -m mean in git commit?                      | 👉 Commit message.                                                                                          |
| 📜 Q19 | Command to view commit history?                       | 👉 `git log`                                                                                                  |
| 📜 Q20 | What does git log show?                               | 👉 `Commits`, `authors`, `dates`, and `messages`.                                                             |
| 📜 Q21 | Command to view a specific commit?                    | 👉 `git show a1b2c3`                                                                                          |
| 📜 Q22 | What does git show display?                           | 👉 Detailed changes in a commit.                                                                            |
| 📜 Q23 | Command to compare changes?                           | 👉 `git diff`                                                                                                 |
| 📜 Q24 | Command to compare two commits?                       | 👉` git diff d4e5f6 a1b2c3`                                                                                   |
| 📜 Q25 | In git diff, green lines mean?                        | 👉` Added code.`                                                                                              |
| 📜 Q26 | In git diff, red lines mean?                          | 👉 `Removed code.`                                                                                            |
| 🔄 Q27 | What is rollback in Git?                              | 👉 Restoring code to a `previous stable version`.                                                             |
| 🔄 Q28 | Common Git rollback methods?                          | 👉 git checkout <br> git revert <br> git reset                                                              |
| 🔄 Q29 | Safest rollback method in production?                 | 👉 `git revert `                                                                                              |
| 🔄 Q30 | Dangerous rollback method?                            | 👉` git reset --hard  `                                                                                       |
| 👀 Q31 | Purpose of git checkout <commit-id>?                  | 👉 `Inspect old code safely. `                                                                                |
| 👀 Q32 | Command to view old commit?                           | 👉 `git checkout <commit-id> `                                                                                |
| 👀 Q33 | Does checkout rewrite history?                        | 👉 No.                                                                                                      |
| 👀 Q34 | Interview line for checkout?                          | 👉 Used to inspect previous commits safely.                                                                 |
| 👀 Q35 | Is checkout safe for production?                      | 👉 Yes, for `viewing/testing`.                                                                                |
| ↩️ Q36 | Purpose of git revert?                                | 👉 `Safely undo changes.`                                                                                     |
| ↩️ Q37 | Command to revert a commit?                           | 👉 `git revert a1b2c3 `                                                                                       |
| ↩️ Q38 | What happens after revert?                            | 👉 Creates a new commit that undoes changes.                                                                |
| ↩️ Q39 | Does revert rewrite history?                          | 👉 `No.`                                                                                                      |
| ↩️ Q40 | Why is revert preferred in production?                | 👉 Keeps commit history intact.                                                                             |
| ↩️ Q41 | Interview line for revert?                            | 👉 `Safest rollback method because history is maintained.`                                                     |
| ⚠️ Q42 | Purpose of git reset --hard?                          | 👉 Completely `move back to old commit`.                                                                      |
| ⚠️ Q43 | Command for hard reset?                               | 👉 `git reset --hard d4e5f6  `                                                                                |
| ⚠️ Q44 | What does `hard reset do`?                            | 👉 `Deletes commits` and `changes permanently`.                                                             |
| ⚠️ Q45 | When should hard reset be `avoided`?                  | 👉 After pushing to `remote repositories.`                                                                    |
| ⚠️ Q46 | Why is reset dangerous?                               | 👉 `Rewrites history and can lose code. `                                                                     |
| ⚠️ Q47 | Best use case for reset?                              | 👉 `Local cleanup before pushing.`                                                                            |
| 🌿 Q48 | What is a branch in Git?                              | 👉 `Separate line of development.  `                                                                          |
| 🌿 Q49 | Why use branches?                                     | 👉 `Work independently without affecting main code.`                                                          |
| 🌿 Q50 | Default branch name in modern Git?                    | 👉 `main `                                                                                                    |
| 🌿 Q51 | Command to create branch?                             | 👉 `git branch feature1  `                                                                                    |
| 🌿 Q52 | Command to switch branch?                             | 👉 `git checkout feature1 `                                                                                   |
| 🌿 Q53 | Command to create and switch branch?                  | 👉 `git checkout -b feature1   `                                                                              |
| 👥 Q54 | Why is Git useful for teams?                          | 👉 Multiple developers can `work safely together`.                                                            |
| 👥 Q55 | What is merge conflict?                               | 👉 Conflict when `two changes affect same code`.                                                              |
| 👥 Q56 | What causes merge conflicts?                          | 👉 Simultaneous edits in `same lines/files.`                                                                  |
| 👥 Q57 | Command to fetch remote changes?                      | 👉 `git pull      `                                                                                           |
| 👥 Q58 | Command to send changes to remote?                    | 👉 `git push     `                                                                                            |
| 👥 Q59 | Command to clone repository?                          | 👉 `git clone <repo-url>   `                                                                                  |
| 🔄 Q60 | Git file lifecycle stages?                            | 👉 `Working Directory` <br> `Staging Area` <br> `Repository  `                                               |
| 🔄 Q61 | Command to add files to staging?                      | 👉 `git add .`                                                                                              |
| 🔄 Q62 | What is staging area?                                 | 👉 `Temporary area before commit. `                                                                           |
| 🔄 Q63 | Command to check repository status?                   | 👉 `git status  `                                                                                             |
| 🔄 Q64 | What does git status show?                            | 👉 `Modified`, `staged`, and `untracked files`.                                                             |
| 🚀 Q65 | Why is Git important in DevOps?                       | 👉 Enables `CI/CD`, `collaboration`, and `rollback`.                                                          |
| 🚀 Q66 | Git use case in deployments?                          | 👉 Roll back failed releases quickly.                                                                       |
| 🚀 Q67 | Why are commits useful in debugging?                  | 👉 `Helps identify when bugs were introduced.  `                                                              |
| 🚀 Q68 | Why use branches in DevOps?                           | 👉 `Feature isolation and safer deployments.     `                                                            |
| 🧠 Q69 | Memory trick for checkout?                            | 👉 checkout → `look back   `                                                                                  |
| 🧠 Q70 | Memory trick for revert?                              | 👉 revert → `safely undo`                                                                                     |
| 🧠 Q71 | Memory trick for reset?                               | 👉 reset → `dangerous force undo`                                                                             |

