## Steps to push a folder from your Linux EC2 instance to GitHub.
1️⃣ Go inside your project folder
```hcl
cd ~/prasanth-poultry
```
2️⃣ Initialize Git (only once)
```hcl
git init
```
3️⃣ Configure Git (first time only)
```hcl
git config --global user.name "Prasanth v"
git config --global user.email "your-email@gmail.com"
```
4️⃣ Check files inside the folder & Check Git status:
```hcl
ls -la
git status
```
5️⃣ Add files to Git
> Add everything
```hcl
git add .
```
`OR` add specific folder/file
```hcl
git add src package.json index.html
```
6️⃣ Commit the files
```hcl
git commit -m "Initial commit"
```
7️⃣ Create a GitHub repository
```hcl
1. Go to GitHub
2. Click New Repository
3. Give repo name (example: prasanth-poultry)
4. ❌ Do NOT initialize with README
5. Click Create repository
```
8️⃣ Add GitHub remote
> HTTPS (easy)
```hcl
git remote add origin https://github.com/prasanth100v/prasanth-poultry.git
```
Verify:
```hcl
git remote -v
```
9️⃣ Push to GitHub
```hcl
git branch -M main
git push -u origin main
```

## 🔐 When asked:
 * Username → `GitHub username`
 * Password → GitHub Personal Access Token (`PAT`)
 * > ❗ Not GitHub password

### 🔐 How to Create GitHub Token
```hcl
1. GitHub → Settings → Developer settings
2. Personal access tokens → Tokens (classic)
3. Generate new token
4. ✅ Copy token and use it as password
```
### ✅ Verify
 * Refresh GitHub → your files will appear 🎉

