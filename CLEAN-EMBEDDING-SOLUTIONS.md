# SharePoint Navigation Menu - Clean Embedding Solutions

## The Problem

When you upload an HTML file to a SharePoint document library and try to embed it, SharePoint often wraps it in a document preview interface instead of rendering the HTML directly. This shows library navigation, headers, and other unwanted elements.

## Solutions (Best to Simplest)

---

## ✅ Solution 1: GitHub Pages (FREE & RECOMMENDED)

This gives you a clean, direct URL with no SharePoint remnants. It's completely free and takes 5 minutes.

### Step-by-Step:

1. **Create a GitHub account** (if you don't have one): https://github.com/join

2. **Create a new repository**:
   - Go to https://github.com/new
   - Repository name: `sharepoint-navigation` (or any name)
   - Make it **Public**
   - Click "Create repository"

3. **Upload your HTML file**:
   - Click "uploading an existing file"
   - Drag and drop `sharepoint-hover-nav-menu.html`
   - **Important**: Rename it to `index.html` before uploading
   - Click "Commit changes"

4. **Enable GitHub Pages**:
   - Go to repository Settings
   - Scroll down to "Pages" section (left sidebar)
   - Under "Source", select "Deploy from a branch"
   - Branch: Select `main` and `/ (root)`
   - Click "Save"

5. **Get your URL** (wait 1-2 minutes for deployment):
   - Your navigation will be at: `https://YOUR-USERNAME.github.io/sharepoint-navigation/`
   - Example: `https://johndoe.github.io/sharepoint-navigation/`

6. **Embed in SharePoint**:
   - Edit your SharePoint page
   - Add **Embed** web part
   - Paste this iframe code:

```html
<iframe src="https://YOUR-USERNAME.github.io/sharepoint-navigation/" width="100%" height="600" frameborder="0" style="border:none;"></iframe>
```

### Updating the Menu Later:
- Go to your GitHub repository
- Click on `index.html`
- Click the pencil icon (Edit)
- Make your changes
- Click "Commit changes"
- Changes appear on your site in 1-2 minutes

**Pros**: ✓ Clean rendering, ✓ No SharePoint remnants, ✓ Free forever, ✓ Easy updates, ✓ Fast loading
**Cons**: - Requires GitHub account (free), - Menu links are public (but that's usually fine)

---

## ✅ Solution 2: Free External Hosting Services

If you prefer not to use GitHub, try these alternatives:

### Option A: Netlify Drop (Easiest)
1. Go to https://app.netlify.com/drop
2. Rename `sharepoint-hover-nav-menu.html` to `index.html`
3. Drag and drop the file
4. Get your URL: `https://random-name.netlify.app`
5. Embed in SharePoint with iframe

### Option B: Azure Static Web Apps (If you have Azure)
1. Create a Storage Account
2. Enable "Static website"
3. Upload as `index.html`
4. Use the static website URL

### Option C: Vercel
1. Sign up at https://vercel.com
2. Create new project
3. Upload your HTML file
4. Get deployment URL

---

## ⚠️ Solution 3: SharePoint Site Assets (May Work)

Some SharePoint environments allow direct rendering from Site Assets:

1. Navigate to: `https://yoursite.sharepoint.com/SiteAssets`
2. Upload `sharepoint-hover-nav-menu.html`
3. Copy the file URL
4. Try adding `?web=1` to force web view:

```html
<iframe src="https://yoursite.sharepoint.com/SiteAssets/sharepoint-hover-nav-menu.html?web=1" width="100%" height="600" frameborder="0"></iframe>
```

**Note**: This may still show SharePoint chrome depending on your tenant settings. If it doesn't work cleanly, use Solution 1 or 2.

---

## ⚠️ Solution 4: Try Query Parameters

If you want to keep using SharePoint document library, try these URL parameters:

```html
<!-- Try adding ?web=1 -->
<iframe src="YOUR_FILE_URL?web=1" width="100%" height="600" frameborder="0"></iframe>

<!-- Or try ?action=embedview -->
<iframe src="YOUR_FILE_URL?action=embedview" width="100%" height="600" frameborder="0"></iframe>

<!-- Or try both -->
<iframe src="YOUR_FILE_URL?web=1&action=embedview" width="100%" height="600" frameborder="0"></iframe>
```

**Note**: Results vary by SharePoint configuration. If these still show library interface, use external hosting (Solution 1).

---

## 🔧 Solution 5: SharePoint Framework (Advanced)

If your organization has strict policies against external hosting:

This requires development skills and SharePoint admin permissions:
1. Build a SharePoint Framework (SPFx) web part
2. Package the navigation menu as an SPFx solution
3. Deploy to your App Catalog
4. Add the web part to your page

**Only use this if**: You have SharePoint development experience AND external hosting is not allowed.

---

## Comparison Table

| Solution | Clean Display | Difficulty | Cost | Updates |
|----------|--------------|------------|------|---------|
| GitHub Pages | ✅ Perfect | Easy | Free | Easy via GitHub |
| Netlify Drop | ✅ Perfect | Very Easy | Free | Re-upload file |
| Azure Static | ✅ Perfect | Medium | Free/Paid tier | Easy via portal |
| Site Assets + ?web=1 | ⚠️ Maybe | Easy | Free | Easy |
| SPFx Web Part | ✅ Perfect | Hard | Free | Requires rebuild |

---

## My Recommendation

**Use GitHub Pages (Solution 1)**. Here's why:

✓ Takes 5 minutes to set up
✓ Completely free forever
✓ Clean, professional display with zero SharePoint remnants
✓ Easy to update (just edit the file in GitHub)
✓ Fast, reliable hosting
✓ No special permissions needed
✓ Works in any SharePoint tenant

The only "downside" is that your navigation menu HTML is publicly accessible (anyone with the link can see it), but since it's just navigation links to your SharePoint sites (which already have their own permissions), this is usually not a security concern.

---

## Quick Start: GitHub Pages Method

```bash
# Detailed steps:

1. Go to https://github.com/new
2. Name: sharepoint-navigation
3. Public repository
4. Create repository

5. Upload file (rename to index.html)
6. Settings > Pages > Deploy from branch (main)
7. Wait 2 minutes

8. Embed code:
<iframe src="https://YOUR-USERNAME.github.io/sharepoint-navigation/"
        width="100%"
        height="600"
        frameborder="0"
        style="border:none;">
</iframe>
```

---

## Need Help?

**If you're not comfortable with GitHub**, I recommend **Netlify Drop** (Solution 2, Option A):
- No account needed
- Just drag and drop
- Instant URL
- Super simple

Let me know which solution you'd like to proceed with and I can provide more detailed guidance!
