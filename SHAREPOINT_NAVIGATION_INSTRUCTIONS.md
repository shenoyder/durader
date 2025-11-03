# SharePoint Hover Navigation Menu - Usage Instructions

## Overview

This is a hover-to-expand hierarchical navigation menu designed specifically for SharePoint subsites. It features smooth animations, Fluent Design styling, and supports up to 3+ levels of hierarchy.

## Features

✓ Hover to expand/collapse submenus
✓ Smooth CSS transitions and animations
✓ Fluent Design inspired styling
✓ Support for multiple hierarchy levels (3+ levels deep)
✓ Clickable links to SharePoint sites
✓ Easy customization through JSON structure
✓ Self-contained single file
✓ Responsive design
✓ Accessible with keyboard navigation support

---

## How to Add to SharePoint

### Step 1: Copy the Code

1. Open the file `sharepoint-hover-nav-menu.html` in a text editor
2. Select all the code (Ctrl+A or Cmd+A)
3. Copy it to your clipboard (Ctrl+C or Cmd+C)

### Step 2: Add to SharePoint Page

1. Navigate to your SharePoint site
2. Go to the page where you want to add the navigation menu
3. Click **"Edit"** at the top right of the page
4. Click the **"+"** icon to add a new web part where you want the menu
5. Search for **"Embed"** in the web part picker
6. Select the **"Embed"** web part
7. In the Embed web part, paste your copied HTML code
8. Click outside the web part or click **"Apply"**
9. Click **"Publish"** or **"Republish"** to save your changes

### Alternative: Using the Script Editor Web Part (Classic Pages)

If you're using classic SharePoint pages:

1. Edit your page
2. Insert > Web Part
3. Under "Media and Content" category, select **"Script Editor"**
4. Click "Add"
5. In the Script Editor web part, click **"EDIT SNIPPET"**
6. Paste your HTML code
7. Click "Insert"
8. Save the page

---

## How to Customize Your Site Links

### Location to Edit

Open `sharepoint-hover-nav-menu.html` and find this section near the top of the `<script>` tag:

```javascript
// ========================================
// CUSTOMIZE YOUR SITE STRUCTURE HERE
// ========================================

const siteStructure = [
    {
        name: "HR Department",
        url: "https://site.sharepoint.com/hr",
        children: [
            {
                name: "Recruiting",
                url: "https://site.sharepoint.com/hr/recruiting",
                children: []
            },
            // ... more items
        ]
    },
    // ... more items
];
```

### Structure Explanation

Each site entry is an object with three properties:

- **`name`**: The display text for the site link
- **`url`**: The full URL to the SharePoint site
- **`children`**: An array of child sites (use empty array `[]` if no children)

### Adding a New Top-Level Site

```javascript
const siteStructure = [
    {
        name: "Your New Department",
        url: "https://yoursite.sharepoint.com/department",
        children: []
    },
    // ... existing items
];
```

### Adding Child Sites (Subsites)

```javascript
{
    name: "Parent Site",
    url: "https://yoursite.sharepoint.com/parent",
    children: [
        {
            name: "Child Site 1",
            url: "https://yoursite.sharepoint.com/parent/child1",
            children: []
        },
        {
            name: "Child Site 2",
            url: "https://yoursite.sharepoint.com/parent/child2",
            children: []
        }
    ]
}
```

### Adding Multiple Levels (3+ levels deep)

```javascript
{
    name: "Level 1",
    url: "https://yoursite.sharepoint.com/level1",
    children: [
        {
            name: "Level 2",
            url: "https://yoursite.sharepoint.com/level1/level2",
            children: [
                {
                    name: "Level 3",
                    url: "https://yoursite.sharepoint.com/level1/level2/level3",
                    children: [
                        {
                            name: "Level 4",
                            url: "https://yoursite.sharepoint.com/level1/level2/level3/level4",
                            children: []
                        }
                    ]
                }
            ]
        }
    ]
}
```

---

## Configuration Options

You can customize the menu behavior by editing the `config` object:

```javascript
const config = {
    // Delay before expanding menu on hover (milliseconds)
    hoverExpandDelay: 150,

    // Delay before collapsing menu when mouse leaves (milliseconds)
    hoverCollapseDelay: 300,

    // Show chevron icon for items with children
    showChevrons: true,

    // Open links in new tab
    openInNewTab: false
};
```

### Configuration Options Explained

- **`hoverExpandDelay`**: How long to wait before expanding a menu when hovering (in milliseconds). Lower = faster response.
- **`hoverCollapseDelay`**: How long to wait before collapsing a menu when mouse leaves. Higher value gives users more time to move to submenu.
- **`showChevrons`**: Set to `true` to show arrow icons, `false` to hide them.
- **`openInNewTab`**: Set to `true` to open all links in new tabs, `false` to open in same tab.

