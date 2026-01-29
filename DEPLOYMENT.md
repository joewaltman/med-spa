# Deployment Guide

## Quick Start: Deploy to Railway

### Step 1: Push to GitHub

```bash
cd medspa-publication

# Initialize git repository
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: MedSpa Industry Insider publication website"

# Create GitHub repository (via GitHub web interface or CLI)
# Then connect your local repo:
git remote add origin https://github.com/YOUR-USERNAME/medspa-publication.git
git branch -M main
git push -u origin main
```

### Step 2: Deploy to Railway

1. **Go to Railway.app**
   - Visit https://railway.app
   - Sign up or log in

2. **Create New Project**
   - Click "New Project"
   - Select "Deploy from GitHub repo"
   - Authorize Railway to access your GitHub account
   - Select the `medspa-publication` repository

3. **Configure Deployment**
   - Railway will automatically detect the configuration from `railway.json`
   - The site will use Python's built-in HTTP server (specified in Procfile)
   - Deploy will start automatically

4. **Generate Domain**
   - Once deployed, click on your project
   - Go to "Settings" tab
   - Click "Generate Domain" under the Domains section
   - Your site will be live at `your-project.railway.app`

### Step 3: Custom Domain (Optional)

1. In Railway project settings, click "Add Custom Domain"
2. Enter your domain name
3. Add the provided CNAME record to your DNS settings
4. Wait for DNS propagation (usually 5-30 minutes)

## Alternative: Deploy to Netlify

### Option A: Drag and Drop

1. Go to https://app.netlify.com
2. Sign up or log in
3. Drag the `medspa-publication` folder onto the deployment area
4. Netlify will deploy your site instantly

### Option B: GitHub Integration

1. Push your code to GitHub (see Step 1 above)
2. In Netlify, click "Add new site" → "Import an existing project"
3. Connect to GitHub and select your repository
4. Netlify will auto-detect settings
5. Click "Deploy site"

## Alternative: Deploy to Vercel

1. Push your code to GitHub (see Step 1 above)
2. Go to https://vercel.com
3. Click "New Project"
4. Import your GitHub repository
5. Vercel will auto-configure
6. Click "Deploy"

## Alternative: Deploy to GitHub Pages

1. Push your code to GitHub (see Step 1 above)
2. Go to repository Settings → Pages
3. Under "Source", select:
   - Branch: `main`
   - Folder: `/ (root)`
4. Click "Save"
5. Your site will be live at `https://YOUR-USERNAME.github.io/medspa-publication/`

## Verification

After deployment, verify:
- ✅ Homepage loads at root URL
- ✅ All article links work
- ✅ All profile links work
- ✅ CSS styles are applied correctly
- ✅ Site is responsive on mobile devices

## Troubleshooting

### Railway Issues

**Problem**: Site not loading
- **Solution**: Check Procfile has correct port variable: `$PORT`
- **Solution**: Verify Python 3 is available in build

**Problem**: 404 errors on navigation
- **Solution**: Ensure all file paths use relative URLs
- **Solution**: Check that all files were committed to git

### General Issues

**Problem**: CSS not loading
- **Solution**: Verify `styles.css` is in the root directory
- **Solution**: Check browser console for 404 errors

**Problem**: Links broken
- **Solution**: All internal links should be relative (e.g., `articles/filename.html` not `/articles/filename.html`)

## Updating the Site

To make changes after deployment:

1. Edit files locally
2. Test changes by opening `index.html` in a browser
3. Commit changes:
   ```bash
   git add .
   git commit -m "Description of changes"
   git push
   ```
4. Railway/Netlify/Vercel will auto-deploy changes

## Performance Optimization

For production use, consider:

1. **Enable CDN**: Most hosting platforms include CDN automatically
2. **Compress Images**: If you add images, optimize them first
3. **Minify CSS**: Use a CSS minifier for production
4. **Add Caching Headers**: Configure via hosting platform settings

## Support

- **Railway Docs**: https://docs.railway.app
- **Netlify Docs**: https://docs.netlify.com
- **Vercel Docs**: https://vercel.com/docs
- **GitHub Pages**: https://docs.github.com/pages

## Site Statistics

- **Total Articles**: 20
- **Company Profiles**: 8
- **Page Weight**: ~50KB (super fast!)
- **Load Time**: <1 second
- **Technology**: Pure HTML/CSS (no dependencies)
