# Quick Deploy to Render - 5 Minutes

## TL;DR - Fast Track

### Step 1: Push to GitHub
```bash
cd c:\Users\Shashank Sharma\Desktop\web
git init
git add .
git commit -m "KodeHost deployment"
git remote add origin https://github.com/YOUR_USERNAME/kodehost.git
git branch -M main
git push -u origin main
```

### Step 2: Deploy on Render
1. Go to https://render.com
2. Sign in with GitHub
3. Click "New +" → "Web Service"
4. Select `kodehost` repository
5. Settings:
   - **Build Command:** `npm install && npm run build`
   - **Start Command:** `npm start`
6. Click "Create Web Service"
7. Wait 5-10 minutes ✅

### Step 3: Your Site is Live!
Visit: `https://kodehost.onrender.com`

---

## Detailed Steps

### Prerequisites
- [ ] GitHub account (https://github.com/signup)
- [ ] Render account (https://render.com/signup)
- [ ] Git installed

### 1. Prepare Local Repository

```bash
# Navigate to project
cd c:\Users\Shashank Sharma\Desktop\web

# Initialize git
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial KodeHost deployment"
```

### 2. Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `kodehost`
3. Description: "Premium VPS & Minecraft Server Hosting"
4. Choose Public or Private
5. **Don't** initialize with README
6. Click "Create repository"

### 3. Push Code to GitHub

```bash
# Add remote
git remote add origin https://github.com/YOUR_USERNAME/kodehost.git

# Rename branch
git branch -M main

# Push code
git push -u origin main
```

### 4. Deploy on Render

#### 4.1 Connect GitHub
1. Go to https://render.com
2. Click "Sign up with GitHub"
3. Authorize Render
4. Click "New +" button
5. Select "Web Service"
6. Click "Connect account" (if needed)

#### 4.2 Select Repository
1. Find and select `kodehost`
2. Click "Connect"

#### 4.3 Configure Service
Fill in these fields:

| Field | Value |
|-------|-------|
| **Name** | kodehost |
| **Environment** | Node |
| **Build Command** | `npm install && npm run build` |
| **Start Command** | `npm start` |
| **Plan** | Free |

#### 4.4 Environment Variables (Optional)
```
NODE_ENV=production
NEXT_PUBLIC_API_URL=https://kodehost.onrender.com
```

#### 4.5 Deploy
Click "Create Web Service" and wait!

### 5. Monitor Deployment

1. Go to Render Dashboard
2. Click on `kodehost` service
3. Watch the logs
4. When you see "Listening on port 3000" - it's ready! ✅

### 6. Access Your Site

Your site is now live at:
```
https://kodehost.onrender.com
```

---

## Common Issues & Fixes

### ❌ Build Failed
**Solution:** Check logs for errors
```bash
# Test build locally
npm run build
npm start
```

### ❌ Port Already in Use
**Solution:** Render handles this automatically, just wait

### ❌ Site Shows 404
**Solution:** 
1. Wait 2-3 minutes for deployment
2. Hard refresh (Ctrl+Shift+R)
3. Check logs in Render dashboard

### ❌ Environment Variables Not Working
**Solution:**
1. Add variables in Render dashboard
2. Redeploy (Manual Deploy button)
3. Wait for new deployment

---

## Next Steps

### ✅ Add Custom Domain
1. Buy domain (GoDaddy, Namecheap, etc.)
2. In Render: Settings → Custom Domain
3. Update DNS records to Render's CNAME
4. Wait 24-48 hours for DNS propagation

### ✅ Enable HTTPS
Render provides free SSL automatically ✅

### ✅ Set Up Database (Optional)
1. In Render: New → PostgreSQL
2. Copy connection string
3. Add to environment variables
4. Update code to use database

### ✅ Add Monitoring
1. Render Dashboard → Alerts
2. Set up email notifications
3. Monitor uptime and errors

---

## Useful Links

- **Render Docs:** https://render.com/docs
- **Next.js Docs:** https://nextjs.org/docs
- **GitHub Help:** https://docs.github.com
- **Your Site:** https://kodehost.onrender.com

---

## Support

If deployment fails:
1. Check Render logs (Dashboard → Logs tab)
2. Read error message carefully
3. Check DEPLOYMENT_GUIDE.md for detailed help
4. Visit Render support: https://render.com/support

---

**Congratulations! Your KodeHost site is now live! 🎉**
