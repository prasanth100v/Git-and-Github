## 🔁 Real Company Workflow (End-to-End)
```
1️⃣ Clone repo
2️⃣ Create feature branch
3️⃣ Write code
4️⃣ git add + commit
5️⃣ git push
6️⃣ Create PR
7️⃣ Review + merge
8️⃣ GitHub Actions deploys
```

## 🔄 End-to-End Workflow :
> “In my daily workflow, I create a feature branch, commit small logical changes, push to GitHub,
> raise a pull request, address reviews, and merge to main. CI/CD then runs automatically using GitHub Actions.”


# 🔐 Connect a Private Repository to Git on Linux
“To connect a private GitHub repository on Linux, I configure SSH authentication using key pairs, add the public key to GitHub, and clone the repo via SSH. This provides secure, passwordless access and is the recommended approach in DevOps environments.”
> Why SSH is preferred : No password every time and Secure & stable

## 🔐 How to Generate an SSH Key (Linux – Real Company Way)
#### 1️⃣ Check if SSH already exists (optional but smart)
```
ls ~/.ssh
```
> If you see id_ed25519 or id_rsa, you may already have a key.

#### 2️⃣ Generate a New SSH Key (Recommended Command)
✅ Modern & recommended (ED25519)
```
ssh-keygen -t ed25519 -C "your_email@company.com"
```
If ED25519 is not supported (older systems)
```
ssh-keygen -t rsa -b 4096 -C "your_email@company.com"
```

This creates: (/home/user/.ssh/id_ed25519)
```
🔐 Private key: ~/.ssh/id_ed25519
🔓 Public key: ~/.ssh/id_ed25519.pub
```

3️⃣ Copy Public Key (This Is What You Share)
```
cat ~/.ssh/id_ed25519.pub
```
Example output:
```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... your_email@company.com
```
> 📌 Only the .pub key is shared
> ❌ Never share the private key (id_ed25519)

4️⃣ Add SSH Key to GitHub
```
GitHub → Settings
SSH and GPG keys
New SSH key
Paste the public key
Save
```

5️⃣ Test SSH Connection (Very Important)
```
ssh -T git@github.com
```
✅ Expected output:
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```
**🎉 SSH setup complete.**
