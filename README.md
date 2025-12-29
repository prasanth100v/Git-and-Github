## Git → the tool that does version control
## GitHub → a website that stores Git projects and helps people work together

# beginner-friendly vocabulary list for Git & GitHub
## 📘 Git Vocabulary (Local Version Control)
| Term                  | Meaning                                                  |
| --------------------- | -------------------------------------------------------- |
| **Git**               | A version control system that tracks changes in files    |
| **Repository (repo)** | 📁 A project folder where Git tracks project files       |
| **Working Directory** | Your project folder where you edit files  ➡️ File is modified but not saved in Git history yet.|
| **Staging Area** (git add) | Temporary area where selected changes (files) wait before commit |
| **Commit**            | A saved snapshot of changes with a message  (Save version)    |
| **Commit ID / Hash**  | Unique ID that identifies a commit                       |
| **Version Control**   | System to track file changes over time                   |
| **Branch**            | A separate line of development ( Like working on a photocopy, not the original. )  |
| **Master / Main**     | Default branch of the project                            |
| **HEAD**              | Pointer to the current branch/commit                     |
| **Clone**             | Copy a repository from remote to local                   |
| **Checkout**          | Switch between branches or commits                       |
| **Merge**             | Combine changes from one branch into another (final document) **PR approved 🎉 ➡️ 🧩 Feature is added to main code.**|
| **Merge Conflict**    | ✍️ Two people editing the same sentence. ➡️ (“Which one is correct?” You decide manually, then commit.)  |
| **Rebase**            | Move commits onto another branch’s base                  |
| **Conflict**          | When Git can’t auto-merge changes                        |
| **Diff**              | Shows differences between files/commits                  |
| **Log**               | History of commits                                       |
| **Status**            | Shows file states (modified, staged, etc.)               |
| **Stash**             | Temporarily save uncommitted changes  🧳 Work is saved temporarily.  **(Pause work  ➡️ Resume later)**  |
| **Reset**             | ⏪ Undo commits or unstage files   **Careful: can erase history**  |
| **Revert**            | 🔙 Create a new commit to undo a previous commit   **Doesn’t delete history**  |
| **Tag**               | Mark a specific commit (often for releases)  **Sticker on a box: “Release v1.0”** |

## 📘 Git File States
| State         | Meaning                        |
| ------------- | ------------------------------ |
| **Untracked** | File not yet tracked by Git    |
| **Tracked**   | File under Git version control |
| **Modified**  | File changed but not staged    |
| **Staged**    | File added to staging area     |
| **Committed** | Changes permanently saved      |

## 📘 GitHub Vocabulary (Remote Collaboration)
| Term                  | Meaning                                      |
| --------------------- | -------------------------------------------- |
| **GitHub**            | Online platform to host Git repositories     |
| **Remote Repository** | Repo stored on GitHub                        |
| **Origin**            | Default name of the remote repository        |
| **Push**              | Upload local commits to GitHub → send it to GitHub. |
| **Pull**              | Download changes from GitHub (Download latest updates before continuing work.) |
| **Pull Request (PR)** | Request to merge changes into another branch (Asking: “Please review and add my work”) |
| **Fork**              | Copy someone’s repo **Fork the repo** → Make changes in your copy → **Create PR** (suggest corrections)|
| **Clone**  git clone  | Download the entire project with history.    |
| **Issue**             | Task, bug, or feature request                |
| **Actions**           | CI/CD automation in GitHub                   |
| **Workflow**          | Steps defined for GitHub Actions             |
| **Release**           | Packaged version of the project              |
| **README.md**         | Project description and instructions         |
| **License**           | Rules for using the code                     |
| **Contributor**       | Person who contributes code                  |
| **Collaborator**      | User with repo write access                  |
| **Stars**             | Bookmark or appreciation                     |
| **Watch**             | Get notifications                            |
| **Organizations**     | Group accounts for teams                     |
