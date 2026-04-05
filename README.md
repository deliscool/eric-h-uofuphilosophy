# hutton.philosophy.utah.edu — WCAG 2.1 AA Remediation

Accessibility remediation for Prof. Eric L. Hutton's faculty page at the University of Utah.  
Work performed by **DevMoms** (devmoms.com) — April 2026.

---

## Files

| File | Description |
| --- | --- |
| `index.html` | Main faculty homepage |
| `Advice.html` | Advice for PhD students in Chinese Thought |

---

## What Changed

Both files were updated to meet **WCAG 2.1 Level AA** — the standard mandated for University of Utah web pages as of April 2026.

Every change is documented with an HTML comment inside the file. Open either file in a text editor to read coaching notes explaining what was changed and why.

### Summary of changes across both files

1. Added `<!DOCTYPE html>` — modern HTML declaration
2. Added `lang="en"` — screen readers use this for correct pronunciation
3. Added `viewport` meta tag — mobile readability
4. Replaced layout `<table>` with semantic `<div>` and CSS
5. Added heading hierarchy (`<h1>`, `<h2>`, `<h3>`) — screen reader navigation
6. Added descriptive `alt` text to all images
7. Added skip navigation link — keyboard users bypass repeated header links
8. Added landmark elements: `<header>`, `<nav>`, `<main>`, `<footer>`, `<section>`
9. Replaced deprecated `<font>`, `<center>`, `<b>`, `<i>` with CSS and semantic equivalents
10. Fixed invalid list structure — content was placed outside `<li>` tags
11. Replaced vague "here" link text with descriptive text
12. Added `lang="zh-TW"` on Chinese-language text inline (replacing invalid nested `<html>` tag)
13. Fixed unquoted `href` attribute values
14. Restored plain `mailto:` email link (replaced broken Cloudflare obfuscation script)
15. Added responsive mobile layout — columns stack vertically on small screens (1.4.10 Reflow)
16. Added keyboard focus styles — visible outline on all interactive elements (2.4.7 Focus Visible)
17. Restored complete publications list (2000-2025), including all articles, both book entries with accessible cover images, and all reviews

---

## How to Use These Files

1. Download the file you want to update (`index.html` or `Advice.html`)
2. Open it in a plain text editor (TextEdit on Mac — set to plain text mode)
3. Make your content changes (see coaching comments inside the file)
4. Save the file
5. Upload it to the university server, replacing the existing version

### Adding a new publication (index.html)

Find the `<h3>Articles, Books, Essays, and Translations</h3>` section and add a new `<li>` at the **top** of the list:
