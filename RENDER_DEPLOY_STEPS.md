# Deploy to Render - Step by Step

## ✅ Prerequisites (5 minutes)

### 1. Create GitHub Account (if you don't have one)
- Go to https://github.com/signup
- Fill in details
- Verify email

### 2. Install Git
- Download from https://git-scm.com/download/win
- Run installer
- Use default settings

### 3. Create Render Account
- Go to https://render.com/signup
- Click "Sign up with GitHub"
- Authorize Render

---

## 🔧 Step 1: Prepare Your Code (5 minutes)

### 1.1 Open Command Prompt
```
Windows Key + R
Type: cmd
Press Enter
```

### 1.2 Navigate to Project
```bash
cd c:\Users\Shashank Sharma\Desktop\web
```

### 1.3 Initialize Git Repository
```bash
git init
```

### 1.4 Add All Files
```bash
git add .
```

### 1.5 Create First Commit
```bash
git commit -m "KodeHost - Initial deployment"
```

---

## 📤 Step 2: Push to GitHub (5 minutes)

### 2.1 Create GitHub Repository
1. Go to https://github.com/new
2. Repository name: `kodehost`
3. Description: `Premium VPS & Minecraft Server Hosting`
4. Choose "Public" or "Private"
5. **IMPORTANT:** Do NOT check "Initialize this repository with a README"
6. Click "Create repository"

### 2.2 Copy Repository URL
- You'll see: `https://github.com/YOUR_USERNAME/kodehost.git`
- Copy this URL

### 2.3 Add Remote and Push
```bash
# Replace YOUR_USERNAME with your actual GitHub username
git remote add origin https://github.com/YOUR_USERNAME/kodehost.git

# Rename branch to main
git branch -M main

# Push code to GitHub
git push -u origin main
```

### 2.4 Verify on GitHub
- Go to https://github.com/YOUR_USERNAME/kodehost
- You should see all your files there ✅

---

## 🚀 Step 3: Deploy on Render (10 minutes)

### 3.1 Go to Render Dashboard
1. Go to https://render.com
2. Log in with GitHub
3. Click "Dashboard" in top right

### 3.2 Create New Web Service
1. Click "New +" button (blue button)
2. Select "Web Service"
3. Click "Connect account" if needed
4. Authorize Render to access GitHub

### 3.3 Select Repository
1. Find `kodehost` in the list
2. Click "Connect" next to it
3. Wait for it to load

### 3.4 Configure Service

Fill in the following information:

**Name:**
```
kodehost
```

**Environment:**
```
Node
```

**Build Command:**
```
npm install && npm run build
```

**Start Command:**
```
npm start
```

**Plan:**
```
Free
```

### 3.5 Add Environment Variables (Optional)

Click "Add Environment Variable" and add:

**Variable 1:**
- Key: `NODE_ENV`
- Value: `production`

**Variable 2:**
- Key: `NEXT_PUBLIC_API_URL`
- Value: `https://kodehost.onrender.com`

(Leave other OAuth variables empty for now)

### 3.6 Deploy
1. Scroll down
2. Click "Create Web Service" (blue button)
3. Wait for deployment to start

---

## ⏳ Step 4: Monitor Deployment (5-10 minutes)

### 4.1 Watch the Logs
1. You'll see a terminal with logs
2. It will show:
   - Building...
   - Installing dependencies...
   - Building Next.js...
   - Starting server...

### 4.2 Wait for Success
Look for this message:
```
Listening on port 3000
```

When you see this, your site is live! ✅

### 4.3 Get Your URL
Your site URL will be:
```
https://kodehost.onrender.com
```

(The exact URL will be shown in the Render dashboard)

---

## ✅ Step 5: Verify Deployment

### 5.1 Visit Your Site
1. Copy your Render URL
2. Open in browser
3. You should see your KodeHost website! 🎉

### 5.2 Test Features
- [ ] Homepage loads
- [ ] Navigation works
- [ ] Pricing page works
- [ ] Login page works
- [ ] Signup works
- [ ] Mobile responsive

---

## 🎯 Step 6: Add Custom Domain (Optional)

### 6.1 Buy a Domain
- GoDaddy: https://www.godaddy.com
- Namecheap: https://www.namecheap.com
- Google Domains: https://domains.google

### 6.2 Configure in Render
1. Go to your Render dashboard
2. Click on `kodehost` service
3. Go to "Settings" tab
4. Scroll to "Custom Domain"
5. Enter your domain (e.g., kodehost.com)
6. Click "Add Custom Domain"

### 6.3 Update DNS Records
1. Go to your domain registrar
2. Find DNS settings
3. Add CNAME record:
   - Name: `@` (or leave blank)
   - Value: (copy from Render)
4. Save changes
5. Wait 24-48 hours for DNS to update

---

## 🔄 Step 7: Update Your Code (Automatic)

### 7.1 Make Changes Locally
```bash
# Edit your code
# Then commit and push
git add .
git commit -m "Update: Add new features"
git push origin main
```

### 7.2 Automatic Redeploy
- Render will automatically detect the push
- It will rebuild and redeploy
- Your site updates automatically! ✅

---

## 🆘 Troubleshooting

### ❌ Build Failed
**Check the logs for errors:**
1. Look at the red error messages
2. Common issues:
   - Missing dependencies
   - Syntax errors
   - Wrong Node version

**Solution:**
1. Fix the error locally
2. Test: `npm run build`
3. Push to GitHub
4. Render will redeploy

### ❌ Site Shows 404
**Wait and refresh:**
1. Wait 2-3 minutes
2. Hard refresh: `Ctrl + Shift + R`
3. Try incognito mode
4. Check Render dashboard for status

### ❌ Deployment Stuck
**Manual redeploy:**
1. Go to Render dashboard
2. Click on your service
3. Click "Manual Deploy"
4. Select "main" branch
5. Click "Deploy"

### ❌ Environment Variables Not Working
**Redeploy after adding variables:**
1. Add variables in Render dashboard
2. Click "Manual Deploy"
3. Wait for new deployment
4. Refresh your site

---

## 📊 Monitoring Your Site

### Check Status
1. Go to Render dashboard
2. Click on `kodehost`
3. See status indicator (green = running)

### View Logs
1. Click "Logs" tab
2. See real-time logs
3. Check for errors

### Set Up Alerts (Optional)
1. Click "Alerts"
2. Add email for notifications
3. Get alerts if site goes down

---

## 💰 Pricing

### Free Tier
- ✅ Free hosting
- ✅ Free SSL/HTTPS
- ✅ Free domain (render.com)
- ⚠️ Spins down after 15 minutes of inactivity
- ⚠️ Limited resources

### Paid Tier ($7/month)
- ✅ Always running
- ✅ More resources
- ✅ Custom domain
- ✅ Better performance

### Upgrade When
- You have real users
- Site is too slow
- Need database

---

## 🎉 Success!

Your KodeHost site is now live!

**Your Site URL:**
```
https://kodehost.onrender.com
```

**Next Steps:**
1. ✅ Share your site with friends
2. ✅ Add custom domain
3. ✅ Set up monitoring
4. ✅ Add database (when needed)
5. ✅ Configure OAuth

---

## 📞 Need Help?

- **Render Support:** https://render.com/support
- **Render Docs:** https://render.com/docs
- **Next.js Docs:** https://nextjs.org/docs
- **GitHub Help:** https://docs.github.com

---

**Congratulations! Your KodeHost website is live! 🚀**
