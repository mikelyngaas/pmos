# Adding Product Dev OS to your personal site

Use this when you copy the showcase into your site repo (e.g. `mikelyngaas.github.io`).

---

## 1. Add the Product Dev OS page

- Copy `showcase/pmos.html` into your site repo.
- Put it in the **same place as your other pages** (e.g. next to `index.html` and `risk.html`), so the URL is:
  - **`https://mikelyngaas.github.io/pmos.html`**

If your site uses a build step (e.g. Jekyll), add `pmos.html` so it’s included in the build output at the root (or adjust the path in the snippet below).

---

## 2. Update the Side projects section on the homepage

**Replace** the “More coming soon” / “Another build in the works” block with the Product Dev OS entry.

### If your homepage is HTML

Find this (or the equivalent in your markup):

```html
More coming soon

Another build in the works.
```

Replace it with:

```html
<a href="https://mikelyngaas.github.io/pmos.html">Product Dev OS</a>

A modular artifact system that turns Cursor or Claude into a product development partner. Structured briefs, PRDs, and more — with AI-simulated stakeholder reviews.
```

(Adjust the link if you put `pmos.html` in a subfolder, e.g. `href="/pmos.html"` or `href="/projects/pmos.html"`.)

### If your homepage is Markdown (e.g. Jekyll)

Find:

```text
More coming soon

Another build in the works.
```

Replace with:

```markdown
[Product Dev OS](https://mikelyngaas.github.io/pmos.html)

A modular artifact system that turns Cursor or Claude into a product development partner. Structured briefs, PRDs, and more — with AI-simulated stakeholder reviews.
```

---

## 3. Edit the copy on the Product Dev OS page

Open `pmos.html` and replace the placeholder sections:

- **Why I built this** — One or two short paragraphs in your voice.
- **What you get** — The four bullet points; use your own value props (or fewer/more).

Search for `[Replace with` to find every placeholder. The repo link is already set to `https://github.com/mikelyngaas/product-dev-os`; change it if your repo URL is different.

---

## 4. Back link

The “← Back” link on the Product Dev OS page points to `https://mikelyngaas.github.io/`. If your site’s root URL is different, update it in `pmos.html`.
