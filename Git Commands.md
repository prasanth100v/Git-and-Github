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
| `git restore file` | Discard file changes            | `git restore config.yml` |
| `git rm file`      | Delete file from repo           | `git rm old.txt`         |

### Commit Commands
| Command             | Explanation                | Example                          |
| ------------------- | -------------------------- | -------------------------------- |
| `git commit -m`     | Commit staged changes      | `git commit -m "Initial commit"` |
| `git commit -am`    | Add + commit tracked files | `git commit -am "Bug fix"`       |
| `git log`           | Show commit history        | `git log`                        |
| `git log --oneline` | Short commit history       | `git log --oneline`              |

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
| `git remote add` | Add remote repo       | `git remote add origin https://github.com/user/repo.git` |
| `git push`       | Push code to remote   | `git push origin main`                                   |
| `git pull`       | Fetch + merge         | `git pull origin main`                                   |
| `git fetch`      | Download changes only | `git fetch origin`                                       |
| `git clone`      | Copy remote repo      | `git clone https://github.com/user/repo.git`             |

### Undo & Fix Commands ⚠️
| Command            | Explanation                  | Example                   |
| ------------------ | ---------------------------- | ------------------------- |
| `git reset file`   | Unstage file                 | `git reset app.py`        |
| `git reset --soft` | Undo commit (keep changes)   | `git reset --soft HEAD~1` |
| `git reset --hard` | Undo commit (delete changes) | `git reset --hard HEAD~1` |
| `git revert`       | Undo commit safely           | `git revert a1b2c3d`      |

### Stash Commands
| Command           | Explanation           | Example           |
| ----------------- | --------------------- | ----------------- |
| `git stash`       | Save uncommitted work | `git stash`       |
| `git stash list`  | View stash list       | `git stash list`  |
| `git stash apply` | Apply last stash      | `git stash apply` |
| `git stash drop`  | Delete stash          | `git stash drop`  |

### Compare & Inspect
| Command             | Explanation              | Example             |
| ------------------- | ------------------------ | ------------------- |
| `git diff`          | Show changes             | `git diff`          |
| `git diff --staged` | Compare staged changes   | `git diff --staged` |
| `git show`          | Show commit details      | `git show a1b2c3d`  |
| `git blame`         | Line-by-line author info | `git blame app.py`  |

### Advanced Useful Commands
| Command           | Explanation            | Example                   |
| ----------------- | ---------------------- | ------------------------- |
| `git rebase`      | Reapply commits        | `git rebase main`         |
| `git cherry-pick` | Apply specific commit  | `git cherry-pick a1b2c3d` |
| `git tag`         | Create version tag     | `git tag v1.0`            |
| `git clean -f`    | Delete untracked files | `git clean -f`            |





