---
layout: default
title: 0xcdef — AI & Agents for ASIC/SoC Design
---

<style>
  :root {
    --bg:        #0f1117;
    --bg-card:   #181c27;
    --bg-hover:  #1e2333;
    --border:    #2a2f42;
    --border-hi: #3d4460;
    --text:      #e8e6e0;
    --text-dim:  #9095a8;
    --text-faint:#565b70;
    --accent:    #e8a642;
    --accent-lo: rgba(232,166,66,0.12);
    --accent-br: rgba(232,166,66,0.28);
    --link:      #e8a642;
    --tag-bg:    rgba(232,166,66,0.08);
    --tag-br:    rgba(232,166,66,0.25);
  }

  /* ── Page base override ── */
  body { background: var(--bg) !important; color: var(--text) !important; }
  a { color: var(--link); }
  a:hover { color: #f5c070; text-decoration: underline; }

  /* ── Hero ── */
  .hero {
    padding: 52px 0 44px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 52px;
  }
  .hero-eyebrow {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: .16em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
  }
  .hero h1 {
    font-size: 2.3rem;
    font-weight: 700;
    line-height: 1.18;
    margin-bottom: 18px;
    color: #ffffff;
    letter-spacing: -.01em;
  }
  .hero h1 em {
    font-style: italic;
    color: var(--accent);
  }
  .hero-sub {
    font-size: 1.05rem;
    color: var(--text-dim);
    max-width: 580px;
    line-height: 1.75;
    margin-bottom: 30px;
  }
  .focus-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .tag {
    font-size: 10.5px;
    font-weight: 700;
    letter-spacing: .1em;
    text-transform: uppercase;
    padding: 4px 13px;
    border-radius: 20px;
    background: var(--tag-bg);
    border: 1px solid var(--tag-br);
    color: var(--accent);
  }

  /* ── Section heading ── */
  .section-heading {
    font-size: 10.5px;
    font-weight: 700;
    letter-spacing: .16em;
    text-transform: uppercase;
    color: var(--text-faint);
    margin-bottom: 20px;
    margin-top: 52px;
  }

  /* ── Focus cards ── */
  .focus-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(210px, 1fr));
    gap: 14px;
    margin-bottom: 52px;
  }
  .focus-card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 22px 24px;
    transition: border-color 0.15s;
  }
  .focus-card:hover { border-color: var(--border-hi); }
  .focus-card .icon {
    font-size: 1.5rem;
    margin-bottom: 12px;
    display: block;
  }
  .focus-card h3 {
    font-size: 0.92rem;
    font-weight: 700;
    color: #ffffff;
    margin-bottom: 7px;
    letter-spacing: -.01em;
  }
  .focus-card p {
    font-size: 0.84rem;
    color: var(--text-dim);
    line-height: 1.6;
    margin: 0;
  }

  /* ── Featured post ── */
  .featured-post {
    background: var(--accent-lo);
    border: 1px solid var(--accent-br);
    border-radius: 10px;
    padding: 28px 32px;
    margin-bottom: 16px;
    display: block;
    text-decoration: none !important;
    color: inherit;
    transition: background 0.15s, border-color 0.15s;
  }
  .featured-post:hover {
    background: rgba(232,166,66,0.17);
    border-color: rgba(232,166,66,0.45);
    text-decoration: none !important;
  }
  .featured-label {
    font-size: 10.5px;
    font-weight: 700;
    letter-spacing: .14em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 10px;
  }
  .featured-post h2 {
    font-size: 1.3rem;
    font-weight: 700;
    margin: 0 0 10px;
    color: #ffffff;
    line-height: 1.3;
    letter-spacing: -.01em;
  }
  .featured-post p {
    color: var(--text-dim);
    font-size: 0.91rem;
    line-height: 1.65;
    margin: 0 0 14px;
  }
  .read-link {
    font-size: 13px;
    font-weight: 600;
    color: var(--accent);
  }

  /* ── Post list ── */
  .post-list {
    list-style: none;
    padding: 0;
    margin: 0 0 52px;
  }
  .post-list li {
    padding: 13px 0;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: baseline;
    gap: 12px;
  }
  .post-list li:last-child { border-bottom: none; }
  .post-list li a {
    font-size: 0.96rem;
    font-weight: 600;
    color: var(--text);
  }
  .post-list li a:hover { color: var(--accent); text-decoration: none; }
  .post-date {
    font-size: 11px;
    color: var(--text-faint);
    white-space: nowrap;
    flex-shrink: 0;
  }

  /* ── About strip ── */
  .about-strip {
    border-top: 1px solid var(--border);
    padding-top: 28px;
    margin-top: 8px;
    font-size: 0.87rem;
    color: var(--text-faint);
    line-height: 1.75;
  }
  .about-strip strong { color: var(--text); }
  .about-strip a { color: var(--text-dim); }
  .about-strip a:hover { color: var(--accent); }

  @media (max-width: 600px) {
    .hero h1 { font-size: 1.75rem; }
    .focus-grid { grid-template-columns: 1fr 1fr; }
    .featured-post { padding: 22px 20px; }
  }
  @media (max-width: 400px) {
    .focus-grid { grid-template-columns: 1fr; }
  }
