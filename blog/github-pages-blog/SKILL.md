---
name: github-pages-blog
description: Publishes a new blog post to 0xcdef's GitHub Pages site (0xcdef/0xcdef.github.io) by reading the blog/_template.html from the repo, writing a properly styled HTML post, pushing it to blog/, and updating index.markdown. Use this skill whenever the user says "write a blog post", "create a post", "publish a post", "add a blog", "push a blog", "new post for my site", or asks to document, write up, or share something on their GitHub Pages site. Also activate when the user describes a topic and says things like "make this a blog post" or "turn this into a post". Always reads the live template from GitHub before writing — never guess the style from memory.
---

# GitHub Pages Blog Skill

Publishes styled blog posts to `0xcdef/0xcdef.github.io` by reading the live template, writing the HTML, pushing it, and updating the index.

---

## Workflow

1. **Read the template** — fetch `blog/_template.html` from GitHub before writing anything
2. **Read `index.markdown`** — to understand the existing post-item structure
3. **Write the post** — fill the template with content, following all rules below
4. **Show the user a preview** — present the file for review before pushing
5. **Push on approval** — push `blog/<slug>.html` and updated `index.markdown` in one commit

---

## CSS Rules (read carefully — these prevent recurring bugs)

### Dark sidebar card: `code` override (REQUIRED)

The global `code` style uses a light parchment background (`var(--bg2)`) and terracotta text (`var(--accent)`). Inside `.sidebar-card.dark`, this creates a jarring light chip on a dark surface.

**Always add this rule to the `<style>` block of every post:**

```css
/* ── code inside dark sidebar card ── */
.sidebar-card.dark code {
  background: rgba(255,255,255,.08);
  color: #A8E6CF;
}
```

**Never** use inline `style="color:..."` on `<code>` tags inside dark sidebar cards — it only fixes the text colour and leaves the background broken.

### Dark sidebar card: general rules

- `p` text: `color: rgba(247,245,240,.7)`
- `h4` label: `color: rgba(247,245,240,.4)`
- Do NOT apply article-level styles (bg2, accent) inside `.sidebar-card.dark` — they break the contrast

---

## File Download on GitHub Pages (REQUIRED when posts include downloadable files)

GitHub Pages does **not** send `Content-Disposition: attachment` headers for any file type. This means:

- `<a href="..." download>` only works for same-origin files **and** only when the server cooperates — GitHub Pages does not cooperate
- `.md`, `.txt`, and most text files will open in the browser instead of downloading
- Binary files like `.zip` may download but cannot be reliably named

**The correct pattern for all downloadable files:**

Use a `<button>` with a JS fetch-to-blob handler that pulls the file from `raw.githubusercontent.com` (which has open CORS) and triggers a real browser save:

```html
<!-- In the <style> block -->
.dl-btn {
  display: inline-flex; align-items: center; gap: 10px;
  background: var(--ink); color: #F7F5F0; text-decoration: none;
  padding: 12px 22px; border-radius: 8px; font-family: var(--mono);
  font-size: 13px; font-weight: 600; letter-spacing: .04em;
  border: none; cursor: pointer; transition: opacity .15s;
}
.dl-btn:hover { opacity: .78; }

<!-- In the <body> -->
<button class="dl-btn" onclick="downloadFile()">&#x2193; &nbsp;Download SKILL.md</button>

<!-- Before </body> -->
<script>
async function downloadFile() {
  const rawUrl = 'https://raw.githubusercontent.com/0xcdef/0xcdef.github.io/main/PATH/TO/FILE.md';
  try {
    const res = await fetch(rawUrl);
    const text = await res.text();
    const blob = new Blob([text], { type: 'text/plain' });
    const a = document.createElement('a');
    a.href = URL.createObjectURL(blob);
    a.download = 'FILENAME.md';
    a.click();
    URL.revokeObjectURL(a.href);
  } catch (e) {
    window.open(rawUrl, '_blank'); // fallback: open raw in new tab
  }
}
</script>
```

Key points:
- Always fetch from `raw.githubusercontent.com/0xcdef/0xcdef.github.io/main/...` — not from the GitHub Pages URL
- The `Blob` type should be `'text/plain'` for `.md` / `.txt` files
- Always include the fallback `window.open` in the catch block
- The `download` attribute on the dynamically created `<a>` sets the saved filename

---

## Post Structure

Follow the template exactly. Key components:

| Component | Notes |
|-----------|-------|
| Masthead | `logo · section · home-link · badge` |
| Hero | Dark, full-width. `eyebrow · h1 (with optional `<em>`) · hero-sub · hero-meta` |
| Article | `h2` sections, `h3` subsections, `.pull` quotes, `.cmd` code blocks, `.card-grid`, `.data-table` |
| Sidebar | Sticky. Numbered `.step-row` checklist + dark callout card. Hidden on mobile. |
| Footer | `<strong>0xcdef</strong> · AI & Agents for ASIC/SoC Design` |

## index.markdown Post-Item Pattern

```html
<div class="post-item">
  <div class="post-item-meta">
    <span class="post-item-tag">Category</span>
    <span class="post-date">Mar 24, 2026</span>
  </div>
  <a class="post-item-title" href="/blog/your-post.html">Post title here&nbsp;.</a>
  <p class="post-item-desc">One sentence description — specific and punchy.</p>
  <a class="post-item-link" href="/blog/your-post.html">Read the post &rarr;</a>
</div>
```

Always insert new posts **at the top** of the post list, above existing entries.

---

## Known Gotchas

- **`code` in dark sidebar** → always add the `.sidebar-card.dark code` override (see CSS Rules above)
- **File downloads** → always use the fetch-to-blob JS pattern (see File Download section above)
- **`layout: home`** → don't use it; use `layout: default` to avoid silent Jekyll fallback to README
- **Stale Gemfile.lock** → delete after any theme or plugin change; GitHub Pages regenerates it
- **Mobile sidebar overlap** → use `display: none` at the mobile breakpoint, never `order: -1`
- **Inline style on dark card code** → never do `<code style="color:...">` inside `.sidebar-card.dark`; use the CSS class override instead
