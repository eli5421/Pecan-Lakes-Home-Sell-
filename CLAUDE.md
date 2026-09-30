# CLAUDE.md — pecan-lakes-home-sell

**Project**: Pecan Lakes Home Sale / Real Estate Platform  
**Type**: Node.js / Next.js Web Application  
**Repo**: https://github.com/eli5421/Pecan-Lakes-Home-Sell-  
**Deployment**: Vercel  
**Primary Maintainer**: Eli Garcia (eli@thechurchlawton.com)

---

## 📋 Cross-Device Rules

This project is part of a **unified 4-repo, 4-device workspace**. Read `SYNC_ARCHITECTURE.md` for the full architecture.

**Golden Rules:**
1. GitHub is source of truth
2. `git pull` before starting work
3. Commit frequently, push before switching devices
4. Keep `.env` in `.gitignore`—never commit secrets
5. Test changes before committing
6. Stop on merge conflicts—resolve locally before pushing

---

## 🌳 Project Structure

```
pecan-lakes-home-sell/
├── CLAUDE.md (this file)
├── README.md
├── vercel.json (deployment config)
├── package.json
├── .env.example (commit this, create .env locally)
├── pages/
├── components/
├── public/
├── docs/ (marketing strategy)
├── .git/ (syncs with GitHub)
└── node_modules/ (local only, not synced)
```

---

## 🔌 Development Environment

### Setup (First Time on Any Device)

```bash
# 1. Clone if needed
git clone https://github.com/eli5421/Pecan-Lakes-Home-Sell-

# 2. Install dependencies
npm install

# 3. Create local .env from template
cp .env.example .env
# Edit .env with your local values (if needed)

# 4. Start development server
npm run dev
# Server runs at http://localhost:3000
```

### Daily Workflow

```bash
# Start of day
git pull origin main           # Get latest changes
npm install                     # Update dependencies if needed
npm run dev                     # Start dev server

# During work
# Edit files in pages/, components/, etc.
# Test in browser at localhost:3000
# Commit frequently

# End of session
git add .                       # Stage changes
git commit -m "feat: ..."       # Commit with clear message
git push origin <branch>        # Push to GitHub
```

---

## 🌿 Branch Strategy

### Branch Naming
- **Features**: `feature/description` (e.g., `feature/property-search`)
- **Bugs**: `fix/description` (e.g., `fix/form-validation`)
- **Refactors**: `refactor/description`
- **Cloud sessions**: `claude/random-name-xxxx` (auto-generated)

### Which Branch to Use
- **Main**: Stable, live platform code
- **Feature branches**: Your working branches

### Workflow
```
1. git checkout -b feature/my-feature origin/main
2. Make changes & test locally
3. git commit -m "feat: description"
4. git push -u origin feature/my-feature
5. Create PR on GitHub for review
6. Merge to main when approved (triggers Vercel deploy)
7. Delete feature branch after merge
```

---

## 💾 Environment & Deployment

### `.env` Management
```
✅ DO commit: .env.example (shows structure)
❌ DON'T commit: .env (actual secrets)
```

### Vercel Deployment
- **Live URL**: See vercel.json and GitHub README
- **Auto-deploy**: Pushing to main triggers Vercel build
- **Preview URLs**: Each PR gets a preview deployment

### Before Merging to Main
```bash
# 1. Test locally
npm run dev
# Visit http://localhost:3000 and test changes

# 2. Build production version locally
npm run build

# 3. Verify no build errors
npm run start (optional, to test production build)

# 4. If OK, commit and push
git push origin feature/name

# 5. Vercel auto-deploys when merged to main
```

---

## 🧪 Testing & Validation

### Before Committing
```bash
# Check for errors
npm run lint               # ESLint
npm run type-check         # TypeScript (if applicable)

# Test in browser
# 1. Start dev server: npm run dev
# 2. Visit http://localhost:3000
# 3. Test all functionality:
#    - Property search
#    - Listing pages
#    - Forms and submissions
#    - Mobile view (use DevTools)
# 4. If OK, commit
```

### Common Checks
- [ ] No console errors
- [ ] All pages load
- [ ] Search works
- [ ] Forms submit correctly
- [ ] Mobile responsive
- [ ] Images load
- [ ] Performance acceptable

---

## 📱 Cloud vs. Local Work

### ✅ Do in Cloud Sessions
- Reading code
- Light edits to content/copy
- Code reviews
- Documentation updates
- Quick styling tweaks
- Checking status from mobile/web

### 🖥️ Must Do Locally
- Running `npm install`
- Running dev server (`npm run dev`)
- Building production (`npm run build`)
- Testing search/database features
- Performance testing
- Complex debugging

### 🔄 Hybrid Workflow
```
Desktop:
  → Start cloud session
  → Clone repo
  → Make changes, commit
  → git push

Laptop:
  → Resume cloud session
  → Or: git pull latest
  → Continue work
  → git push

Mobile/Web:
  → View session
  → Read code
  → Light content edits
```

---

## 🚀 Live Platform

- **Website**: Check README.md for live URL
- **Status**: Check Vercel deployment dashboard
- **Analytics**: Check Vercel metrics

---

## 📊 Useful Commands

```bash
# Status & commits
git status                      # Current state
git log --oneline -5            # Last 5 commits

# Development
npm install                     # Install deps
npm run dev                     # Start dev server
npm run build                   # Production build
npm run lint                    # Check code style

# Git operations
git pull origin main            # Get latest
git push origin feature/name    # Push branch
git commit -m "msg"             # Commit changes
git checkout -b feature/name    # Create branch
```

---

## 🆘 Troubleshooting

**Dev server won't start**
→ Delete `.next` folder and try again: `rm -rf .next && npm run dev`

**Vercel deployment fails**
→ Check the deployment logs on Vercel dashboard. Common issues:
  - Build error (check `npm run build` locally)
  - Missing environment variables
  - Node version mismatch

**Search not working**
→ Check database connection in .env is correct

---

## 🎯 Priorities (Current)

See `PROJECT_STATUS.md` for today's priority and known issues.

---

## 📞 Cloud-Ready Status

- ✅ Can clone in cloud sessions
- ✅ Can make edits in cloud
- ✅ Can read code
- ❌ Can't run `npm install` easily in cloud
- ✅ Best for: Light edits, code review, documentation

---

## ✨ Remember

**This is part of a 4-device, 4-repo unified workspace.**

- Always check `SYNC_ARCHITECTURE.md` for cross-device rules
- Always push before switching devices
- Always pull before starting work
- Keep GitHub as your source of truth

**Start on Desktop → Test locally → Push to GitHub → Vercel auto-deploys → Check on all devices.**

---

*Last Updated: 2026-09-30*  
*Maintained by: Eli Garcia*  
*Part of: lawton-crm + 3 other repos*
