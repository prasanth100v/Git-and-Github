## 🔁 Real Company Workflow (End-to-End)
  * 📂 In my company workflow, a DevOps Engineer `clones the repository`, creates a feature branch, writes code, commits and pushes changes, opens a `Pull Request` for `review`, and after approval the `code is merged`.
  * 🚀 After merging, the CI/CD pipeline such as GitHub Actions and Argo CD automatically builds, tests, and deploys the application.
  * 🎉 Key Points
       * 🌿 Every new feature is developed in its own branch.
       * 🔍 `Pull Requests` ensure code quality through peer review (`experts in the same field evaluate the work`).
       * ✅ Only approved code is merged into the main branch.

| 🔢 **Step** | 📖 **Action**                         | 💻 **Git Command**                        | 🧠 **What Happens**                                    | 💡 **Purpose**                             |
| ----------- | ------------------------------------- | ----------------------------------------- | --------------------------------------------------------- | ------------------------------------------ |
| 1️⃣         | 📥 **Clone Repository**               | `git clone <repo-url>`                    | Download the project from GitHub to your local machine    | Start working on the project               |
| 2️⃣         | 🌿 **Create Feature Branch**          | `git checkout -b feature/login`           | Create a separate branch from `main` or `develop`         | Isolate your changes                       |
| 3️⃣         | 💻 **Write Code**                     | *(Edit files)*                            | Implement the feature or fix the bug                      | Develop without affecting others           |
| 4️⃣         | 🔍 **Check Changes**                  | `git status`                              | View modified, staged, and untracked files                | Verify your changes                        |
| 5️⃣         | ➕ **Stage Changes**                   | `git add .`                               | Add changes to the staging area                          | Prepare files for commit                   |
| 6️⃣         | 💾 **Commit Changes**                 | `git commit -m "Add login feature"`       | Save changes in the local repository                      | Create a meaningful checkpoint             |
| 7️⃣         | ⬆️ **Push Branch**                    | `git push origin feature/login`           | Push your branch to GitHub                                | Share your changes with the team           |
| 8️⃣         | 🔀 **Create Pull Request (PR)**       | *(GitHub UI)*                             | Request to merge your branch                              | Start the code review process              |
| 9️⃣         | 🔄 **Sync Latest Changes (Optional)** | `git pull origin main`                    | `Fetch` and `merge` the latest changes from `main`        | Keep your branch up to date before merging |
| 🔟         | 👨‍💻 **Code Review + Merge**            | *(GitHub UI or `git merge main` locally)* | Team reviews, approves, and merges the PR                 | Maintain code quality                      |
| 1️⃣1️⃣      | 🚀 **GitHub Actions Deploys**          | *(Triggered automatically)*               | CI/CD pipeline `builds`, `tests`, and `deploys` the application | Automate delivery to environments    |

---

## 🔐 Connect a Private GitHub Repository on Linux (Real Company Workflow)
 * 🚀 To connect a private GitHub repository on Linux, I configure `SSH authentication using key pairs`, add the public key to GitHub, verify the connection using `ssh -T git@github.com`, and clone the repository using the `SSH URL`.
 * 🔑 This provides secure, `passwordless access` authentication and is the recommended approach in DevOps environments.
 * 🔐 Why SSH is preferred : `No password every time` and `Secure & stable`

| 🔢 **Step** | 📖 **Action**                | 💻 **Command / Action**                                      | 💡 **Purpose**                                  |
| ----------- | ---------------------------- | ------------------------------------------------------------ | ----------------------------------------------- |
| 1️⃣         | 📂 Check existing SSH keys   | `ls ~/.ssh`                                                  | Verify whether an SSH key already exists        |
| 2️⃣         | 🔑 Generate SSH key          | `ssh-keygen -t ed25519 -C "your_email@example.com"`          | Create a secure SSH key pair                    |
| 3️⃣         | 🚀 Start SSH Agent           | `eval "$(ssh-agent -s)"`                                     | Start the SSH agent to manage keys              |
| 4️⃣         | ➕ Add private key            | `ssh-add ~/.ssh/id_ed25519`                                  | Load the private key into the SSH agent         |
| 5️⃣         | ✅ Verify loaded key          | `ssh-add -l`                                                 | Confirm the SSH key is loaded                   |
| 6️⃣         | 📋 Copy public key           | `cat ~/.ssh/id_ed25519.pub`                                  | Copy the public key to add to GitHub            |
| 7️⃣         | 🌐 Add key to GitHub         | **GitHub → Settings → SSH and GPG keys → New SSH key**       | Register your public key with GitHub            |
| 8️⃣         | 🔍 Test SSH connection       | `ssh -T git@github.com`                                      | Verify SSH authentication with GitHub           |
| 9️⃣         | 📥 Clone repository          | `git clone git@github.com:<user>/<repo>.git`                 | Clone the private repository using SSH          |
| 🔟          | 📍 Navigate to repository    | `cd <repo-name>`                                             | Enter the cloned repository                     |
| 1️⃣1️⃣      | 🔗 Verify remote URL         | `git remote -v`                                              | Confirm the repository uses the SSH URL         |
| 1️⃣2️⃣      | 🔄 Update remote (if needed) | `git remote set-url origin git@github.com:<user>/<repo>.git` | Switch an existing repository from HTTPS to SSH |

