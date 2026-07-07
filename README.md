# 🌳 Git vs GitHub
## 🛠️ Git
 * ➡️ A tool used for `version control`
 * ➡️ `Tracks file changes` and `manages project history locally`

## ☁️ GitHub
 * ➡️ `A website/platform` that stores Git repositories online
 * ➡️ Helps developers collaborate, review code, and automate deployments
 * 💡 “I use Git for clean history management with branches and commits, and GitHub for collaboration, reviews, and automated deployments.”

### 📘 Beginner-Friendly Git Vocabulary (Local Version Control)
| 🌟 Term                         | 📖 Meaning                                                                                    |
| ------------------------------- | --------------------------------------------------------------------------------------------- |
| 🔧 **Git**                      | A `version control system` that tracks changes in files                                         |
| 📁 **Repository (Repo)**        | A project folder where `Git tracks project files`                                               |
| 🖊️ **Working Directory**        | Your project folder `where you edit files` ➡️ File is modified but not saved in Git history yet |
| 📦 **Staging Area (`git add`)** | Temporary area where `selected changes wait before commit  `                                    |
| 💾 **Commit**                   | A saved snapshot of changes with a message ➡️ *(`Save version`)*                                |
| 🆔 **Commit ID / Hash**         | `Unique ID` that identifies a commit                                                            |
| 🕒 **Version Control**          | System to track file changes over time                                                        |
| 🌿 **Branch**                   | A separate line of development *(Like working on `dev`, not the `prod`)*                     |
| 👑 **Master / Main**            | Default branch of the project                                                                 |
| 📍 **HEAD**                     | Pointer to the `latest commit of the current branch` 👉 “You are currently here.”               |
| 📥 **Clone**                    | Copy a repository from `remote to local  `                                                      |
| 🔄 **Checkout**                 | Switch between `branches` or `commits`                                                            |
| 🧩 **Merge**                    | `Combine changes from one branch into another` *(Final document)*                               |
| ⚠️ **Merge Conflict**           | ✍️ Two people edited the same line ➡️ You manually decide which version to keep               |
| 🚚 **Rebase**                   | Move commits onto another branch’s base  (combines changes from `one branch` into `another` by moving your commits)    |
| ❗ **Conflict**                  | When Git `can’t automatically merge changes `                                                   |
| 🔍 **Diff**                     | Shows differences between files or commits                                                    |
| 📜 **Log**                      | History of commits                                                                            |
| 📊 **Status**                   | Shows file states *(modified, staged, etc.)*                                                  |
| 🧳 **Stash**                    | Temporarily save uncommitted changes ➡️ *(`Pause work → Resume later`)*                         |
| ⏪ **Reset**                     | Undo commits or unstage files ⚠️ *(Can erase history)*                                        |
| 🔙 **Revert**                   | Create a new commit to` undo a previous commit` *(Keeps history safe)*                          |
| 🏷️ **Tag**                     | Mark a specific commit *(Example:` Release v1.0`)*                                              |

### 📘 Git File States
| 📂 State         | 📖 Meaning                    |
| ---------------- | ------------------------------ |
| 🆕 **Untracked** | File not yet tracked by Git    |
| 👀 **Tracked**   | File under Git version control |
| ✏️ **Modified**  | File changed but not staged    |
| 📌 **Staged**    | File added to staging area     |
| ✅ **Committed**  | Changes permanently saved     |

### ☁️ Beginner-Friendly GitHub Vocabulary (Remote Collaboration)
| 🌟 Term                    | 📖 Meaning                                     |
| -------------------------- | ---------------------------------------------- |
| ☁️ **GitHub**              | GitHub is a web-based platform that allows you to create, store, and teams to collaborate on `files or code`.    |
| 🌍 **Remote Repository**   | Repo stored on `GitHub `                         |
| 🎯 **Origin**              | Default name of the `remote repository   `       |
| ⬆️ **Push**                |` Upload local commits to GitHub      `           |
| ⬇️ **Pull**                | `Download latest changes` from GitHub            |
| 🔀 **Pull Request (PR)**   | Request to `merge changes into another branch`   |
| 🍴 **Fork**                | `Copy` someone else’s repository to your account |
| 📥 **Clone (`git clone`)** | Download the `entire project with history`       |
| 🐞 **Issue**               | Task, bug, or feature request                  |
| 🤖 **Actions**             | `CI/CD automation in GitHub`                     |
| ⚙️ **Workflow**            | Steps defined for GitHub Actions               |
| 📦 **Release**             | Packaged version of the project                |
| 📘 **README.md**           | Project description and instructions           |
| 📜 **License**             | Rules for using the code                       |
| 👨‍💻 **Contributor**        | Person who contributes code                    |
| 🤝 **Collaborator**        | User with repository write access              |
| ⭐ **Stars**                | Bookmark or appreciation                       |
| 👀 **Watch**               | Get repository notifications                   |
| 🏢 **Organizations**       | `Group accounts` for `teams/projects`            |

---

<img width="1920" height="2400" alt="InShot_20260707_121421496 jpg" src="https://github.com/user-attachments/assets/8b6a9dbf-1f8a-4dbe-b05e-d16cce720106" />

## 🚀 Popular Git Commands — When to Use
| 💻 **Git Command** | 🎯 **When to Use**                    | 💡 **Purpose**                               | 📝 **Example**                      |
| ------------------ | --------------------------------------- | -------------------------------------------- | ----------------------------------- |
| `git clone`        | 📥 First time working on a project      | Download a remote repository                 | `git clone <repo-url>`              |
| `git checkout -b`  | 🌿 Start a new feature                  | Create and switch to a new branch            | `git checkout -b feature/login`     |
| `git status`       | 🔍 Check current changes                | View modified, staged, and untracked files   | `git status`                        |
| `git add`          | ➕ Prepare files for commit             | Stage changes                                | `git add .`                         |
| `git commit`       | 💾 Save changes locally                 | Create a commit with a message               | `git commit -m "Add login feature"` |
| `git push`         | ⬆️ Share your changes                   | Upload commits to the remote repository      | `git push origin feature/login`     |
| `git pull`         | ⬇️ Get the latest changes               | Fetch and merge remote changes               | `git pull origin main`              |
| `git fetch`        | 📥 Check remote updates without merging | Download latest commits only                 | `git fetch origin`                  |
| `git merge`        | 🔀 Combine branches                     | Merge another branch into the current branch | `git merge feature/login`           |
| `git rebase`       | 📚 Clean commit history                 | Replay commits on top of another branch      | `git rebase main`                   |
| `git revert`       | ↩️ Undo a pushed commit                 | Create a new commit that reverses changes    | `git revert <commit-id>`            |
| `git reset`        | ⏪ Undo local commits                   | Move the branch pointer to an earlier commit | `git reset --soft HEAD~1`           |
| `git log`          | View commit history                     | Show commit history                          | `git log --oneline`                 |
| `git diff`         | Compare changes                         | View differences between files or commits    | `git diff`                          |
| `git stash`        | 📦 Temporarily save work                | Store uncommitted changes                    | `git stash`                         |
| `git stash pop`    | Restore saved work                      | Apply the latest stashed changes             | `git stash pop`                     |
| `git branch`       | Manage branches                         | List or create branches                      | `git branch`                        |
| `git remote -v`    |  Verify remote repository               | Display remote URLs                          | `git remote -v`                     |
| `git tag`          |  📜 Mark releases                       | Create version tags                          | `git tag v1.0.0`                    |
