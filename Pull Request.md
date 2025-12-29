# Pull Request (PR)
Pull Request reviews mean other team members must check and approve your code before it is merged into the main branch.
### PR ➡️ 📬 Request approval from manager : “I finished my task, please review”

**Real-world team workflow:**
```
You push code
Create a Pull Request
Senior reviews your code
Approved → merged
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
