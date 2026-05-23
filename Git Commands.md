# Git Commands
### Basic Git Commands
| Command                          | Explanation                   | Example                                        |
| -------------------------------- | ----------------------------- | ---------------------------------------------- |
| `git --version`                  | Check installed Git version   | `git --version`                                |
| `git config --global user.name`  | Set Git username              | `git config --global user.name "Prasanth"`     |
| `git config --global user.email` | Set Git email                 | `git config --global user.email "p@gmail.com"` |
| `git config --list`              | Displays all the Git configuration settings    | `git config --list`           |
| `git init`                       | Initialize new Git repository | `git init myproject`                           |
| `git status`                     | Show current repo status      | `git status`                                   |

### File & Staging Commands
| Command            | Explanation                     | Example                  |
| ------------------ | ------------------------------- | ------------------------ |
| `git add file`     | Stage a specific file           | `git add app.py`         |
| `git add .`        | Stage **all files recursively** | `git add .`              |
| `git restore file` | undo changes in your working directory | `git restore config.yml` |
| `git rm file`      | Delete file from repo           | `git rm old.txt`         |

### Commit Commands
| Command             | Explanation                | Example                          |
| ------------------- | -------------------------- | -------------------------------- |
| `git commit -m`     | Commit staged changes      | `git commit -m "Initial commit"` |
| `git commit -am`    | Add + commit tracked files | `git commit -am "Bug fix"`       |
| `git log`           | Show commit history        | `git log`                        |
| `git log --oneline` | Short commit history       | `git log --oneline`              |
| `git log -5`        | Show Last 5 commits        | `git log -5`                     |
| `git log --author`  | commit history By author   | `git log --author`               |
	
### Branching Commands
| Command               | Explanation            | Example                    |
| --------------------- | ---------------------- | -------------------------- |
| `git branch`          | List branches          | `git branch`               |
| `git branch new`      | Create new branch      | `git branch dev`           |
| `git checkout branch` | Switch branch          | `git checkout dev`         |
| `git checkout -b`     | Create & switch branch | `git checkout -b feature1` |
| `git merge branch`    | Merge branch           | `git merge dev`            |
| `git branch -d`       | Delete branch          | `git branch -d dev`        |

### Remote Repository (GitHub)
| Command          | Explanation           | Example                                                  |
| ---------------- | --------------------- | -------------------------------------------------------- |
| `git remote -v`  | Show remote URLs      | `git remote -v`                                          |
| `git remote add` | Add remote repo  (want to push your code to a new GitHub repo) | `git remote add origin https://github.com/user/repo.git` |
| `git push`       | Push code to remote   | `git push origin main`                                   |
| `git pull`       | Fetch + merge         | `git pull origin main`                                   |
| `git fetch`      | Download changes only | `git fetch origin`                                       |
| `git clone`      | Copy remote repo      | `git clone https://github.com/user/repo.git`             |
| `git ssh remote add` | Add remote repo  (push your code to a new GitHub repo) | `git remote set-url origin git@github.com:username/repo.git` |
| `Before push`    |Before pushing, verify the ssh connection     | `ssh -T git@github.com`             |

---

### username and token
 * When you run: **git push origin master** Git asks for ***username and token*
 * ✅ Why this happens :
    * Your remote URL is HTTPS (`not SSH`)
    * Git now requires a `Personal Access Token` (PAT) `instead of a password`

### ✅ Correct way to push using HTTPS
* Create a GitHub Personal Access Token (`PAT`)
```hcl
1. Go to GitHub → Settings
2. Developer settings
3. Personal access tokens
4. Tokens (classic) → Generate new token
5. Select scopes:
     ☑ repo
6. Generate token and COPY it (you won’t see it again)
```
When prompted:
```hcl
Username: your_github_username
Password: PASTE_YOUR_TOKEN_HERE
```

---

### Undo & Fix Commands ⚠️ (Undo the last commit)
| Command            | Explanation                  | Example                   |
| ------------------ | ---------------------------- | ------------------------- |
| `git reset file`   | Unstage file                 | `git reset app.py`        |
| `git reset --soft` | Undo commit (keep changes)   | `git reset --soft HEAD~1` |
| `git reset --hard` | Undo commit (delete changes) | `git reset --hard HEAD~1` |
| `git revert`       | Undo commit safely           | `git revert a1b2c3d`      |

