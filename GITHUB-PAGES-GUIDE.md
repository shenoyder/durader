# GitHub Pages - Step-by-Step Visual Guide

## Why GitHub Pages?

✅ **Free forever**
✅ **No SharePoint remnants** - clean, direct rendering
✅ **Easy to update** - just edit the file
✅ **Fast & reliable** - hosted on GitHub's infrastructure
✅ **Takes 5 minutes** - no technical expertise needed

---

## Step 1: Create GitHub Account (Skip if you have one)

1. Go to: **https://github.com/join**
2. Enter your email, create a password
3. Verify your email
4. Done!

---

## Step 2: Create a New Repository

1. Go to: **https://github.com/new**

2. Fill in these details:
   - **Repository name**: `sharepoint-navigation` (or any name you like)
   - **Description**: (optional) "SharePoint site navigation menu"
   - **Visibility**: Select **"Public"**
   - Leave everything else as default

3. Click **"Create repository"**

---

## Step 3: Upload Your HTML File

1. You'll see a page with setup instructions. Look for the text:
   **"uploading an existing file"** (it's a link in the middle of the page)

2. Click that link

3. **IMPORTANT - Rename your file first**:
   - On your computer, rename `sharepoint-hover-nav-menu.html` to `index.html`
   - (GitHub Pages requires the main file to be named `index.html`)

4. Drag and drop `index.html` into the upload area

5. Scroll down and click **"Commit changes"** (green button)

---

## Step 4: Enable GitHub Pages

1. Click **"Settings"** (tab at the top of your repository)

2. In the left sidebar, scroll down and click **"Pages"**

3. Under **"Source"**:
   - Click the dropdown that says "None"
   - Select **"Deploy from a branch"**

4. Under **"Branch"**:
   - Select **`main`** from the first dropdown
   - Select **`/ (root)`** from the second dropdown

5. Click **"Save"**

6. You'll see a message: "GitHub Pages source saved"

---

## Step 5: Wait for Deployment (1-2 minutes)

1. Stay on the Pages settings page

2. Refresh the page after about 1 minute

3. You'll see a message at the top:
   **"Your site is live at https://YOUR-USERNAME.github.io/sharepoint-navigation/"**

4. Click that URL to test it - you should see your navigation menu!

---

## Step 6: Embed in SharePoint

1. Copy your GitHub Pages URL:
   ```
   https://YOUR-USERNAME.github.io/sharepoint-navigation/
   ```

2. Create the iframe code (replace YOUR-USERNAME with your actual GitHub username):
   ```html
   <iframe src="https://YOUR-USERNAME.github.io/sharepoint-navigation/"
           width="100%"
           height="600"
           frameborder="0"
           style="border:none;">
   </iframe>
   ```

3. In SharePoint:
   - Edit your page
   - Click **+** to add a web part
   - Search for **"Embed"**
   - Select the Embed web part
   - Paste your iframe code
   - Click outside the web part
   - **Publish** the page

4. **Done!** Your navigation menu should now appear cleanly with no SharePoint library interface.

---

## Customizing Your Site Links

### Option A: Edit Directly on GitHub (Easiest)

1. Go to your repository: `https://github.com/YOUR-USERNAME/sharepoint-navigation`

2. Click on `index.html`

3. Click the **pencil icon** (✏️) at the top right to edit

4. Find the `siteStructure` array (around line 144):
   ```javascript
   const siteStructure = [
       {
           name: "HR Department",
           url: "https://site.sharepoint.com/hr",
           children: [...]
       },
       // Add or modify your sites here
   ];
   ```

5. Make your changes

6. Scroll down and click **"Commit changes"**

7. In the popup, click **"Commit changes"** again

8. Wait 1-2 minutes - your changes will automatically appear on your SharePoint page!

### Option B: Edit Locally and Re-upload

1. Download `index.html` from your repository
2. Edit it on your computer
3. Go to your repository
4. Click on `index.html`
5. Click the pencil icon to edit
6. Delete all the old content
7. Copy and paste your updated HTML
8. Commit changes

---

## Troubleshooting

### Page shows "404 - Not Found"
- Wait 2-3 minutes after enabling Pages - deployment takes time
- Make sure you named the file `index.html` (not `sharepoint-hover-nav-menu.html`)
- Check that your repository is **Public**

### Changes don't appear
- Wait 1-2 minutes after committing - GitHub Pages needs time to rebuild
- Hard refresh your SharePoint page (Ctrl+F5 or Cmd+Shift+R)
- Clear your browser cache

### SharePoint won't let me embed
- Some organizations block external iframes
- Contact your SharePoint admin about allowing `github.io` domains
- Alternative: Use the internal SharePoint solutions (see CLEAN-EMBEDDING-SOLUTIONS.md)

---

## Updating Your Menu Later

Whenever you need to add or change site links:

1. Go to `https://github.com/YOUR-USERNAME/sharepoint-navigation`
2. Click on `index.html`
3. Click the pencil icon (✏️)
4. Edit the `siteStructure` array
5. Commit changes
6. Wait 1-2 minutes
7. Your SharePoint page automatically shows the updates!

---

## Security Note

Your `index.html` file is publicly accessible (anyone with the link can view it). This is fine because:

- It only contains navigation links (no sensitive data)
- The actual SharePoint sites have their own permissions
- Only authorized users can access the SharePoint sites themselves
- It's the same information users would see in SharePoint's built-in navigation

If your organization requires that even the navigation structure be private, you'll need to use an internal SharePoint solution instead.

---

## Example: Complete URL

Here's what your final iframe code might look like:

```html
<iframe src="https://johndoe.github.io/sharepoint-navigation/"
        width="100%"
        height="600"
        frameborder="0"
        style="border:none;">
</iframe>
```

Where:
- `johndoe` = your GitHub username
- `sharepoint-navigation` = your repository name

---

## Benefits Summary

| What You Get | Why It Matters |
|--------------|----------------|
| Clean display | No SharePoint library interface |
| Fast loading | GitHub's CDN is super fast |
| Free hosting | No cost, unlimited bandwidth |
| Easy updates | Edit directly on GitHub |
| Version control | See history of all changes |
| Always available | 99.9%+ uptime |
| No maintenance | GitHub handles everything |

---

**Ready to get started?** Follow Step 1 above!

**Already have it set up?** Just share your GitHub Pages URL and I can help you create the iframe code.

**Prefer a different solution?** Check out `CLEAN-EMBEDDING-SOLUTIONS.md` for alternatives like Netlify Drop or Azure.
