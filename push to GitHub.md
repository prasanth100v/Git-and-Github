## Steps to push a folder from your Linux EC2 instance to GitHub.
1️⃣ Go inside your project folder
```
cd ~/prasanth-poultry
```
2️⃣ Initialize Git (only once)
```
git init
```
3️⃣ Configure Git (first time only)
```
git config --global user.name "Prasanth v"
git config --global user.email "your-email@gmail.com"
```
4️⃣ Check files inside the folder & Check Git status:
```
ls -la
git status
```
5️⃣ Add files to Git
> Add everything
```
git add .
```
OR add specific folder/file
```
git add src package.json index.html
```
6️⃣ Commit the files
```
git commit -m "Initial commit"
```
7️⃣ Create a GitHub repository
```
Go to GitHub
Click New Repository
Give repo name (example: prasanth-poultry)
❌ Do NOT initialize with README
Click Create repository
```
8️⃣ Add GitHub remote
> HTTPS (easy)
```
git remote add origin https://github.com/prasanth100v/prasanth-poultry.git
```
Verify:
```
git remote -v
```
9️⃣ Push to GitHub
```
git branch -M main
git push -u origin main
```

## 🔐 When asked:
Username → GitHub username

Password → GitHub Personal Access Token (PAT)
> ❗ Not GitHub password

### 🔐 How to Create GitHub Token
```
GitHub → Settings → Developer settings
Personal access tokens → Tokens (classic)
Generate new token
✅ Copy token and use it as password
```
### ✅ Verify
Refresh GitHub → your files will appear 🎉