### Stash Commands
> git stash is your "digital shelf." It allows you to temporarily set aside (shelve) your current uncommitted changes so you can work on something else, and then come back and reapply them later.

| Command           | Explanation           | Example           |
| ----------------- | --------------------- | ----------------- |
| `git stash`       | Save uncommitted work | `git stash`       |
| `git stash list`  | View stash list       | `git stash list`  |
| `git stash apply` | Apply last stash      | `git stash apply` |
| `git stash drop`  | Delete stash          | `git stash drop`  |

### Compare & Inspect
| Command             | Explanation              | Example             |
| ------------------- | ------------------------ | ------------------- |
| `git diff`          | Show changes ( Working Directory vs. Staging Area ) | `git diff`          |
| `git diff --staged` | Compare staged changes (Staging Area vs. Last Commit)  | `git diff --staged` |
| `git show`          | Show commit details      | `git show a1b2c3d`  |
| `git blame`         | Line-by-line author info | `git blame app.py`  |
| `git diff HEAD` | Working Directory vs. Last Commit (Staged + Unstaged changes).  | `git diff HEAD` |
| `git diff <branch1> <branch2>` | Differences between two entire branches. |  `git diff <branch1> <branch2>` |

### Advanced Useful Commands
| Command           | Explanation            | Example                   |
| ----------------- | ---------------------- | ------------------------- |
| `git rebase`      | Update your branch with latest main  | `git rebase main`    |
| `🍒 git cherry-pick` | copy a specific commit from one branch and apply it onto another branch  | `git cherry-pick a1b2c3d` |
| `git tag`         | Create version tag (A tag is like a bookmark in Git history 📌)     | `git tag v1.0`            |
| `git clean -f`    | Delete untracked files | `git clean -f`            |


### 📌 Tag a specific commit
```hcl
git tag -a v1.0.1 <commit-hash> -m "Hotfix release"
```
### 🚀 Push tags to remote (IMPORTANT)
Push single tag
```hcl
git push origin v1.0.0
```
Push all tags
```hcl
git push origin --tags
```

🧪 Real release workflow (best practice)
```hcl
1. git checkout main
2. git pull origin main
3. git tag -a v2.0.0 -m "Stable production release"
4. git push origin v2.0.0
```

---

## 🌿 Git Commands — Full Rapid Fire Interview Q&A