---

## Styling Customization

### Change the Header

Find this section in the HTML:

```html
<!-- Optional header - remove if not needed -->
<div class="nav-header">Site Navigation</div>
```

- Change "Site Navigation" to your desired text
- To remove the header entirely, delete this entire `<div>` block

### Change the Header Color

Find this CSS rule and modify the gradient colors:

```css
.nav-header {
    background: linear-gradient(135deg, #106ebe 0%, #0078d4 100%);
    color: #ffffff;
}
```

### Change Hover Color

Find and modify these values:

```css
.nav-link:hover {
    background-color: #f3f2f1;  /* Light gray background */
    color: #106ebe;              /* Blue text color */
}
```

### Change Menu Width

```css
.nav-container {
    max-width: 400px;  /* Change this value */
}
```

### Change Font Size

```css
.nav-link {
    font-size: 14px;  /* Adjust main item font size */
}

.nav-submenu .nav-link {
    font-size: 13px;  /* Adjust submenu font size */
}
```

---

## Troubleshooting

### Menu Doesn't Appear

1. Make sure you pasted the entire HTML code including `<!DOCTYPE html>` at the beginning
2. Try using the Embed web part instead of Script Editor
3. Check SharePoint's browser console for JavaScript errors (F12 > Console)

### Links Don't Work

1. Verify your URLs are correct and complete (including `https://`)
2. Check that you have access to the linked SharePoint sites
3. Ensure URLs are wrapped in quotes in the JavaScript

### Hover Doesn't Expand

1. Check that the item has `children: [...]` with at least one child
2. Verify JavaScript isn't blocked by your organization's policies
3. Try increasing the `hoverExpandDelay` in config

### Menu Too Wide/Narrow

Change the `max-width` value in the `.nav-container` CSS rule:

```css
.nav-container {
    max-width: 400px;  /* Adjust this value */
}
```

### Styling Doesn't Match SharePoint

The menu uses Fluent Design principles matching modern SharePoint. If you need to match specific brand colors:

1. Find the color values in the CSS (they look like `#106ebe`)
2. Replace them with your brand colors
3. Test in SharePoint to ensure proper contrast and readability

---

## Advanced Customization

### Loading Data from SharePoint List

If you want to dynamically load the menu structure from a SharePoint list, you would need to:

1. Create a SharePoint list with columns: Title, URL, ParentID, SortOrder
2. Use SharePoint REST API or Microsoft Graph API to fetch the data
3. Transform the data into the `siteStructure` format
4. Note: This requires additional permissions and is more complex

### Adding Icons for Each Site

You can add icon support by:

1. Adding an `icon` property to each site object
2. Modifying the `generateMenuHTML` function to include the icon
3. Using SVG icons, icon fonts, or image URLs

Example:

```javascript
{
    name: "HR Department",
    url: "https://site.sharepoint.com/hr",
    icon: "👥",  // Or use an SVG/image
    children: []
}
```

---

## Browser Compatibility

This menu works in:
- Microsoft Edge (recommended for SharePoint)
- Google Chrome
- Mozilla Firefox
- Safari

**Note**: Hover functionality requires desktop browsers. Mobile users will need to tap to expand.

---

## Support and Updates

For issues or questions:
1. Check the troubleshooting section above
2. Verify your SharePoint permissions allow custom scripts
3. Test in a browser's incognito/private mode to rule out extension conflicts

---

## Example: Complete Site Structure

Here's a comprehensive example you can use as a template:

```javascript
const siteStructure = [
    {
        name: "Human Resources",
        url: "https://contoso.sharepoint.com/sites/hr",
        children: [
            {
                name: "Onboarding",
                url: "https://contoso.sharepoint.com/sites/hr/onboarding",
                children: [
                    {
                        name: "New Hire Checklist",
                        url: "https://contoso.sharepoint.com/sites/hr/onboarding/checklist",
                        children: []
                    }
                ]
            },
            {
                name: "Benefits",
                url: "https://contoso.sharepoint.com/sites/hr/benefits",
                children: []
            }
        ]
    },
    {
        name: "Information Technology",
        url: "https://contoso.sharepoint.com/sites/it",
        children: [
            {
                name: "Help Desk",
                url: "https://contoso.sharepoint.com/sites/it/helpdesk",
                children: []
            }
        ]
    }
];
```

---

## Quick Start Checklist

- [ ] Copy the entire `sharepoint-hover-nav-menu.html` code
- [ ] Edit the `siteStructure` array with your site links
- [ ] Add the Embed web part to your SharePoint page
- [ ] Paste the code into the Embed web part
- [ ] Publish the page
- [ ] Test the hover functionality
- [ ] Adjust styling/timing as needed

---

**Version**: 1.0
**Last Updated**: 2025-11-03
**Compatible with**: SharePoint Online (Modern & Classic)
