# GitHub Deployment Guide - NSE Option Chain Analyzer

## Quick Deploy to GitHub (4 Steps)

### Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Create a new repository:
   - **Repository name**: `nse-option-chain-analyzer`
   - **Description**: "Real-time interactive NSE F&O option chain analyzer with AI trading signals"
   - **Visibility**: Public (to allow GitHub Pages hosting)
   - **Do NOT initialize with README** (we already have one)

3. Click "Create repository"

### Step 2: Add Remote and Push

```bash
cd /path/to/nse-option-chain-analyzer

# Add remote origin
git remote add origin https://github.com/YOUR_USERNAME/nse-option-chain-analyzer.git

# Rename master to main (optional but recommended)
git branch -M main

# Push to GitHub
git push -u origin main
```

**Replace `YOUR_USERNAME` with your GitHub username**

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (gear icon)
3. Click **Pages** in the left menu
4. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: Select **main** (or master)
   - Folder: **/root**
   - Click **Save**

5. GitHub will show: "Your site is live at `https://YOUR_USERNAME.github.io/nse-option-chain-analyzer/`"

### Step 4: Share Your Link

Your analyzer is now live at:
```
https://YOUR_USERNAME.github.io/nse-option-chain-analyzer/
```

You can access it from any device with internet!

---

## Alternative: Using GitHub Web Interface

If you prefer not to use Git command line:

1. Create empty repository on GitHub (see Step 1)
2. Click **Add file** → **Upload files**
3. Upload these files:
   - `option_chain_nse.html`
   - `README.md`
   - `CONTRIBUTING.md`
   - `LICENSE`
   - `.gitignore`
4. Add commit message: "Initial commit: NSE Option Chain Analyzer"
5. Click **Commit changes**
6. Enable GitHub Pages (see Step 3)

---

## Mobile Access

Your deployed analyzer works perfectly on mobile:

### Desktop:
```
https://YOUR_USERNAME.github.io/nse-option-chain-analyzer/
```

### Mobile (Same URL - Responsive Design):
```
https://YOUR_USERNAME.github.io/nse-option-chain-analyzer/
```

**Create a home screen shortcut for easy access:**

- **iOS**: Safari → Share → Add to Home Screen
- **Android**: Chrome → Menu → Install app / Add to home screen

---

## Features of GitHub Pages Hosting

✅ **Free**: No cost at all
✅ **Fast**: CDN-backed, global distribution
✅ **Secure**: HTTPS by default
✅ **No Maintenance**: GitHub handles everything
✅ **Version Control**: Built-in Git history
✅ **Collaboration**: Easy to accept contributions
✅ **SEO**: Google-indexed, shareable

---

## Updating Your Analyzer

### To Update Code:

```bash
# Make changes locally
vim option_chain_nse.html

# Commit changes
git add option_chain_nse.html
git commit -m "Improve PCR calculation accuracy"

# Push to GitHub
git push
```

Changes go live automatically (usually within a few minutes).

### To Update Data:

1. Extract new NSE CSV file
2. Generate new HTML with updated data
3. Commit and push
4. GitHub Pages updates automatically

---

## Troubleshooting

### "Site not live yet"
- Wait 2-3 minutes after enabling GitHub Pages
- Hard refresh browser (Ctrl+Shift+R)
- Check Settings → Pages to confirm source

### "404 Not Found"
- Ensure `option_chain_nse.html` is in root directory
- Check repo is public (Settings → Visibility)
- Verify GitHub Pages is enabled

### "Charts not displaying"
- Clear browser cache (Ctrl+Shift+Delete)
- Check Chart.js CDN is accessible
- Test in incognito/private window

### "Mobile link not working"
- Ensure GitHub Pages is enabled
- Share the full URL: `https://username.github.io/repo-name/`
- Test on different mobile browser

---

## Adding Custom Domain (Optional)

Want to use your own domain? Here's how:

1. Buy domain from registrar (Namecheap, GoDaddy, etc.)
2. Go to Settings → Pages
3. Under "Custom domain", enter your domain: `optionchains.yourdomain.com`
4. Update your domain's DNS records to GitHub's IP
5. GitHub will generate free HTTPS certificate

This is optional - GitHub's free subdomain works perfectly!

---

## Repository Structure

After pushing, your GitHub repo will look like:

```
nse-option-chain-analyzer/
├── README.md                    (Main documentation)
├── CONTRIBUTING.md              (How to contribute)
├── LICENSE                      (MIT License)
├── .gitignore                   (Git ignore rules)
├── option_chain_nse.html        (Main application)
└── .git/                        (Version history)
```

---

## Sharing Your Analyzer

### Share the Live Link:
```
Check out my NSE option chain analyzer:
https://YOUR_USERNAME.github.io/nse-option-chain-analyzer/

Real-time trading signals for BHARTIARTL, JIOFIN, SBIN, TATA STEEL!
```

### Share GitHub Repository:
```
Star and fork my options trading tool:
https://github.com/YOUR_USERNAME/nse-option-chain-analyzer
```

### Generate QR Code for Mobile:
Visit: https://qr-code-generator.com/
- Enter: `https://YOUR_USERNAME.github.io/nse-option-chain-analyzer/`
- Generate QR code
- Share it socially or print it

---

## CI/CD (Optional - For Auto-Updates)

Want to auto-update data daily? Set up GitHub Actions:

1. Create `.github/workflows/update.yml`:

```yaml
name: Update NSE Data

on:
  schedule:
    - cron: '0 16 * * MON-FRI'  # 4 PM every weekday

jobs:
  update:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Fetch NSE data
        run: python3 fetch_nse_data.py
      - name: Commit and push
        run: |
          git config user.name "NSE Bot"
          git config user.email "bot@nse.local"
          git add .
          git commit -m "Auto: Update NSE option data"
          git push
```

This requires Python script to fetch NSE data (beyond this guide).

---

## Monetization Options (If Interested)

If your analyzer becomes popular, you could:

1. **Sponsor Button** - Add GitHub sponsor button
2. **Premium Version** - Private GitHub repo with more features
3. **Documentation** - Sell tutorials on building option analyzers
4. **API** - Offer real-time data API for traders
5. **Desktop App** - Package as Electron app

But the free version is perfectly fine!

---

## Support & Questions

### Documentation Files:
- `README.md` - Usage guide
- `CONTRIBUTING.md` - Contributing guidelines
- `LICENSE` - Legal information

### GitHub Pages Issues:
- https://docs.github.com/en/pages

### NSE Data:
- Official NSE: https://www.nseindia.com/
- Option Chain: https://www1.nseindia.com/live_market/dynaContent/live_watch/opti_chai.htm

---

## Success! 🎉

Your analyzer is now:
- ✅ Version controlled (Git)
- ✅ Publicly hosted (GitHub Pages)
- ✅ Mobile accessible
- ✅ Shareable
- ✅ Updatable
- ✅ Collaborative

### Next Steps:
1. Share the URL with traders
2. Gather feedback
3. Iterate and improve
4. Watch the stars ⭐

---

**Your Live Link:**
```
https://YOUR_USERNAME.github.io/nse-option-chain-analyzer/
```

Replace `YOUR_USERNAME` with your actual GitHub username!

---

**Created**: 07-MAY-2026
**Version**: 1.0.0
**License**: MIT
