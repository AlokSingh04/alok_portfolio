# Vercel Deployment Guide - Step by Step

## Method 1: Via Vercel Dashboard (Recommended) ✅

### Step 1: Create Vercel Account
1. Go to https://vercel.com
2. Click **"Sign Up"**
3. Choose **"Continue with GitHub"**
4. Authorize Vercel to access your GitHub account

### Step 2: Import Your Repository
1. In Vercel Dashboard, click **"Add New..."** → **"Project"**
2. Find and select **`AlokSingh04/alok_portfolio`** repository
3. Click **"Import"**

### Step 3: Configure Project Settings
**IMPORTANT:** Set these values:
- **Framework Preset:** `Other` or `Other (Static)`
- **Root Directory:** `portfolio` ⚠️ (This is crucial!)
- **Build Command:** Leave empty (static site, no build needed)
- **Output Directory:** `.` (current directory)
- **Install Command:** Leave empty

### Step 4: Deploy
1. Click **"Deploy"** button
2. Wait 1-2 minutes for deployment
3. Your site will be live at: `https://alok-portfolio-xxxxx.vercel.app`

### Step 5: Custom Domain (Optional)
1. Go to Project Settings → **Domains**
2. Add your custom domain (e.g., `aloksingh.dev`)
3. Follow DNS configuration instructions

---

## Method 2: Via Vercel CLI (Alternative)

### Prerequisites
- Node.js installed (v16+)
- Git installed

### Step 1: Install Vercel CLI
```bash
npm install -g vercel
```

### Step 2: Login to Vercel
```bash
vercel login
```
This will open browser for authentication.

### Step 3: Navigate to Project
```bash
cd D:\class\coding\vishal_portfolio\portfolio
```

### Step 4: Deploy
```bash
vercel
```

Follow the prompts:
- **Set up and deploy?** → Yes
- **Which scope?** → Your account
- **Link to existing project?** → No (first time)
- **Project name?** → `alok-portfolio` (or press Enter for default)
- **Directory?** → `.` (current directory)
- **Override settings?** → No

### Step 5: Production Deploy
```bash
vercel --prod
```

---

## Post-Deployment Checklist

### ✅ Update Meta Tags
After deployment, update these in `index.html`:
- Line 25: `og:image` → Your Vercel URL
- Line 26: `og:url` → Your Vercel URL  
- Line 35: `twitter:image` → Your Vercel URL
- Line 38: `canonical` → Your Vercel URL

### ✅ Test Contact Form
1. Go to your live Vercel URL
2. Fill out the contact form
3. Check if Formspree receives the submission
4. Verify email delivery

### ✅ Test All Pages
- Home page loads correctly
- About section scrolls smoothly
- Projects filter works
- Contact form submits successfully
- Resume downloads correctly
- Nexus Card opens properly

---

## Troubleshooting

### Issue: 404 on refresh
**Solution:** `vercel.json` is already configured with rewrites. If still happening, check Root Directory is set to `portfolio`.

### Issue: Assets not loading
**Solution:** Check that all asset paths use relative URLs (starting with `./` or `/`).

### Issue: Form not working
**Solution:** 
- Verify Formspree endpoint: `https://formspree.io/f/manayweg`
- Check browser console for errors
- Ensure Formspree account is verified

### Issue: Build fails
**Solution:**
- Make sure Root Directory = `portfolio`
- Build Command should be empty
- Check Vercel build logs for specific errors

---

## Environment Variables (If Needed Later)

If you need to add environment variables:
1. Go to Project Settings → **Environment Variables**
2. Add variables (e.g., API keys)
3. Redeploy

---

## Continuous Deployment

Once connected to GitHub:
- Every push to `main` branch = automatic deployment
- Preview deployments for pull requests
- Zero-downtime deployments

---

## Need Help?

- Vercel Docs: https://vercel.com/docs
- Vercel Support: https://vercel.com/support
- Your Repo: https://github.com/AlokSingh04/alok_portfolio

