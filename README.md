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
17. Restored complete publications list (2000–2025), including all articles, both book entries with accessible cover images, and all reviews
18. Fixed decorative dot borders around profile photo using CSS `position: absolute` containers (see below)

---

### About the profile photo dot borders (change #18)

The original page used four small GIF images (`sub_top_right.gif`, `sub_left.gif`, `sub_right.gif`) placed inline with `<br>` tags to create a decorative dot border around the professor's photo. This relied on the old layout table to hold them in position. After the table was removed in the WCAG remediation, the GIFs stacked vertically and no longer framed the photo correctly.

**Fix (by Larry Guerra, April 2026):** A `.photo-frame` container `<div>` with `position: relative` was added around the photo. Each dot GIF was given the class `dots` (`position: absolute`) and a position class (`top-right`, `left`, `right`, `bottom-right`) so they sit precisely at the edges of the photo regardless of screen size.

```html
<div class="profile-photo">
  <div class="photo-frame">
    <img class="hutton-pic" src="HuttonPicture.jpg" alt="Professor Eric L. Hutton">

    <img class="dots top-right" src="sub_top_right.gif" alt="">
    <img class="dots left" src="sub_left.gif" alt="">
    <img class="dots right" src="sub_right.gif" alt="">
    <img class="dots bottom-right" src="sub_top_right.gif" alt="">
  </div>
</div>
```

**If you need to replace the photo:** swap `HuttonPicture.jpg` with your new filename and update the `alt` text to describe the new image. The dot borders will continue to frame the new photo automatically.

---

## How to Use These Files

1. Download the file you want to update (`index.html` or `Advice.html`)
2. Open it in a plain text editor (TextEdit on Mac — set to plain text mode)
3. Make your content changes (see coaching comments inside the file)
4. Save the file
5. Upload it to the university server, replacing the existing version

### Adding a new publication (`index.html`)

Find the `<h3>Articles, Books, Essays, and Translations</h3>` section and add a new `<li>` at the **top** of the list:

```html
<li>
  <a href="https://doi.org/..."><em>Article Title Here</em></a>
  in <em>Journal Name</em> vol:issue (year), p. X&ndash;Y.
</li>
```

If no URL is available yet, omit the `<a>` tag and write plain text:

```html
<li>
  <em>Article Title Here</em>
  in <em>Journal Name</em> vol:issue (year), p. X&ndash;Y.
</li>
```

For a book entry with a cover image:

```html
<div class="book-entry">
  <img src="bookcover.jpg" width="105" height="160"
       alt="Cover of Book Title by Author Name">
  <div class="book-text">
    <em>Book Title</em>. Publisher, Year.
  </div>
</div>
```

### Adding a review (`index.html`)

Find the `<h3>Reviews</h3>` section and add a new `<li>` at the top:

```html
<li>
  Review of <em>Book Title</em>, by Author Name,
  in <em>Journal Name</em> vol:issue (year), p. X&ndash;Y.
</li>
```

### Adding an advice item (`Advice.html`)

Find the `<ol>` inside `<main>` and add a new `<li>` anywhere in the list:

```html
<li>
  <strong>Topic title:</strong> Your paragraph text here.
</li>
```

---

## WCAG Rules Applied

| WCAG Criterion | Level | What it requires |
| --- | --- | --- |
| 1.1.1 Non-text Content | A | All images have descriptive `alt` text |
| 1.3.1 Info and Relationships | A | Semantic HTML structure (headings, lists, landmarks) |
| 1.4.1 Use of Color | A | Links underlined — not identified by color alone |
| 1.4.3 Contrast (Minimum) | AA | Text contrast ratio ≥ 4.5:1 |
| 1.4.4 Resize Text | AA | Viewport meta tag; no fixed-size containers blocking zoom |
| 1.4.10 Reflow | AA | Responsive layout — no horizontal scroll at 320px width |
| 2.4.1 Bypass Blocks | A | Skip navigation link added |
| 2.4.4 Link Purpose | A | All links have descriptive text |
| 2.4.6 Headings and Labels | AA | Descriptive headings at every section |
| 2.4.7 Focus Visible | AA | Keyboard focus outline visible on all interactive elements |
| 3.1.1 Language of Page | A | `lang="en"` on `<html>`; `lang="zh-TW"` on Chinese passages |
