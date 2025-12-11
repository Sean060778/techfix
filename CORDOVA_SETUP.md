# Cordova Setup Guide

## Two Options for Cordova

### Option 1: Load from GitHub Pages (Recommended) ⭐

**Best for:** Easy updates, no rebuilds needed

1. **Deploy frontend to GitHub Pages first**
   - Push `frontend/` folder to GitHub
   - Enable GitHub Pages
   - Your site: `https://yourusername.github.io/techfix-frontend/`

2. **Create Cordova app that loads GitHub Pages**
   ```bash
   cordova create techfix-app com.techfix.app TechFix
   cd techfix-app
   ```

3. **Edit `config.xml`**
   ```xml
   <content src="https://yourusername.github.io/techfix-frontend/index.html" />
   ```

4. **Add platforms and build**
   ```bash
   cordova platform add android
   cordova platform add ios
   cordova build android
   ```

**Pros:**
- ✅ Updates automatically when you push to GitHub
- ✅ No need to rebuild app for frontend changes
- ✅ Smaller app size
- ✅ Same codebase for web and mobile

**Cons:**
- ❌ Requires internet connection
- ❌ Slightly slower initial load

---

### Option 2: Bundle Files Locally

**Best for:** Offline support, faster loading

1. **Create Cordova app**
   ```bash
   cordova create techfix-app com.techfix.app TechFix
   cd techfix-app
   ```

2. **Copy frontend files**
   ```bash
   # Copy all frontend files to www folder
   cp -r ../frontend/* www/
   ```

3. **Update API URL in `www/js/config.js`**
   - Change production URL to your Hostinger domain

4. **Add platforms and build**
   ```bash
   cordova platform add android
   cordova platform add ios
   cordova build android
   ```

**Pros:**
- ✅ Works offline (after initial load)
- ✅ Faster loading
- ✅ No external dependencies

**Cons:**
- ❌ Need to rebuild app for every frontend update
- ❌ Larger app size
- ❌ Separate codebase to maintain

---

## API Configuration

### For Both Options:

1. **Update `js/config.js`** (or `www/js/config.js` if bundling)
   ```javascript
   production: 'https://yourdomain.com/api'
   ```
   Replace `yourdomain.com` with your Hostinger domain

2. **Cordova automatically uses production API**
   - The `config.js` detects Cordova and uses production URL
   - No need to change anything else!

---

## What is 127.0.0.1:8000?

- **127.0.0.1:8000** = Local development server
- This is what runs when you do: `php artisan serve`
- Only used when testing on your computer
- **NOT used in production** (GitHub Pages or Cordova)

### Flow:
- **Development**: Frontend → `127.0.0.1:8000/api` (local Laravel)
- **Production**: Frontend → `https://yourdomain.com/api` (Hostinger)

---

## Recommended Setup

**For your use case:**
1. ✅ Frontend on GitHub Pages
2. ✅ Cordova loads from GitHub Pages (Option 1)
3. ✅ Backend on Hostinger
4. ✅ Update `config.js` with Hostinger domain

**Result:**
- Web users: Visit GitHub Pages
- Mobile users: Install Cordova app (loads GitHub Pages)
- Both use Hostinger API
- One codebase, easy updates!

