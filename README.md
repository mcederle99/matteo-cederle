# matteo-cederle

My personal website: plain HTML, CSS and JS with no build step. It's served by GitHub Pages.

```
index.html            all the content
assets/css/style.css  styles (colors are the variables at the top)
assets/js/main.js     theme toggle, mobile menu, scroll effects, BibTeX copy
assets/img/           profile.jpg + optional paper thumbnails in pubs/
assets/cv/            Cederle_CV.pdf
```

## Preview locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Updating content

Every list in `index.html` has a `<!-- copy this block -->` comment above its first entry. To add something, copy that block, paste it **at the top** of the list and edit it.

- **News:** copy an `<li>` in the `#news` section. When the visible list gets long (more than about 6 items), move the oldest items into the "Show older news" `<details>` below it.
- **Paper:** the 3 newest papers are always visible, and the rest sit under "Show older publications", grouped by year. To add one, copy an `<article class="pub">` block and paste it at the top of the first list. Then move the paper that is now 4th to the top of its year inside "Show older publications". For a new year, copy a whole `<div class="pub-group">`.
  - Wrap your own name in `<span class="me">…</span>` so it's highlighted.
  - Link pills (Paper, arXiv, Code) with an empty `href=""` are hidden automatically, so fill in only the ones you have.
  - For BibTeX, paste the entry inside `<pre><code>…</code></pre>`. The Copy button works on its own. Escape `&` as `&amp;` and `<` as `&lt;`.
  - When a preprint gets accepted, change its badge (for example `Preprint` → `ICML 2027` + `Conference`) and the venue line.
  - For a thumbnail, put an image in `assets/img/pubs/` and uncomment the `pub-thumb` div (see the first paper).
- **Project / experience:** copy an `<article class="project">` in `#projects`.
- **Teaching:** copy an `<li>` in `#teaching`.
- **CV:** replace `assets/cv/Cederle_CV.pdf`, keeping the same file name.
- **Photo:** replace `assets/img/profile.jpg` with a square image, at least 400×400. If it's missing, the initials are shown instead.

After editing, update "Last updated" in the footer.

## Changing colors

Edit the variables at the top of `assets/css/style.css`: the `[data-theme="dark"]` block and the `[data-theme="light"]` block. `--accent` is the main color (teal at night, petrol teal by day). The only gradients are the soft glow and dot grid behind the intro (`.hero::before` / `.hero::after`).
