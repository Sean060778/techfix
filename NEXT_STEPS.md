# Next Steps After GitHub Pages Deployment

## ✅ What's Done
- ✅ Frontend uploaded to GitHub
- ✅ GitHub Pages enabled
- ✅ Site live at: https://sean060778.github.io/techfix/

---

## 🔧 Step 1: Update API URL

Your frontend needs to connect to your Hostinger backend API.

### Update config.js on GitHub:

1. **Go to your GitHub repository**
   - Visit: https://github.com/sean060778/techfix (or your repo URL)

2. **Click on `js/config.js`**

3. **Click the pencil icon** (Edit file) ✏️

4. **Find line 13** and change:
   ```javascript
   production: 'https://yourdomain.com/api'
   ```
   
   **Replace `yourdomain.com` with your actual Hostinger domain**
   
   Example:
   ```javascript
   production: 'https://techfix.yourdomain.com/api'
   ```
   or
   ```javascript
   production: 'https://api.yourdomain.com/api'
   ```

5. **Scroll down** → Click **"Commit changes"**

6. **Wait 1-2 minutes** for GitHub Pages to update

---

## 🧪 Step 2: Test Your Site

1. **Visit your site**: https://sean060778.github.io/techfix/

2. **Open Browser Console** (Press F12)

3. **Check the log** - Should show:
   ```
   🚀 Production Mode - API URL: https://yourdomain.com/api
   ```

4. **Try logging in** or **registering**
   - If you see CORS errors, proceed to Step 3

---

## 🔒 Step 3: Configure CORS on Hostinger Backend

Your Laravel backend needs to allow requests from GitHub Pages.

### On Hostinger:

1. **Upload your backend** (if not done yet)
   - Upload `backend/` folder to Hostinger
   - See `../DEPLOYMENT.md` for detailed instructions

2. **Edit CORS configuration**
   - File: `backend/config/cors.php`
   - Add your GitHub Pages URL to allowed origins:

   ```php
   'allowed_origins' => [
       'https://sean060778.github.io',
       'https://yourdomain.com', // Your Hostinger domain
   ],
   ```

3. **Save and test**

---

## 📋 Step 4: Deploy Backend to Hostinger

If you haven't deployed the backend yet:

### Quick Steps:

1. **Upload backend files** to Hostinger
   - Upload entire `backend/` folder
   - Move `backend/public/*` to `public_html/`

2. **Create `.env` file**
   ```env
   APP_NAME="TechFix Repairs"
   APP_ENV=production
   APP_DEBUG=false
   APP_URL=https://yourdomain.com

   DB_CONNECTION=mysql
   DB_HOST=localhost
   DB_PORT=3306
   DB_DATABASE=your_database_name
   DB_USERNAME=your_database_user
   DB_PASSWORD=your_database_password
   ```

3. **Run migrations**
   ```bash
   php artisan migrate
   php artisan db:seed
   ```

4. **Configure CORS** (see Step 3 above)

5. **Test API**
   - Visit: `https://yourdomain.com/api/devices`
   - Should return JSON data

---

## ✅ Step 5: Final Checklist

- [ ] Updated `config.js` with Hostinger API URL
- [ ] Backend deployed to Hostinger
- [ ] CORS configured to allow GitHub Pages
- [ ] Database created and migrated
- [ ] Tested login/registration
- [ ] Tested booking functionality
- [ ] Tested admin panel
- [ ] Tested staff panel

---

## 🐛 Troubleshooting

### "CORS Error" in browser console
- **Solution**: Update `backend/config/cors.php` to include `https://sean060778.github.io`

### "API URL not found" or "404"
- **Check**: Is your Hostinger backend deployed?
- **Check**: Is the API URL correct in `config.js`?
- **Test**: Visit `https://yourdomain.com/api/devices` directly

### "Network Error" or "Failed to fetch"
- **Check**: Is your Hostinger backend running?
- **Check**: Is the domain correct?
- **Check**: Is SSL/HTTPS enabled on Hostinger?

### Site shows but API doesn't work
- **Open browser console** (F12)
- **Check Network tab** - see what requests are failing
- **Verify API URL** in console log

---

## 🎉 You're Almost Done!

Once you:
1. ✅ Update API URL in `config.js`
2. ✅ Deploy backend to Hostinger
3. ✅ Configure CORS

Your full-stack application will be live! 🚀

---

## 📞 Need Help?

- Check `DEPLOYMENT.md` for backend deployment details
- Check `CORDOVA_SETUP.md` for mobile app setup
- Test API endpoints directly: `https://yourdomain.com/api/devices`

