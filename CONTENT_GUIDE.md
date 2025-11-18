# Content Management Guide

## Overview

The home page content is now managed through a simple Markdown file, making it easy to update without touching HTML or CSS code.

## Quick Start

### To Update Home Page Content:

1. **Open the content file:**
   ```
   content/home.md
   ```

2. **Edit the content** using any text editor (VS Code, Sublime, Notepad, etc.)

3. **Save the file**

4. **Refresh your browser** - changes appear immediately!

## File Structure

```
pct-map-website/
├── index.html              # Home page (loads content from markdown)
├── map.html                # Interactive map page
├── photography.html        # Photo slideshow page
├── content/
│   ├── home.md            # HOME PAGE CONTENT (edit this!)
│   └── README.md          # Markdown syntax guide
└── CONTENT_GUIDE.md       # This file
```

## What You Can Edit

### In `content/home.md`:

✅ **Text content** - All paragraphs, descriptions, titles
✅ **Section headings** - Add, remove, or rename sections
✅ **Links** - Update link text and destinations
✅ **Lists** - Bullet points, numbered lists
✅ **Formatting** - Bold, italic, emphasis
✅ **Structure** - Add or remove sections entirely

### What Stays the Same:

🔒 **Header navigation** - Managed in index.html
🔒 **Footer** - Managed in index.html
🔒 **Styling/colors** - Managed in index.html CSS
🔒 **Page layout** - Managed in index.html

## Markdown Syntax Quick Reference

### Headers
```markdown
# Main Title (largest)
## Section Title
### Subsection Title
```

### Text Formatting
```markdown
**Bold text**
*Italic text*
```

### Links
```markdown
[Link Text](url)

Example:
[View Map](map.html)
```

### Lists
```markdown
Bullet list:
- Item 1
- Item 2
- Item 3

Numbered list:
1. First item
2. Second item
3. Third item
```

### Horizontal Divider
```markdown
---
```

### Paragraphs
Just write text with blank lines between paragraphs.

## Example Edits

### Adding a New Section

```markdown
---

## New Section Title

This is the content for my new section. I can add **bold text** and *italic text*.

[Link to somewhere](url)
```

### Updating Trail Information

```markdown
## Trail Information

- **Total Distance:** 2,650 miles
- **Route:** Mexico → Canada
- **States:** California, Oregon, Washington
- **Duration:** 5 months
- **Start Date:** April 2025
```

### Changing Link Text

Before:
```markdown
[View Map](map.html)
```

After:
```markdown
[Explore the Interactive Map](map.html)
```

## Tips

1. **Preview changes** - Just refresh your browser after saving
2. **Keep backups** - Copy `home.md` before major changes
3. **Use blank lines** - Separate paragraphs with blank lines
4. **Test links** - Make sure all links work after editing
5. **Keep it simple** - Markdown is meant to be readable as plain text

## Troubleshooting

### Content not updating?
- Make sure you saved the file
- Hard refresh browser (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows)
- Check browser console for errors (F12)

### Formatting looks wrong?
- Check markdown syntax (see examples above)
- Make sure you have blank lines between sections
- Verify link syntax: `[text](url)`

### "Error loading content" message?
- Make sure `content/home.md` exists
- Check file permissions
- Verify you're running from a web server (not file://)

## Advanced: Adding More Markdown Pages

You can create additional markdown files for other pages:

1. Create new markdown file: `content/about.md`
2. Create new HTML page that loads it (copy index.html structure)
3. Update the JavaScript to load your new markdown file

## Need Help?

- See `content/README.md` for more markdown examples
- Check the markdown file directly to see current content
- The home page automatically renders whatever is in `content/home.md`

