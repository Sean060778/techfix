# Step-by-Step: Deploy Frontend to GitHub Pages

## 🎯 Two Methods: Choose What's Easier For You!

### Method 1: Upload Files Directly (EASIEST!) ⭐
**No Git commands needed - just drag and drop!**

### Method 2: Use Git Commands
**For advanced users or if you want to update via commands**

---

## Method 1: Upload Files Directly (Recommended for Beginners)

### Step 1: Create GitHub Repository

1. **Go to GitHub.com** and sign in
2. **Click the "+" icon** (top right) → **"New repository"**
3. **Repository settings:**
   - **Repository name**: `techfix-frontend` (or any name you like)
   - **Description**: "TechFix Repairs - Frontend"
   - **Visibility**: Public (required for free GitHub Pages)
   - **DO NOT** check "Initialize with README" (we already have files)
4. **Click "Create repository"**

### Step 2: Upload Files

After creating the repository, you'll see a page with "Quick setup" options.

1. **Click "uploading an existing file"** link (or scroll down)
2. **Drag and drop your entire `frontend` folder** OR click "choose your files"
3. **Select all files** from your frontend folder:
   - All `.html` files
   - `js/` folder (with all `.js` files)
   - `css/` folder
   - `images/` folder
   - `admin/` folder
   - `staff/` folder
   - Any other files/folders

4. **Scroll down** and click **"Commit changes"**
5. **Wait for upload** (may take a few minutes if many files)

### Step 3: Enable GitHub Pages

1. **Go to your repository** (refresh the page)
2. **Click "Settings"** (top menu)
3. **Scroll down to "Pages"** (left sidebar)
4. **Under "Source":**
   - Select: **"Deploy from a branch"**
   - Branch: **"main"**
   - Folder: **"/ (root)"**
5. **Click "Save"**

### Step 4: Wait for Deployment

- Wait 1-2 minutes
- Your site will be live at: `https://YOUR_USERNAME.github.io/techfix-frontend/`

### Step 5: Update API URL

1. **Go to your repository on GitHub**
2. **Click on `js/config.js`**
3. **Click the pencil icon** (Edit file)
4. **Change line 13:**
   ```javascript
   production: 'https://yourdomain.com/api'
   ```
   Replace `yourdomain.com` with your Hostinger domain
5. **Scroll down → "Commit changes"**
6. **Click "Commit changes"**

**Done!** ✅ Your site is live!

---

## Method 2: Use Git Commands (Advanced)

### Step 1: Create GitHub Repository

1. **Go to GitHub.com** and sign in
2. **Click the "+" icon** (top right) → **"New repository"**
3. **Repository settings:**
   - **Repository name**: `techfix-frontend` (or any name you like)
   - **Description**: "TechFix Repairs - Frontend"
   - **Visibility**: Public (required for free GitHub Pages)
   - **DO NOT** check "Initialize with README" (we already have files)
4. **Click "Create repository"**

### Step 2: Open Terminal/Command Prompt

### Windows:
- Press `Win + R`
- Type `cmd` and press Enter
- Or search "Command Prompt" in Start menu

### Mac/Linux:
- Press `Cmd + Space` (Mac) or `Ctrl + Alt + T` (Linux)
- Type "Terminal" and press Enter

### Step 3: Navigate to Your Frontend Folder

In the terminal, type:

```bash
cd "C:\Users\seanp\Downloads\wetransfer_itel4final-zip_2025-12-02_1215\ITEL4FINAL\ITEL4FINAL\frontend"
```

**Or if you're already in the project folder:**
```bash
cd frontend
```

**Verify you're in the right place:**
```bash
dir
```
(Windows) or
```bash
ls
```
(Mac/Linux)

You should see files like `index.html`, `login.html`, `js/`, `css/`, etc.

### Step 4: Initialize Git Repository

```bash
git init
```

This creates a new Git repository in your folder.

### Step 5: Add All Files

```bash
git add .
```

This adds all files to Git's staging area.

### Step 6: Create First Commit

```bash
git commit -m "Initial commit - TechFix Frontend"
```

This saves all your files as the first version.

### Step 7: Connect to GitHub Repository

**Replace `YOUR_USERNAME` with your actual GitHub username:**

```bash
git remote add origin https://github.com/YOUR_USERNAME/techfix-frontend.git
```

**Example:**
If your username is `johnsmith`, it would be:
```bash
git remote add origin https://github.com/johnsmith/techfix-frontend.git
```

### Step 8: Push to GitHub

```bash
git branch -M main
git push -u origin main
```

**If prompted for credentials:**
- **Username**: Your GitHub username
- **Password**: Use a **Personal Access Token** (not your GitHub password)
  - Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
  - Generate new token → Select "repo" scope → Copy token
  - Use this token as your password

### Step 9: Enable GitHub Pages

1. **Go to your repository on GitHub.com**
2. **Click "Settings"** (top menu)
3. **Scroll down to "Pages"** (left sidebar)
4. **Under "Source":**
   - Select: **"Deploy from a branch"**
   - Branch: **"main"**
   - Folder: **"/ (root)"**
5. **Click "Save"**

---

## Step 10: Wait for Deployment

- GitHub will show: "Your site is ready to be published at..."
- Wait 1-2 minutes for deployment
- Your site will be live at: `https://YOUR_USERNAME.github.io/techfix-frontend/`

---

## Step 11: Update API URL

1. **Go to your repository on GitHub**
2. **Click on `js/config.js`**
3. **Click the pencil icon** (Edit file)
4. **Change line 13:**
   ```javascript
   production: 'https://yourdomain.com/api'
   ```
   Replace `yourdomain.com` with your Hostinger domain
5. **Scroll down → "Commit changes"**
6. **Click "Commit changes"**

---

## ✅ Verify It Works

1. **Visit your GitHub Pages URL:**
   `https://YOUR_USERNAME.github.io/techfix-frontend/`

2. **Open browser console** (F12)
3. **Check the log** - should show:
   ```
   🚀 Production Mode - API URL: https://yourdomain.com/api
   ```

---

## 🔄 Making Updates

When you make changes to your files:

```bash
git add .
git commit -m "Description of changes"
git push
```

GitHub Pages will automatically update in 1-2 minutes!

---

## 🐛 Troubleshooting

### "git is not recognized"
- Install Git: https://git-scm.com/downloads
- Restart terminal after installation

### "Permission denied"
- Check your GitHub username and token
- Make sure repository name matches

### "Site not loading"
- Wait 2-3 minutes after enabling Pages
- Check repository Settings → Pages for errors
- Make sure `index.html` is in the root folder

### "API not working"
- Check browser console for errors
- Verify `config.js` has correct Hostinger domain
- Make sure CORS is configured on Hostinger backend

---

## 📝 Quick Reference

```bash
# Navigate to frontend folder
cd path/to/frontend

# Initialize Git
git init

# Add files
git add .

# Commit
git commit -m "Initial commit"

# Connect to GitHub (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/techfix-frontend.git

# Push to GitHub
git branch -M main
git push -u origin main
```

---

## 🎉 Done!

Your frontend is now live on GitHub Pages! 

Next steps:
1. Update `config.js` with your Hostinger domain
2. Test the site
3. Set up Cordova (see `CORDOVA_SETUP.md`)

