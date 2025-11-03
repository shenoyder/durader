# Quick Start: Embedding with iframe

## TL;DR - 3-Step Process

### Step 1: Customize & Upload
1. Edit `sharepoint-hover-nav-menu.html` (change the site links around line 144)
2. Upload the file to your SharePoint **Documents** library
3. Open the file and copy its URL from the browser address bar

### Step 2: Get the iframe Code
Copy this template and replace `YOUR_FILE_URL` with your file's URL:

```html
<iframe src="YOUR_FILE_URL" width="100%" height="600" frameborder="0" scrolling="no"></iframe>
```

**Example:**
```html
<iframe src="https://contoso.sharepoint.com/sites/hr/Documents/sharepoint-hover-nav-menu.html" width="100%" height="600" frameborder="0" scrolling="no"></iframe>
```

### Step 3: Add to SharePoint Page
1. Edit your SharePoint page
2. Add **Embed** web part
3. Paste the iframe code
4. Publish!

---

## Common iframe Height Values

Adjust the `height` value based on your menu size:

- **Small menu (1-3 items)**: `height="300"`
- **Medium menu (4-6 items)**: `height="500"`
- **Large menu (7-10 items)**: `height="700"`
- **Very large menu (10+ items)**: `height="900"`

---

## Troubleshooting

### "Access Denied" Error
Right-click the HTML file in SharePoint > **Manage Access** > Share with "Everyone except external users" or your target audience.

### Scrollbars Appear
Increase the iframe height value until scrollbars disappear.

### Menu Doesn't Load
1. Open the file URL directly in a new browser tab - does it work?
2. If yes: Check iframe permissions
3. If no: Check file permissions or JavaScript errors (F12 console)

---

## Alternative: Site Assets Library

If the Documents library doesn't work, try **Site Assets**:

1. Go to: `https://yoursite.sharepoint.com/sites/yoursite/SiteAssets`
2. Upload the HTML file there
3. Use the Site Assets URL in your iframe

Example:
```html
<iframe src="https://yoursite.sharepoint.com/sites/yoursite/SiteAssets/sharepoint-hover-nav-menu.html" width="100%" height="600" frameborder="0" scrolling="no"></iframe>
```

---

**Need more help?** See the full `SHAREPOINT_NAVIGATION_INSTRUCTIONS.md` file for detailed documentation.