| 🔢 Q#  | ❓ Question                                                  | 💡 Answer                                                                                                                        |
| ------ | ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| 🔹 Q1  | Command to check Git version?                                 | 👉 `git --version `                                                                                                                |
| 🔹 Q2  | Command to configure Git username?                            | 👉 `git config --global user.name "Prasanth"`                                                                                      |
| 🔹 Q3  | Command to configure Git email?                               | 👉 `git config --global user.email "(prasanth100@gmail.com)" `                                                           |
| 🔹 Q4  | Command to list Git configuration?                            | 👉 `git config --list `                                                                                                            |
| 🔹 Q5  | Purpose of git init?                                          | 👉 `Initialize a new Git repository.  `                                                                                            |
| 🔹 Q6  | Command to initialize repository?                             | 👉 `git init myproject`                                                                                                            |
| 🔹 Q7  | Purpose of git status?                                        | 👉 Shows repository status.                                                                                                      |
| 🔹 Q8  | What does git status display?                                 |  Modified files <br> Staged files <br> Untracked files <br> Current branch                                                     |
| 📂 Q9  | Command to stage a specific file?                             | 👉 `git add app.py  `                                                                                                              |
| 📂 Q10 | Command to stage all files?                                   | 👉` git add .   `                                                                                                                  |
| 📂 Q11 | What does git add . do?                                       | 👉 `Stages all files recursively. `                                                                                                |
| 📂 Q12 | Purpose of staging area?                                      | 👉 `Temporary area before commit. `                                                                                                |
| 📂 Q13 | Command to undo working directory changes?                    | 👉 `git restore config.yml  `                                                                                                      |
| 📂 Q14 | Purpose of git restore?                                       | 👉 `Restore file to last committed state.  `                                                                                       |
| 📂 Q15 | Command to delete file from Git repo?                         | 👉 `git rm old.txt  `                                                                                                              |
| 📸 Q16 | Command to create commit?                                     | 👉 git commit -m "Initial commit"                                                                                                |
| 📸 Q17 | Meaning of -m in commit?                                      | 👉 `Commit message.`                                                                                                               |
| 📸 Q18 | What does git commit -am do?                                  | 👉 `Add tracked files + commit.`                                                                                                   |
| 📸 Q19 | Command for short commit history?                             | 👉 `git log --oneline     `                                                                                                        |
| 📸 Q20 | Command to show last 5 commits?                               | 👉 `git log -5  `                                                                                                                  |
| 📸 Q21 | Command to filter commits by author?                          | 👉 `git log --author`                                                                                                              |
| 📸 Q22 | Purpose of git log?                                           | 👉 `Shows commit history.  `                                                                                                       |
| 🌿 Q23 | Command to list branches?                                     | 👉 `git branch `                                                                                                                   |
| 🌿 Q24 | Command to create branch?                                     | 👉 `git branch dev`                                                                                                                |
| 🌿 Q25 | Command to switch branch?                                     | 👉 `git checkout dev   `                                                                                                           |
| 🌿 Q26 | Command to create and switch branch?                          | 👉 `git checkout -b feature1  `                                                                                                    |
| 🌿 Q27 | Command to merge branch?                                      | 👉 `git merge dev  `                                                                                                               |
| 🌿 Q28 | Command to delete branch?                                     | 👉 `git branch -d dev  `                                                                                                           |
| 🌿 Q29 | Why use branches?                                             | 👉 Isolate development safely.                                                                                                   |
| ☁️ Q30 | Command to show remote URLs?                                  | 👉 `git remote -v     `                                                                                                            |
| ☁️ Q31 | Command to add remote repository?                             | 👉 git remote add origin` [https://github.com/user/repo.git](https://github.com/user/repo.git)     `                               |
| ☁️ Q32 | Command to push code?                                         | 👉 `git push origin main    `                                                                                                      |
| ☁️ Q33 | Command to pull latest changes?                               | 👉 `git pull origin main   `                                                                                                       |
| ☁️ Q34 | What does git pull do?                                        | 👉` Fetch + merge. `                                                                                                               |
| ☁️ Q35 | Command to fetch only?                                        | 👉 `git fetch origin ` (download commits, files)                                                                                 |
| ☁️ Q36 | Difference between pull and fetch?                            | 👉 Pull = `fetch + merge`, fetch = `download only.   `                                                                               |
| ☁️ Q37 | Command to clone repository?                                  | 👉 `git clone [https://github.com/user/repo.git](https://github.com/user/repo.git) `                                               |
| ☁️ Q38 | SSH remote URL format?                                        | 👉 `[git@github.com](mailto:git@github.com):user/repo.git    `                                                                     |
| ☁️ Q39 | Command to switch HTTPS remote to SSH?                        | 👉 `git remote set-url origin [git@github.com](mailto:git@github.com):username/repo.git   `                                        |
| ☁️ Q40 | Command to verify GitHub SSH connection?                      | 👉 `ssh -T [git@github.com](mailto:git@github.com)    `                                                                            |
| 🔐 Q41 | Why does Git ask for username/token during push?              | 👉 `Remote URL uses HTTPS.  `                                                                                                      |
| 🔐 Q42 | What replaced GitHub password authentication?                 | 👉 `Personal Access Token (PAT).`                                                                                                  |
| ↩️ Q46 | Command to unstage file?                                      | 👉 git reset app.py                                                                                                              |
| ↩️ Q47 | Command to undo commit but keep changes?                      | 👉 `git reset --soft HEAD~1    `                                                                                                   |
| ↩️ Q48 | Command to undo commit and delete changes?                    | 👉 `git reset --hard HEAD~1   `                                                                                                    |
| ⚠️ Q49 | Why is reset --hard dangerous?                                | 👉 `Deletes changes permanently.`                                                                                                  |
| ↩️ Q50 | Command for safe rollback?                                    | 👉 `git revert a1b2c3d  `                                                                                                          |
| ↩️ Q51 | Why is revert safer?                                          | 👉 `Creates new commit without rewriting history.  `                                                                               |
| 📦 Q52 | What is git stash?                                            | 👉 Temporary storage for uncommitted work.                                                                                       |
| 📦 Q53 | Command to save uncommitted changes?                          | 👉 `git stash`                                                                                                                     |
| 📦 Q54 | Command to list stashes?                                      | 👉 `git stash list  `                                                                                                              |
| 📦 Q55 | Command to apply stash?                                       | 👉 `git stash apply    `                                                                                                           |
| 📦 Q56 | Command to remove stash?                                      | 👉 `git stash drop  `                                                                                                              |
| 📦 Q57 | Why use stash?                                                | 👉 `Switch tasks without committing incomplete work.   `                                                                           |
| 🔍 Q58 | Purpose of git diff?                                          | 👉 `Show unstaged changes. `                                                                                                       |
| 🔍 Q59 | Command to compare staged changes?                            | 👉 `git diff --staged `                                                                                                            |
| 🔍 Q60 | Command to compare with last commit?                          | 👉 `git diff HEAD `                                                                                                                |
| 🔍 Q61 | Command to compare two branches?                              | 👉 `git diff branch1 branch2  `                                                                                                    |
| 🔍 Q62 | Command to show commit details?                               | 👉 `git show a1b2c3d`                                                                                                              |
| 🔍 Q63 | Purpose of git blame?                                         | 👉 `Shows line-by-line author info.   `                                                                                            |
| 🔍 Q64 | Command for line ownership?                                   | 👉 git blame app.py                                                                                                              |
| 🚀 Q65 | Purpose of git rebase?                                        | 👉 Update branch with latest main cleanly.                                                                                       |
| 🚀 Q66 | Command for rebase?                                           | 👉 git rebase main                                                                                                               |
| 🚀 Q67 | What is cherry-pick?                                          | 👉 `Copy specific commit to another branch.   `                                                                                    |
| 🚀 Q68 | Command for cherry-pick?                                      | 👉 git cherry-pick a1b2c3d                                                                                                       |
| 🚀 Q69 | What is Git tag?                                              | 👉 Bookmark/version `label in Git history`.                                                                                        |
| 🚀 Q70 | Command to create tag?                                        | 👉 `git tag v1.0   `                                                                                                               |
| 🚀 Q71 | Command to create annotated tag?                              | 👉 git tag -a v1.0.1 <commit-hash> -m "Hotfix release"                                                                           |
| 🚀 Q72 | Command to push single tag?                                   | 👉 `git push origin v1.0.0 `                                                                                                       |
| 🚀 Q73 | Command to push all tags?                                     | 👉 `git push origin --tags `                                                                                                       |
| 🚀 Q74 | Purpose of git clean -f?                                      | 👉 Delete untracked files.                                                                                                       |
| 📦 Q75 | Example production release workflow?                          | git checkout main <br> git pull origin main <br> git tag -a v2.0.0 -m "Stable production release" <br> git push origin v2.0.0 |
| 📦 Q76 | Why use Git tags in production?                               | 👉 Identify stable releases easily.                                                                                              |
| 📦 Q77 | Common tag naming style?                                      | 👉 v1.0.0                                                                                                                        |
| 🎯 Q78 | You accidentally staged wrong file. What do you use?          | 👉 git reset file                                                                                                                |
| 🎯 Q79 | You want temporary save without commit. What do you use?      | 👉 git stash                                                                                                                     |
| 🎯 Q80 | You want clean release point in history. What do you use?     | 👉 Git tags.                                                                                                                     |
| 🎯 Q81 | You want to inspect who changed a line. What command?         | 👉 git blame                                                                                                                     |
| 🎯 Q82 | You want latest remote changes without merging. What command? | 👉 git fetch                                                                                                                     |
 
