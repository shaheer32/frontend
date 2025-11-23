# Fix Vercel Build Error

## The Problem
Vercel build is failing with:
```
Rollup failed to resolve import "/src/main.jsx"
```

## Solution

I've fixed the issue by changing the import path in `index.html` from:
```html
<script type="module" src="/src/main.jsx"></script>
```

To:
```html
<script type="module" src="./src/main.jsx"></script>
```

## Steps to Fix

1. **Update your code** (already done in the desktop folder):
   - Changed `/src/main.jsx` to `./src/main.jsx` in `index.html`

2. **Commit and push to GitHub**:
   ```bash
   cd "C:\Users\SHAH\Desktop\frontend"
   git add .
   git commit -m "Fix Vercel build error - update main.jsx import path"
   git push
   ```

3. **Vercel will auto-redeploy**:
   - Vercel automatically detects new commits
   - It will rebuild with the fix
   - Check the deployment logs

## Alternative: If Still Failing

If the issue persists, try these:

1. **Clear Vercel cache**:
   - Go to Vercel dashboard
   - Project Settings → General
   - Click "Clear Build Cache"
   - Redeploy

2. **Check Root Directory**:
   - In Vercel project settings
   - Make sure "Root Directory" is empty (not `frontend` or `Frontend/frontend`)
   - Since you're deploying the `frontend` folder directly

3. **Verify File Structure**:
   Make sure your GitHub repo has this structure:
   ```
   frontend/
   ├── index.html
   ├── package.json
   ├── src/
   │   └── main.jsx
   └── ...
   ```

## Test Locally First

Before pushing, test the build locally:
```bash
cd "C:\Users\SHAH\Desktop\frontend"
npm run build
```

If it builds successfully locally, it should work on Vercel too.

