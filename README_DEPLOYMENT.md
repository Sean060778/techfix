# Quick Deployment Guide

## ✅ Already Done!
- ✅ All HTML files now include `config.js`
- ✅ All JS files (`app.js`, `admin.js`, `staff.js`) use `API_URL` from `config.js`
- ✅ Automatic environment detection (development vs production)

---

## 🚀 Frontend Deployment

### For GitHub Pages:

1. **Update API URL**
   - Open `js/config.js`
   - Change line 13:
     ```javascript
     production: 'https://yourdomain.com/api'
     ```
     Replace `yourdomain.com` with your Hostinger domain

2. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/yourusername/techfix-frontend.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to repository Settings → Pages
   - Source: Deploy from branch `main`
   - Your site: `https://yourusername.github.io/techfix-frontend/`

### For Cordova:

**Option 1: Load from GitHub Pages (Recommended)** ⭐
1. **Deploy to GitHub Pages first** (see above)
2. **Create Cordova app**
   ```bash
   cordova create techfix-app com.techfix.app TechFix
   cd techfix-app
   ```
3. **Edit `config.xml`** - Point to GitHub Pages:
   ```xml
   <content src="https://yourusername.github.io/techfix-frontend/index.html" />
   ```
4. **Build**
   ```bash
   cordova platform add android
   cordova build android
   ```
   ✅ Updates automatically when you push to GitHub!

**Option 2: Bundle Files Locally**
1. **Update API URL** in `js/config.js` with your Hostinger domain
2. **Build Cordova App**
   ```bash
   cordova create techfix-app com.techfix.app TechFix
   cd techfix-app
   cp -r ../frontend/* www/
   cordova platform add android
   cordova build android
   ```
   The `config.js` will automatically detect Cordova and use production API URL.

See `CORDOVA_SETUP.md` for detailed instructions.

---

## 🔧 Backend (Hostinger)

### Quick Steps:
1. Upload `backend/` folder to Hostinger
2. Move `backend/public/*` to `public_html/`
3. Update `public_html/index.php` paths (change `../` to correct paths)
4. Create `.env` file with your database credentials
5. Run `php artisan migrate`
6. Configure CORS in `config/cors.php` - add your GitHub Pages URL

See `../DEPLOYMENT.md` for detailed instructions.

---

## 📝 Files to Update Before Deployment

1. **`js/config.js`** - Update production API URL (line 13)
2. **`backend/.env`** - Add database credentials
3. **`backend/config/cors.php`** - Add GitHub Pages URL to allowed origins

---

## ✅ Pre-Deployment Checklist

- [x] All HTML files include `config.js`
- [x] All JS files use `API_URL` from config
- [ ] Updated API URL in `js/config.js` with your Hostinger domain
- [ ] Uploaded Laravel backend to Hostinger
- [ ] Created `.env` file with production settings
- [ ] Configured CORS with GitHub Pages URL
- [ ] Tested API endpoints
- [ ] Tested frontend on GitHub Pages

---

## 🎯 How It Works

- **Development**: When running locally (`localhost` or `127.0.0.1`), uses `http://127.0.0.1:8000/api`
- **Production**: When on GitHub Pages or Cordova, automatically uses your Hostinger API URL
- **No code changes needed** - just update the domain in `config.js`!

