# KodeHost Deployment Guide - Render

## Prerequisites
- GitHub account
- Render account (free at https://render.com)
- Git installed on your machine

## Step 1: Prepare Your Repository

### 1.1 Initialize Git (if not already done)
```bash
cd c:\Users\Shashank Sharma\Desktop\web
git init
git add .
git commit -m "Initial commit: KodeHost website"
```

### 1.2 Create GitHub Repository
1. Go to https://github.com/new
2. Create a new repository named `kodehost`
3. Don't initialize with README (we already have files)
4. Click "Create repository"

### 1.3 Push to GitHub
```bash
git remote add origin https://github.com/YOUR_USERNAME/kodehost.git
git branch -M main
git push -u origin main
```

## Step 2: Deploy to Render

### 2.1 Connect Render to GitHub
1. Go to https://render.com
2. Sign up or log in with GitHub
3. Click "New +" button
4. Select "Web Service"
5. Click "Connect account" to link GitHub
6. Authorize Render to access your GitHub repositories

### 2.2 Create Web Service
1. Select the `kodehost` repository
2. Fill in the following details:
   - **Name:** kodehost
   - **Environment:** Node
   - **Build Command:** `npm install && npm run build`
   - **Start Command:** `npm start`
   - **Plan:** Free (or upgrade as needed)

### 2.3 Add Environment Variables
In the "Environment" section, add:

```
NODE_ENV=production
NEXT_PUBLIC_API_URL=https://kodehost.onrender.com
```

For OAuth (optional):
```
NEXT_PUBLIC_GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
NEXT_PUBLIC_DISCORD_CLIENT_ID=your_discord_client_id
DISCORD_CLIENT_SECRET=your_discord_client_secret
NEXT_PUBLIC_GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret
```

### 2.4 Deploy
1. Click "Create Web Service"
2. Render will automatically start building and deploying
3. Wait for the build to complete (usually 5-10 minutes)
4. Your site will be available at: `https://kodehost.onrender.com`

## Step 3: Configure Custom Domain (Optional)

### 3.1 Add Custom Domain
1. Go to your Render dashboard
2. Select your web service
3. Go to "Settings" tab
4. Scroll to "Custom Domain"
5. Enter your domain (e.g., kodehost.com)
6. Click "Add Custom Domain"

### 3.2 Update DNS Records
1. Go to your domain registrar (GoDaddy, Namecheap, etc.)
2. Update DNS records to point to Render:
   - **Type:** CNAME
   - **Name:** @ (or your subdomain)
   - **Value:** (provided by Render)

## Step 4: Set Up OAuth (Google Example)

### 4.1 Create Google OAuth Credentials
1. Go to https://console.cloud.google.com
2. Create a new project
3. Enable Google+ API
4. Go to "Credentials"
5. Click "Create Credentials" → "OAuth 2.0 Client ID"
6. Select "Web application"
7. Add authorized redirect URIs:
   - `http://localhost:3000/client/auth/google`
   - `https://kodehost.onrender.com/client/auth/google`
8. Copy Client ID and Client Secret

### 4.2 Add to Render
1. Go to your Render web service settings
2. Add environment variables:
   - `NEXT_PUBLIC_GOOGLE_CLIENT_ID=your_client_id`
   - `GOOGLE_CLIENT_SECRET=your_client_secret`
3. Click "Save"
4. Render will automatically redeploy

## Step 5: Monitor and Maintain

### 5.1 View Logs
1. Go to your Render dashboard
2. Click on your web service
3. Click "Logs" tab to see real-time logs

### 5.2 Manual Redeploy
1. Click "Manual Deploy" button
2. Select branch (main)
3. Click "Deploy"

### 5.3 Auto-Deploy on Push
Render automatically redeploys when you push to GitHub:
```bash
git add .
git commit -m "Update: Add new features"
git push origin main
```

## Troubleshooting

### Build Fails
- Check logs in Render dashboard
- Ensure `package.json` has all dependencies
- Verify Node version compatibility

### Site Not Loading
- Check if service is running (green status in dashboard)
- Clear browser cache
- Check environment variables are set correctly

### OAuth Not Working
- Verify redirect URIs are correct
- Check environment variables are set
- Ensure credentials are valid

## Performance Tips

1. **Enable Caching:**
   - Render automatically caches static assets
   - Use `next/image` for optimized images

2. **Database (if needed):**
   - Add PostgreSQL database from Render dashboard
   - Update connection string in environment variables

3. **Monitoring:**
   - Enable Render's built-in monitoring
   - Set up alerts for errors

## Useful Commands

```bash
# Build locally to test
npm run build

# Start production server
npm start

# Check for build errors
npm run lint

# View environment variables
cat .env.local
```

## Support

- Render Docs: https://render.com/docs
- Next.js Docs: https://nextjs.org/docs
- GitHub Issues: Report bugs in your repository

## Next Steps

1. ✅ Deploy to Render
2. ✅ Set up custom domain
3. ✅ Configure OAuth providers
4. ✅ Set up database (PostgreSQL)
5. ✅ Add monitoring and alerts
6. ✅ Set up CI/CD pipeline
7. ✅ Configure email service for notifications

---

**Your site will be live at:** https://kodehost.onrender.com
