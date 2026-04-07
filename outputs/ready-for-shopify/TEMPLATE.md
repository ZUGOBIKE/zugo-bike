# Shopify Blog Post — Publishing Template

## How to use these files

Each `.html` file in `blog/` is ready to paste directly into Shopify.

### Steps to publish:

1. Go to **Shopify Admin → Online Store → Blog Posts → Add blog post**
2. Enter the **title** (shown at the top of each file as a comment)
3. In the content editor, click **"Show HTML"** (the `<>` button)
4. **Paste the entire HTML** from the file
5. Click **"Show HTML"** again to return to visual mode and verify formatting
6. Fill in the **SEO fields** below the editor:
   - **Page title:** use the `<title>` from the file comment
   - **Meta description:** use the meta description from the file comment
   - **URL handle:** use the filename (e.g. `how-to-choose-an-electric-bike`)
7. Add a **featured image**
8. Set **author** to ZUGO Bike
9. Set **blog** to the appropriate blog (e.g. "News" or "Guides")
10. Click **Save** → **Publish**

### Formatting rules:

- No external CSS or Tailwind — all styling comes from Shopify's theme
- Tables use simple HTML with no inline styles beyond basic borders
- FAQ sections use `<details>` tags which render as expandable accordions
- CTAs use a simple styled `<a>` tag that inherits theme button colors
- All links to zugobike.com use relative paths where possible

### File naming:

```
outputs/ready-for-shopify/blog/
  how-to-choose-an-electric-bike.html
  fat-tire-vs-regular-ebike.html
  are-electric-bikes-worth-it.html
```
