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



When you run: **git push origin master** Git asks for ***username and token*
### ✅ Why this happens
> Your remote URL is HTTPS (not SSH)
Git now requires a Personal Access Token (PAT) instead of a password
### ✅ Correct way to push using HTTPS
 Create a GitHub Personal Access Token (PAT)
```
Go to GitHub → Settings
Developer settings
Personal access tokens
Tokens (classic) → Generate new token
Select scopes:
☑ repo
Generate token and COPY it (you won’t see it again)
```
When prompted:
```
Username: your_github_username
Password: PASTE_YOUR_TOKEN_HERE
```




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
```
git tag -a v1.0.1 <commit-hash> -m "Hotfix release"
```
### 🚀 Push tags to remote (IMPORTANT)
Push single tag
```
git push origin v1.0.0
```
Push all tags
```
git push origin --tags
```

🧪 Real release workflow (best practice)
```
git checkout main
git pull origin main
git tag -a v2.0.0 -m "Stable production release"
git push origin v2.0.0
```