</style>

<!-- Hero -->
<div class="hero">
  <div class="hero-eyebrow">0xcdef &middot; Research &amp; Engineering</div>
  <h1>AI &amp; Agents for<br><em>Modern ASIC/SoC Design</em></h1>
  <p class="hero-sub">
    Exploring how large language models and autonomous agents can transform
    the way we design, verify, and optimize application-specific integrated circuits —
    from RTL generation to physical implementation.
  </p>
  <div class="focus-tags">
    <span class="tag">LLM for EDA</span>
    <span class="tag">AI Agents</span>
    <span class="tag">RTL Design</span>
    <span class="tag">SoC Architecture</span>
    <span class="tag">Chip Verification</span>
    <span class="tag">Physical Design</span>
  </div>
</div>

<!-- Focus Areas -->
<div class="section-heading">Focus Areas</div>
<div class="focus-grid">
  <div class="focus-card">
    <span class="icon">🤖</span>
    <h3>Agentic EDA Workflows</h3>
    <p>Building AI agents that drive EDA tools autonomously — synthesis, place &amp; route, timing closure.</p>
  </div>
  <div class="focus-card">
    <span class="icon">⚡</span>
    <h3>LLM-Assisted RTL</h3>
    <p>Using large language models to generate, review, and refactor RTL code at scale.</p>
  </div>
  <div class="focus-card">
    <span class="icon">🔬</span>
    <h3>Verification Intelligence</h3>
    <p>Applying AI to functional verification — testbench generation, coverage closure, bug triage.</p>
  </div>
  <div class="focus-card">
    <span class="icon">🏗️</span>
    <h3>SoC Architecture</h3>
    <p>Exploring AI-guided architecture exploration and design space optimization for complex SoCs.</p>
  </div>
</div>

<!-- Featured Post -->
<div class="section-heading">Featured Post</div>
<a class="featured-post" href="/blog/skill-loop.html">
  <div class="featured-label">Methodology &middot; March 2026</div>
  <h2>Stop hoping your Claude skills work. Prove it.</h2>
  <p>Introducing skill-loop — a step-by-step guide built on the Skills 2.0 methodology, covering creation, eval testing, A/B benchmarking, and trigger optimization.</p>
  <span class="read-link">Read the post &rarr;</span>
</a>

<!-- All Posts -->
<div class="section-heading">All Posts</div>
<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
    </li>
  {% endfor %}
  <li>
    <a href="/blog/skill-loop.html">Stop hoping your Claude skills work. Prove it.</a>
    <span class="post-date">Mar 21, 2026</span>
  </li>
</ul>

<!-- About -->
<div class="about-strip">
  <strong>0xcdef</strong> &mdash;
  Engineer at the intersection of AI/LLM agents and modern ASIC/SoC chip design.
  Writing about EDA automation, RTL intelligence, and the future of hardware development.
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/0xcdef">GitHub</a>
  &nbsp;&middot;&nbsp;
  <a href="https://twitter.com/curliph">Twitter</a>
</div>
