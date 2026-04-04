# hutton.philosophy.utah.edu — WCAG 2.1 AA Remediation

Accessibility remediation for Prof. Eric L. Hutton's faculty page at the University of Utah.  
Work performed by **DevMoms** (devmoms.com) — April 2026.

---

## Files

| File | Description |
|------|-------------|
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
12. Added `lang="zh-TW"` on Chinese-language text
13. Fixed unquoted `href` attribute values
14. Restored plain `mailto:` email link (replaced broken Cloudflare obfuscation script)

---

## How to Use These Files

1. Download the file you want to update (`index.html` or `Advice.html`)
2. Open it in a plain text editor (TextEdit on Mac — set to plain text mode)
3. Make your content changes (see coaching comments inside the file)
4. Save the file
5. Upload it to the university server, replacing the existing version

### Adding a new publication (index.html)

Find the `<h3>Articles, Books, Essays, and Translations</h3>` section and add a new `<li>` at the **top** of the list:

```html
<li>
  <a href="URL_TO_ARTICLE"><em>Article Title</em></a>
  in <em>Journal Name</em> vol:issue (year), p. X&ndash;Y.
</li>
```

If the article has no URL yet, omit the `<a href>` tag and write the citation as plain text inside the `<li>`.

### Adding a book cover image

When adding an image (e.g., a book cover), always include an `alt` attribute:

```html
<img src="bookcover.jpg" width="100" height="150" alt="Cover of [Book Title] by [Author]">
```

Never leave `alt` empty for an informative image. Never omit `alt` entirely.

---

## WCAG Rules Referenced

| Rule | Name | Level |
|------|------|-------|
| 1.1.1 | Non-text Content (alt text) | A |
| 1.3.1 | Info and Relationships (semantic HTML) | A |
| 1.4.1 | Use of Color (links not color-only) | A |
| 1.4.3 | Contrast (Minimum) | AA |
| 1.4.4 | Resize Text (viewport/mobile) | AA |
| 1.4.10 | Reflow (responsive layout) | AA |
| 2.4.1 | Bypass Blocks (skip link) | A |
| 2.4.4 | Link Purpose (descriptive link text) | A |
| 2.4.7 | Focus Visible (keyboard focus styles) | AA |
| 3.1.1 | Language of Page (lang attribute) | A |
| 3.1.2 | Language of Parts (lang on non-English text) | AA |

---

## Contact

Questions about these files?  
Del Guerra — [devmoms.com](https://devmoms.com) — info@devmoms.com