---

# Step by Step Explain :
## 🔐 How to Generate an SSH Key (Linux – Real Company Way)
#### 1️⃣ Check if SSH already exists (optional but smart)
```hcl
ls ~/.ssh
```
> If you see id_ed25519 or id_rsa, you may already have a key.

#### 2️⃣ Generate a New SSH Key (Recommended Command)
✅ Modern & recommended (ED25519)
```hcl
ssh-keygen -t ed25519 -C "prasanthema100.com"
```
If ED25519 is not supported (older systems)
```hcl
ssh-keygen -t rsa -b 4096 -C "prasanthema100.com"
```
Press:
```hcl
Enter → accept default location (~/.ssh/id_ed25519)
Enter passphrase (optional but recommended)
```
This creates: (/home/user/.ssh/id_ed25519)
```hcl
🔐 Private key: ~/.ssh/id_ed25519
🔓 Public key: ~/.ssh/id_ed25519.pub
```
3️⃣ Start the SSH Agent
```hcl
eval "$(ssh-agent -s)"
```
What you should see
```hcl
Agent pid 12345       👉 This means SSH Agent is now running ✅
```
### Add your SSH key to the agent
```hcl
ssh-add ~/.ssh/id_ed25519
```
What you should see
```hcl
Identity added: /home/user/.ssh/id_ed25519   👉 Now the agent holds your key 🔐
```
### Verify (very useful)
```hcl
ssh-add -l
```
Output example :
```hcl
256 SHA256:abcd1234... id_ed25519 (ED25519)   ✔ This confirms the key is loaded correctly
```

4️⃣ Copy Public Key (This Is What You Share)
```hcl
cat ~/.ssh/id_ed25519.pub
```
Example output:
```hcl
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... your_email@company.com
```
> 📌 Only the .pub key is shared
> ❌ Never share the private key (id_ed25519)

### Add SSH Key to GitHub
```hcl
1. GitHub → Settings
2. SSH and GPG keys
3. Click New SSH key
4. Paste the key
5. Type: Authentication Key
6. Save
```

5️⃣ Test SSH Connection (Very Important)
```hcl
ssh -T git@github.com
```
✅ Expected output:
```hcl
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```
**🎉 SSH setup complete.**

## Clone private repo using SSH (repo uses SSH (not HTTPS)
```hcl
git clone git@github.com:prasanth100v/private.git
```
### Make sure you are inside the repo folder
```hcl
cd private
git status
```
2️⃣ Set this SSH URL as origin (safe even if already set)
```hcl
git remote set-url origin git@github.com:prasanth100v/private.git
git remote -v
```
Expected:
```hcl
origin  git@github.com:prasanth100v/private.git (fetch)
origin  git@github.com:prasanth100v/private.git (push)
```

---

