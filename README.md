# Springhouse Project — Static Site

Off-grid build log for solar power, greenhouse construction, rural infrastructure, and practical resilience.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Main page — hero, article, sidebar, build log cards |
| `style.css` | All styles — linked from index.html |
| `.nojekyll` | Tells GitHub Pages to skip Jekyll processing |
| `README.md` | This file |

---

## Publishing to GitHub Pages

### First-time setup

1. Create a new repository on GitHub. Name it anything — `springhouse`, `springhouse-site`, etc.
   - Set it to **Public** (required for free GitHub Pages hosting).
   - Do **not** initialize it with a README (you already have one here).

2. Open a terminal in the `springhouse-github-pages-site/` folder on your machine.

3. Initialize the repo and push:

```bash
git init
git add .
git commit -m "Initial Springhouse static site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/REPO-NAME.git
git push -u origin main
```

4. In GitHub, go to the repository **Settings → Pages**.

5. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`

6. Click **Save**. GitHub will build and publish the site within a minute or two.

7. Your site URL will be:
   ```
   https://YOUR-USERNAME.github.io/REPO-NAME/
   ```
   It appears at the top of the Pages settings after the first build.

---

### Using a custom domain (optional)

If you have a domain pointed at GitHub Pages:

1. Add a file named `CNAME` to the repo root containing just your domain:
   ```
   springhouse.yourdomain.com
   ```
2. In your domain registrar's DNS settings, add a CNAME record pointing to `YOUR-USERNAME.github.io`.
3. In GitHub Pages settings, enter the custom domain. Check "Enforce HTTPS" once the DNS propagates.

---

## Adding Future Build Log Entries

The current `index.html` has three placeholder log cards in the `.sh-log-entries` section. To add a real post:

**Option A — Add cards directly to index.html (simple)**

Find the `<div class="sh-log-entries">` section and copy the card pattern:

```html
<article class="sh-log-card">
  <div class="sh-log-date">Month DD, YYYY</div>
  <h3 class="sh-log-title">Post Title Here</h3>
  <p class="sh-log-excerpt">Short summary of what happened in the field.</p>
  <a href="posts/your-post-slug.html" class="sh-log-more">Read more →</a>
</article>
```

**Option B — Create individual post pages (cleaner for longer entries)**

1. Create a `posts/` folder inside the site directory.
2. Create `posts/your-post-slug.html` using the same `<head>` and stylesheet link as `index.html`.
3. Write the post content using the `.sh-panel` and `.sh-lede` classes for consistent styling.
4. Link back to the homepage with `<a href="../index.html">← Back to Build Log</a>`.
5. Update the card in `index.html` to link to the new post file.

---

## Local Preview

No build step needed. Open the file directly in any browser:

- Double-click `index.html` in your file manager, or
- Run a simple local server from the site folder:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080` in your browser.

---

## Acceptance Checklist

Before pushing live, verify:

- [ ] No mention of the old project host anywhere on the page
- [ ] No advanced automation pitch in the public copy
- [ ] Tagline reads exactly: *Springhouse is a real-world off-grid build log for solar power, greenhouse construction, rural infrastructure, and practical resilience.*
- [ ] Dark grey/dark green text panels — not white
- [ ] Page reads correctly on mobile
- [ ] No JavaScript errors in browser console
- [ ] `style.css` loads and applies correctly
- [ ] `.nojekyll` file is present in the repo root
