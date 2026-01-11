# Pull Request (PR)
Pull Request reviews mean other team members must check and approve your code before it is merged into the main branch or another branch.
### PR ➡️ 📬 Request approval from manager : “I finished my task, please review”

**Real-world team workflow:**
```
You push code
Create a Pull Request
Senior reviews your code
Approved → merged
```
🔄 Why Pull Requests are Used
```
✅ Code review before merging
✅ Team discussion & comments
✅ Catch bugs early
✅ Maintain clean main/master branch
✅ Approval-based merging
```
# 🔒 Branch Protection Rules
“Branch protection rules are settings that prevent accidental or unauthorized changes to production code.”
#### 🧭 When to use Branch Protection
Use it on critical branches like:
```
main
production
release/*
```

## Core branch protection settings (must-know)
1️⃣ Require pull request before merging
```
✔ Forces all changes to go through a PR
✔ Enables code review & discussion
👉 This alone blocks direct pushes
```
2️⃣ Require approvals
```
 1–2 reviewers 👉 Prevents self-approval
```
📌 Interview tip: “We require at least one reviewer for production branches.”
> “Approvals act as a human gate before Argo CD syncs.”

3️⃣Restrict who can push to matching branches ✅

## 🏆 Production-Ready Rule (Recommended)
For main / production branch:
```
✅ Require PR
✅ Require 1–2 approvals
✅ Require CI checks
✅ Restrict who can push
❌ No force push
```

# 🔁 Pull Request Workflow (Step-by-Step)
1️⃣ Create a new branch
```
git checkout -b feature-login
```
2️⃣ Make changes & commit
```
git add .
git commit -m "Add login feature"
```
3️⃣ Push branch to GitHub
```
git push origin feature-login
```
4️⃣ Create Pull Request on GitHub
```
✅ Go to GitHub repo
✅ Click Compare & pull request
✅ Add title & description
✅ Click Create Pull Request
```
5️⃣ Review & Merge
```
✅ Team reviews code
✅ Approve or request changes
✅ Click Merge pull request
```