## 🔐 GitHub SSH & Real Company Git Workflow — Rapid Fire Interview Q&A
| 🔢 Q#   | ❓ Question                                          | 💡 Answer                                                                                                                                        |
| ------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| 🏢 Q1   | Typical Git workflow in companies?                  |  Clone repo <br> Create branch <br> Write code <br> Commit <br> Push <br> Create PR <br> Review <br> Merge <br> Deploy                         |
| 🏢 Q2   | What happens after PR merge in modern DevOps?       | 👉 `CI/CD pipeline deploys automatically. `                                                                                                        |
| 🏢 Q5   | Real interview workflow statement?                  | 👉 “I create feature branches, commit logical changes, raise PRs, address reviews, and merge to main. CI/CD then deploys automatically.”         |
| 🔐 Q6   | Best way to connect private GitHub repo in Linux?   | 👉 `SSH authentication.`                                                                                                                           |
| 🔐 Q7   | Why is SSH preferred over HTTPS?                    |  ✅ Passwordless access <br> ✅ More secure <br> ✅ Stable authentication                                                                         |
| 🔐 Q8   | What authentication method does SSH use?            | 👉 `Public/private key pair.  `                                                                                                                    |
| 🔐 Q9   | Which key is shared with GitHub?                    | 👉 `Public key (.pub).    `                                                                                                                        |
| 🔐 Q10  | Which key must NEVER be shared?                     | 👉 `Private key.  `                                                                                                                                |
| 🔑 Q11  | Command to check existing SSH keys?                 | 👉 `ls ~/.ssh `                                                                                                                                    |
| 🔑 Q12  | Recommended modern SSH algorithm?                   | 👉 `ED25519 `                                                                                                                                      |
| 🔑 Q13  | Command to generate ED25519 SSH key?                | 👉 `ssh-keygen -t ed25519 -C "[email@example.com](mailto:email@example.com)"   `                                                                   |
| 🔑 Q14  | Alternative SSH algorithm for older systems?        | 👉 `RSA. `                                                                                                                                         |
| 🔑 Q15  | Command to generate RSA key?                        | 👉 `ssh-keygen -t rsa -b 4096 -C "[email@example.com](mailto:email@example.com)" `                                                                 |
| 🔑 Q16  | What does -b 4096 mean?                             | 👉 `4096-bit RSA key strength.  `                                                                                                                  |
| 🔑 Q17  | Default location of ED25519 private key?            | 👉` ~/.ssh/id_ed25519 `                                                                                                                            |
| 🔑 Q18  | Default location of public key?                     | 👉` ~/.ssh/id_ed25519.pub `                                                                                                                        |
| 🔑 Q19  | Which file is private key?                          | 👉 `id_ed25519 `                                                                                                                                   |
| 🔑 Q20  | Which file is public key?                           | 👉 `id_ed25519.pub   `                                                                                                                             |
| 🧠 Q21  | What is SSH Agent?                                  | 👉 Background service that `stores SSH keys securely`.                                                                                             |
| 🧠 Q22  | Command to start SSH Agent?                         | 👉 eval "$(ssh-agent -s)"                                                                                                                        |
| 🧠 Q23  | Expected SSH Agent output?                          | 👉 `Agent pid 12345   `                                                                                                                            |
| 🧠 Q24  | Command to add SSH key to agent?                    | 👉 `ssh-add ~/.ssh/id_ed25519 `                                                                                                                    |
| 🧠 Q25  | Command to verify loaded SSH keys?                  | 👉 `ssh-add -l`                                                                                                                                    |
| 🧠 Q26  | What does ssh-add -l show?                          | 👉 `Loaded SSH identities.`                                                                                                                        |
| ☁️ Q27  | Command to display public key?                      | 👉 `cat ~/.ssh/id_ed25519.pub  `                                                                                                                   |
| ☁️ Q28  | Where do you add SSH key in GitHub?                 | 👉 `Settings → SSH and GPG Keys.     `                                                                                                             |
| ☁️ Q29  | Which key type is selected in GitHub?               | 👉 `Authentication Key`                                                                                                                            |
| ☁️ Q30  | Command to test GitHub SSH connection?              | 👉 `ssh -T [git@github.com](mailto:git@github.com)    `                                                                                            |
| ☁️ Q31  | Successful GitHub SSH test message?                 | 👉 Hi username! You've successfully authenticated...                                                                                             |
| ☁️ Q32  | Does GitHub provide shell access over SSH?          | 👉 No.                                                                                                                                           |
| 🌿 Q33  | SSH clone URL format?                               | 👉 `[git@github.com](mailto:git@github.com):user/repo.git `                                                                                        |
| 🌿 Q34  | Command to clone private repo via SSH?              | 👉 `git clone [git@github.com](mailto:git@github.com):user/private.git    `                                                                        |
| 🌿 Q35  | Command to enter cloned repository?                 | 👉 cd private                                                                                                                                    |
| 🌿 Q36  | Command to verify repo status?                      | 👉 git status                                                                                                                                    |
| 🌿 Q37  | Command to change remote URL to SSH?                | 👉 `git remote set-url origin [git@github.com](mailto:git@github.com):user/repo.git  `                                                             |
| 🌿 Q38  | Command to verify remote URLs?                      | 👉` git remote -v  `                                                                                                                               |
| 🛡️ Q39 | Recommended permission for private key?             | 👉 `chmod 600 ~/.ssh/id_ed25519 `                                                                                                                  |
| 🚀 Q40  | What is GitOps?                                     | 👉 Git as source of truth for `infrastructure/deployments`.                                                                                        |
| 🛠️ Q41 | SSH authentication fails. First thing to check?     | 👉 ssh -T [git@github.com](mailto:git@github.com)                                                                                                |
| 🛠️ Q42 | SSH key not working. What may be missing?           | 👉 Key not added to SSH agent or GitHub.                                                                                                         |
| 🛠️ Q43 | Command to confirm SSH agent has key?               | 👉` ssh-add -l   `                                                                                                                                 |
| 🛠️ Q44 | Git asks for password despite SSH setup. Why?       | 👉 Remote URL still uses `HTTPS`.                                                                                                                  |
| 🛠️ Q45 | How to fix Git asking for password?                 | 👉 Change `remote URL to SSH`.                                                                                                                     |

