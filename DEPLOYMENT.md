# Deployment Guide - Pecan Lakes Property Website

## Quick Deployment to Vercel

The site is ready to deploy. Follow these steps to get it live:

### Option 1: One-Click Deploy (Easiest)

1. Go to https://vercel.com/new
2. Click "From Git Repository" 
3. Connect your GitHub account (or create one if needed)
4. Select this repository
5. Vercel will auto-detect the settings
6. Click "Deploy"

Done! Your site will be live in ~2-3 minutes at a `.vercel.app` domain.

### Option 2: Deploy from Local

1. **Install Vercel CLI:**
   ```bash
   npm install -g vercel
   ```

2. **From the project directory:**
   ```bash
   cd pecan-lakes-website
   vercel
   ```

3. **Follow the prompts:**
   - Answer questions about your project
   - Confirm deployment
   - Your URL will be provided

4. **To redeploy after changes:**
   ```bash
   vercel --prod
   ```

### Option 3: GitHub First (Recommended)

If you want a private GitHub repository:

1. **Create private GitHub repo:**
   - Go to https://github.com/new
   - Name: `pecan-lakes-website`
   - Make it Private
   - Create repository

2. **Add remote and push (run in project directory):**
   ```bash
   git remote add origin https://github.com/YOUR-USERNAME/pecan-lakes-website.git
   git branch -M main
   git push -u origin main
   ```

3. **Deploy from GitHub:**
   - Go to https://vercel.com/import
   - Select your GitHub repo
   - Click Import
   - Vercel deploys automatically
   - Get your live URL

## After Deployment

### Your Live Site
- Main site: `https://your-domain.vercel.app`
- Call log: `https://your-domain.vercel.app/call-log.html`

### Test the Site
- ✓ Check hero image and gallery load
- ✓ Test Call Now button on mobile
- ✓ Verify video plays
- ✓ Click "View on Zillow" link
- ✓ Check analytics in browser console: `getAnalytics()`

### Facebook Post Link
Once you have your Vercel URL, use it in your Facebook post:
- `https://your-domain.vercel.app?source=facebook`

This tracks visits coming from your Facebook post.

## Tracking & Analytics

### Page Visit Analytics
- Stored locally in your browser
- View in console: `getAnalytics()`
- Shows: page views, call button taps, visitor source

### Call & Showing Log
- Access at `/call-log.html`
- Log each inquiry manually
- Export to CSV anytime
- Tracks: name, phone, date, status, notes

## Support

For showing inquiries: (580) 498-0224
Listing Agent: April Elkouri, Real Estate Experts, LLC

---

**Questions?** Review the site on localhost first:
```bash
python3 -m http.server 8000
# Open http://localhost:8000
```
