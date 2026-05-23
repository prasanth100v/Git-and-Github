# Pull Request (PR)
 * `Pull Request reviews` mean other team members must `check` and `approve your code` before it is merged into the `main branch` or another branch.
 * PR ➡️ 📬 Request approval from manager : `“I finished my task, please review”`
 * **Real-world team workflow:**
```hcl
1. You push code
2. Create a Pull Request
3. Senior reviews your code
4. Approved → merged
```

🔄 Why Pull Requests are Used
```hcl
✅ Code review before merging
✅ Team discussion & comments
✅ Catch bugs early
✅ Maintain clean main/master branch
✅ Approval-based merging
```

# 🔒 Branch Protection Rules
* `Branch protection rules` are settings that prevent accidental or unauthorized changes to production code.
* 🧭 When to use Branch Protection
* Use it on critical branches like:
```hcl
main
production
release/*
```

## Core branch protection settings (`must-know`)
1️⃣ Require pull request before merging
```hcl
✔ Forces all changes to go through a PR
✔ Enables code review & discussion
👉 This alone blocks direct pushes
```

2️⃣ Require approvals
```hcl
 1–2 reviewers 👉 Prevents self-approval
```
* 📌 Interview tip : “We require at least `one reviewer` for production branches.”
* > “Approvals act as a human gate `before Argo CD syncs`.”

3️⃣ Restrict who can push to matching branches ✅

## 🏆 Production-Ready Rule (Recommended)
* For main / production branch:
```hcl
✅ Require PR
✅ Require 1–2 approvals
✅ Require CI checks
✅ Restrict who can push
❌ No force push
```

---

# 🔁 Pull Request Workflow (Step-by-Step)
1️⃣ Create a new branch
```hcl
git checkout -b feature-login
```
2️⃣ Make changes & commit
```hcl
git add .
git commit -m "Add login feature"
```
3️⃣ Push branch to GitHub
```hcl
git push origin feature-login
```
4️⃣ Create Pull Request on GitHub
```hcl
✅ Go to GitHub repo
✅ Click Compare & pull request
✅ Add title & description
✅ Click Create Pull Request
```
5️⃣ Review & Merge
```hcl
✅ Team reviews code
✅ Approve or request changes
✅ Click Merge pull request
```

---

