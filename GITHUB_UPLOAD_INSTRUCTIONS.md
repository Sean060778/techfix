# GitHub Upload - Step by Step

## ✅ Correct Way: Upload CONTENTS of frontend folder

### What You Need to Upload:

Upload the **FILES and FOLDERS INSIDE** the `frontend` folder:

```
✅ Upload these (contents INSIDE frontend/):
   ├── index.html
   ├── login.html
   ├── register.html
   ├── js/ (folder)
   ├── css/ (folder)
   ├── images/ (folder)
   ├── admin/ (folder)
   ├── staff/ (folder)
   └── all other .html files

❌ DO NOT upload:
   └── frontend/ (the folder itself)
```

---

## Step-by-Step Instructions

### Method 1: Using GitHub Web Interface (Easiest)

1. **Open your `frontend` folder** in Windows File Explorer
   - Navigate to: `C:\Users\seanp\Downloads\ITEL4Final\frontend`
   - You should see: `index.html`, `login.html`, `js/`, `css/`, etc.

2. **Go to your GitHub repository** on GitHub.com
   - If you haven't created it yet, create a new repository first
   - Make sure it's **Public** (required for free GitHub Pages)

3. **Click "uploading an existing file"** or drag and drop area

4. **Select ALL files and folders INSIDE the frontend folder:**
   - Select `index.html`
   - Select `login.html`
   - Select `register.html`
   - Select `js/` folder
   - Select `css/` folder
   - Select `images/` folder
   - Select `admin/` folder
   - Select `staff/` folder
   - Select all other `.html` files
   - **DO NOT select the `frontend` folder itself**

5. **Drag all selected items** into GitHub upload area
   - OR use "choose your files" button

6. **Scroll down** and click **"Commit changes"**

7. **Wait for upload** to complete

---

### Method 2: Using Git Commands

1. **Open Command Prompt** or Terminal

2. **Navigate to the frontend folder:**
   ```bash
   cd "C:\Users\seanp\Downloads\ITEL4Final\frontend"
   ```

3. **Verify you're in the right place:**
   ```bash
   dir
   ```
   You should see: `index.html`, `login.html`, `js/`, `css/`, etc.

4. **Initialize Git:**
   ```bash
   git init
   ```

5. **Add all files:**
   ```bash
   git add .
   ```

6. **Commit:**
   ```bash
   git commit -m "Initial commit - TechFix Frontend"
   ```

7. **Connect to GitHub (replace YOUR_USERNAME):**
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
   ```

8. **Push to GitHub:**
   ```bash
   git branch -M main
   git push -u origin main
   ```

---

## Verify Correct Structure

After uploading, your GitHub repository should look like this:

```
Your Repository (root level):
   ├── index.html          ← Should be at root, NOT in frontend/
   ├── login.html          ← Should be at root, NOT in frontend/
   ├── register.html       ← Should be at root, NOT in frontend/
   ├── js/                 ← Folder at root
   │   ├── config.js
   │   ├── auth.js
   │   └── ...
   ├── css/                ← Folder at root
   ├── images/             ← Folder at root
   ├── admin/              ← Folder at root
   └── staff/              ← Folder at root
```

**NOT like this:**
```
Your Repository:
   └── frontend/           ← ❌ WRONG - Don't upload the folder
       ├── index.html
       ├── login.html
       └── ...
```

---

## Enable GitHub Pages

1. **Go to your repository** on GitHub.com
2. **Click "Settings"** (top menu)
3. **Click "Pages"** (left sidebar)
4. **Under "Source":**
   - Select: **"Deploy from a branch"**
   - Branch: **"main"** (or "master")
   - Folder: **"/ (root)"** ← This is why files must be at root!
5. **Click "Save"**

---

## Your Site URL

After enabling GitHub Pages, your site will be at:
- `https://YOUR_USERNAME.github.io/REPO_NAME/`

For example:
- If your username is `sean060778` and repo is `techfix-frontend`
- Your site: `https://sean060778.github.io/techfix-frontend/`

---

## Quick Checklist

- [ ] Opened the `frontend` folder in File Explorer
- [ ] Selected files INSIDE the folder (not the folder itself)
- [ ] Uploaded: `index.html`, `login.html`, `js/`, `css/`, `images/`, `admin/`, `staff/`
- [ ] Files appear at ROOT level in GitHub (not in a `frontend/` subfolder)
- [ ] Enabled GitHub Pages in Settings
- [ ] Set Pages source to `/ (root)` folder

---

## Need Help?

If you're not sure:
1. After uploading, check your GitHub repository
2. Look at the file structure
3. Make sure `index.html` is at the root level (not inside any folder)
4. If `index.html` is inside a `frontend/` folder, you uploaded the wrong thing!

