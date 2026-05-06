# Zhibo Xuan — academic homepage exports

Two static HTML versions of the academic homepage, ready for GitHub Pages.

- `variant-a/index.html` — Classic single-column (Jon Barron-style)
- `variant-b/index.html` — Sticky sidebar (two-column)

## What's inside each file

A single self-contained HTML file:
- All CSS is inlined in `<style>` (no build step, no framework).
- One small `<script>` at the bottom toggles "show earlier publications".
- Fonts pulled from Google Fonts via `<link>`.
- Static markup — every news item, publication, etc. is a real `<div>` you can edit by hand or in Claude Desktop.

## To deploy to GitHub Pages

Easiest setup: pick **one** variant as your homepage.

1. Create a new repo named `<your-username>.github.io` on GitHub.
2. Copy the contents of either `variant-a/` or `variant-b/` into the repo root.
3. Commit + push.
4. GitHub Pages serves it automatically at `https://<your-username>.github.io`.

If you want both online for comparison, you can put one at the root and the other at `/b/`, like:

```
<repo>/
  index.html               <- variant-a
  b/
    index.html             <- variant-b
```

Then `https://<your-username>.github.io/b/` shows variant B.

## To replace the portrait

Drop `me.jpg` (or `me.png`, `me.webp`) next to `index.html` and uncomment the `<img src="me.jpg" ...>` line inside the `.portrait` div. The `portrait` placeholder text just sits in the empty div until you do.

## To change the accent color

Edit the `--accent` value at the top of the `<style>` block in each `index.html`. The CCF badge background, link colors, and section accents all read from this one variable.

## To edit content with Claude Desktop / hand

Everything is plain HTML. Open `index.html` and find the section you want to edit:

- Bio: inside `<section class="bio">` (variant A) or under `<h1>` in `<section id="about">` (variant B).
- News: inside `<ul class="dl">` under the News heading — each `<li>` is one item.
- Publications: each `<article class="pub">` is one paper. Edit title, authors, venue, badge `CCF-A`/`CCF-B`, links inline.
- Awards / Service / Education / Experience: same pattern, edit the visible text.

The "show earlier" button works as long as the script at the bottom stays. The button's text and count is hardcoded in the script — if you change the publication count, also update the `var n = …` number.
