# Deploy Frontend to Vercel - Step by Step

## Prerequisites
- Your frontend code ready
- GitHub account
- Railway backend URL (e.g., `https://hybrid-backend-production-xxxx.up.railway.app`)

---

## Step 1: Push Code to GitHub

1. **Initialize Git** (if not already done):
   ```bash
   cd "C:\Users\SHAH\Desktop\frontend"
   git init
   ```

2. **Add and commit files**:
   ```bash
   git add .
   git commit -m "Ready for Vercel deployment"
   ```

3. **Create GitHub repository**:
   - Go to [github.com](https://github.com)
   - Click "New repository"
   - Name it (e.g., `biogenesis-frontend`)
   - Don't initialize with README
   - Click "Create repository"

4. **Push to GitHub**:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/biogenesis-frontend.git
   git branch -M main
   git push -u origin main
   ```

---

## Step 2: Deploy on Vercel

1. **Go to Vercel**:
   - Visit [vercel.com](https://vercel.com)
   - Click **"Sign Up"** or **"Log In"**
   - **Use your GitHub account** to sign in

2. **Import Project**:
   - Click **"Add New Project"** or **"Import Project"**
   - You'll see your GitHub repositories
   - Click **"Import"** next to your frontend repository

3. **Configure Project**:
   - **Framework Preset**: Should auto-detect as "Vite" ✅
   - **Root Directory**: Leave empty (or `./`)
   - **Build Command**: `npm run build` (auto-filled)
   - **Output Directory**: `dist` (auto-filled)

4. **Add Environment Variable**:
   - Scroll down to **"Environment Variables"** section
   - Click **"Add"**
   - **Name**: `VITE_API_BASE`
   - **Value**: `https://your-railway-backend.up.railway.app/api`
     - Replace with your actual Railway backend URL
     - Make sure it ends with `/api`
   - **Environment**: Select all (Production, Preview, Development)
   - Click **"Add"**

5. **Deploy**:
   - Click **"Deploy"** button
   - Wait 2-3 minutes for build to complete

6. **Get Your URL**:
   - After deployment, Vercel will show:
     - **Production URL**: `https://your-app.vercel.app`
     - This is your live frontend URL! 🎉

---

## Step 3: Update Backend CORS

1. **Go to Railway Dashboard**:
   - Open your backend service
   - Go to **"Variables"** tab

2. **Add/Update Environment Variable**:
   - **Name**: `FRONTEND_URL`
   - **Value**: `https://your-app.vercel.app`
     - Use your Vercel production URL
   - Click **"Add"** or **"Update"**

---

## Step 4: Test Your Deployment

1. **Visit your Vercel URL**: `https://your-app.vercel.app`
2. **Test Features**:
   - ✅ Google login should work
   - ✅ Dashboard should load
   - ✅ Try generating a hybrid

---

## Quick Checklist

- [ ] Code pushed to GitHub
- [ ] Vercel account created (via GitHub)
- [ ] Project imported from GitHub
- [ ] Environment variable `VITE_API_BASE` added
- [ ] Deployed successfully
- [ ] Got production URL from Vercel
- [ ] Updated Railway backend `FRONTEND_URL`
- [ ] Tested login and generation

---

## Your URLs Summary

After deployment, you'll have:

- **Frontend**: `https://your-app.vercel.app`
- **Backend**: `https://your-backend.up.railway.app`
- **Python/AI**: Your Hugging Face Space URL

All three should be connected and working! 🚀