## 🔀 Pull Request (PR) & Branch Protection — Rapid Fire Interview Q&A
| 🔢 Q#   | ❓ Question                                                                 | 💡 Answer                                                                                                          |
| ------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| 🔹 Q1   | What is a Pull Request (PR)?                                               | 👉 `A request to review and merge code into another branch.   `                                                      |
| 🔹 Q2   | Why are Pull Requests important?                                           | 👉 They enable `code review before merging`.                                                                         |
| 🔹 Q3   | Real-world meaning of PR?                                                  | 👉 `“I completed my task, please review my code.”  `                                                                 |
| 🔹 Q4   | Typical PR workflow?                                                       |  Push code <br> Create PR <br> Review <br> Approve <br> Merge                                                    |
| 🔹 Q5   | Main purpose of Pull Requests?                                             | 👉 `Collaboration and code quality control.  `                                                                       |
| 🔹 Q6   | Which platform commonly uses Pull Requests?                                | 👉 GitHub                                                                                                          |
| 🔹 Q7   | Alternative PR name in GitLab?                                             | 👉 `Merge Request (MR).   `                                                                                          |
| ✅ Q8    | Why use Pull Requests in teams?                                            |  ✅ Code review <br> ✅ Team discussion <br> ✅ Bug detection <br> ✅ Approval workflow <br> ✅ Cleaner main branch   |
| ✅ Q9    | How do PRs improve code quality?                                           | 👉 `Multiple developers review changes before merge.      `                                                          |
| ✅ Q10   | Why are PR comments useful?                                                | 👉 `Enable technical discussions and improvements.  `                                                                |
| ✅ Q11   | How do PRs help DevOps?                                                    | 👉 `Prevent unstable code from reaching production.   `                                                              |
| ✅ Q12   | What happens after PR approval?                                            | 👉 Code can be merged.                                                                                             |
| 🌿 Q13  | First step before PR creation?                                             | 👉 `Create a feature branch.  `                                                                                      |
| 🌿 Q14  | Command to create a new branch?                                            | 👉 `git checkout -b feature-login  `                                                                                 |
| 🌿 Q15  | Command to stage changes?                                                  | 👉 `git add . `                                                                                                      |
| 🌿 Q16  | Command to commit changes?                                                 | 👉 `git commit -m "Add login feature"  `                                                                             |
| 🌿 Q17  | Command to push branch to remote?                                          | 👉 `git push origin feature-login `                                                                                  |
| 🌿 Q18  | Where is PR created?                                                       | 👉 `On GitHub repository UI.`                                                                                        |
| 🌿 Q19  | GitHub button to start PR?                                                 | 👉 `Compare & pull request  `                                                                                        |
| 🌿 Q20  | Final step after review?                                                   | 👉 `Merge Pull Request.  `                                                                                           |
| 👥 Q21  | Who reviews Pull Requests?                                                 | 👉 `Senior developers/team members.   `                                                                          |
| 👥 Q23  | Can reviewer request changes?                                              | 👉 Yes.                                                                                                            |
| 👥 Q24  | What happens if PR is rejected?                                            | 👉 `Developer updates code and resubmits. `                                                                          |
| 👥 Q25  | What is approval-based merging?                                            | 👉 `Merge allowed only after reviewer approval.  `                                                                   |
| 👥 Q26  | Why avoid self-approval?                                                   | 👉 `Ensures independent code review.   `                                                                             |
| 🛡️ Q27 | What are branch protection rules?                                          | 👉` Rules preventing unsafe changes to critical branches.`                                                           |
| 🛡️ Q28 | Why use branch protection?                                                 | 👉 `Protect production/stable code. `                                                                                |
| 🛡️ Q29 | Common protected branches?                                                 | 👉 `main `<br> `production` <br> `release/*`                                                                        |
| 🛡️ Q30 | Most important protection rule?                                            | 👉 `Require Pull Request before merging.`                                                                            |
| 🛡️ Q31 | What does “Require PR before merging” do?                                  | 👉 `Blocks direct pushes.`                                                                                           |
| 🛡️ Q32 | Why block direct pushes?                                                   | 👉 `Prevent accidental production changes.  `                                                                        |
| 🛡️ Q34 | Recommended approval count?                                                | 👉 1–2 reviewers.                                                                                                  |
| 🛡️ Q35 | What is “Restrict who can push”?                                           | 👉 `Only authorized users can push.    `                                                                             |
| 🛡️ Q36 | Why disable force push?                                                    | 👉 `Prevent history rewriting. `                                                                                     |
| 🛡️ Q37 | What are CI checks in branch protection?                                   | 👉 Automated tests that must pass before merge.                                                                    |
| 🛡️ Q38 | Why require CI checks?                                                     | 👉 `Prevent broken code deployment.  `                                                                               |
| 🚀 Q39  | Recommended protection for production branches?                            | ✅ Require PR <br> ✅ Require approvals <br> ✅ Require CI checks <br> ✅ Restrict push access <br> ❌ No force push |
| 🚀 Q40  | Why protect main branch?                                                   | 👉 It usually contains `production-ready code. `                                                                     |
| 🚀 Q41  | Why are approvals important before Argo CD sync?                           | 👉 `Human validation before deployment.   `                                                                          |
| 🚀 Q42  | Interview line for approvals?                                              | 👉 “Approvals act as a human gate before deployment.”                                                              |
| 🔀 Q43  | What is merge commit?                                                      | 👉 `Commit created when PR is merged. `                                                                              |
| 🔀 Q44  | What is squash merge?                                                      | 👉 `Combines multiple commits into one.   `                                                                          |
| 🔀 Q45  | Why use squash merge?                                                      | 👉 `Cleaner Git history. `                                                                                           |
| 🔀 Q46  | What is rebase merge?                                                      | 👉 Reapplies commits on top of target branch.                                                                      |
| 🔀 Q48  | When do merge conflicts occur?                                             | 👉 `Same lines/files modified by multiple developers.   `                                                            |
| 🔀 Q49  | How are merge conflicts resolved?                                          | 👉` Manual editing and recommit. `                                                                                   |
| ☸️ Q50  | Why are PRs important in CI/CD?                                            | 👉 `CI pipelines validate code before deployment. `                                                                  |
| ☸️ Q51  | What usually runs automatically on PR?                                     | 👉 Tests <br> Linting <br> Security scans <br> Build validation                                                    |
| ☸️ Q52  | Why integrate PRs with CI pipelines?                                       | 👉 `Detect issues early. `                                                                                           |
| ☸️ Q53  | What happens if CI fails?                                                  | 👉 `Merge is blocked.`                                                                                               |
| ☸️ Q54  | Why are PR reviews critical in production?                                 | 👉 Reduce deployment risks.                                                                                        |
| 🎯 Q55  | A developer directly pushes broken code to main. What could prevent this?  | 👉` Branch protection rules.`                                                                                        |
| 🎯 Q56  | A PR cannot merge because checks failed. Why?                              | 👉 `Required CI checks failed.   `                                                                                   |
| 🎯 Q57  | A developer force-pushed production history accidentally. Best prevention? | 👉 `Disable force push.  `                                                                                           |
| 🎯 Q58  | Why should developers work in feature branches?                            | 👉 `Isolate changes safely.  `                                                                                       |
| 🧠 Q59  | One-line definition of Pull Request?                                       | 👉 A Pull Request is a code review request before merging changes.                                                 |
| 🧠 Q60  | One-line definition of branch protection?                                  | 👉 Branch protection prevents unsafe modifications to critical branches.                                           |
