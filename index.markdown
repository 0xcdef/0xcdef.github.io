---
layout: default
title: 0xcdef — AI & Agents for ASIC/SoC Design
---

<style>
  /* ── Hero ── */
  .hero {
    padding: 48px 0 40px;
    border-bottom: 1px solid rgba(255,255,255,0.1);
    margin-bottom: 48px;
  }
  .hero-eyebrow {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: .14em;
    text-transform: uppercase;
    color: #acd5f2;
    margin-bottom: 14px;
  }
  .hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 16px;
    color: #fff;
  }
  .hero h1 em {
    font-style: italic;
    color: #acd5f2;
  }
  .hero-sub {
    font-size: 1.05rem;
    opacity: 0.7;
    max-width: 600px;
    line-height: 1.7;
    margin-bottom: 28px;
  }
  .focus-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .tag {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: .1em;
    text-transform: uppercase;
    padding: 4px 12px;
    border-radius: 20px;
    border: 1px solid rgba(172,213,242,0.35);
    color: #acd5f2;
  }

  /* ── Focus areas ── */
  .section-heading {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: .14em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.4);
    margin-bottom: 20px;
    margin-top: 48px;
  }
  .focus-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 16px;
    margin-bottom: 48px;
  }
  .focus-card {
    background: rgba(255,255,255,0.05);
    border: 1px solid rgba(255,255,255,0.1);
    border-radius: 10px;
    padding: 22px 24px;
  }
  .focus-card .icon {
    font-size: 1.6rem;
    margin-bottom: 10px;
  }
  .focus-card h3 {
    font-size: 0.95rem;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
  }
  .focus-card p {
    font-size: 0.85rem;
    opacity: 0.6;
    line-height: 1.55;
    margin: 0;
  }

  /* ── Featured post ── */
  .featured-post {
    background: rgba(172,213,242,0.07);
    border: 1px solid rgba(172,213,242,0.2);
    border-radius: 10px;
    padding: 28px 32px;
    margin-bottom: 16px;
    display: block;
    text-decoration: none;
    color: inherit;
    transition: background 0.15s;
  }
  .featured-post:hover { background: rgba(172,213,242,0.12); text-decoration: none; }
  .featured-label {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: .12em;
    text-transform: uppercase;
    color: #acd5f2;
    margin-bottom: 10px;
  }
  .featured-post h2 {
    font-size: 1.35rem;
    font-weight: 700;
    margin: 0 0 10px;
    color: #fff;
    line-height: 1.3;
  }
  .featured-post p {
    opacity: 0.65;
    font-size: 0.92rem;
    line-height: 1.6;
    margin: 0 0 12px;
  }
  .read-link {
    font-size: 13px;
    font-weight: 600;
    color: #acd5f2;
  }

  /* ── Post list ── */
  .post-list {
    list-style: none;
    padding: 0;
    margin: 0 0 48px;
  }
  .post-list li {
    padding: 13px 0;
    border-bottom: 1px solid rgba(255,255,255,0.07);
    display: flex;
    align-items: baseline;
    gap: 12px;
  }
  .post-list li a {
    font-size: 0.97rem;
    font-weight: 600;
    color: #acd5f2;
  }
  .post-list li a:hover { text-decoration: underline; }
  .post-date {
    font-size: 11px;
    opacity: 0.38;
    white-space: nowrap;
  }

  /* ── About strip ── */
  .about-strip {
    border-top: 1px solid rgba(255,255,255,0.1);
    padding-top: 32px;
    margin-top: 8px;
    font-size: 0.88rem;
    opacity: 0.5;
    line-height: 1.7;
  }
  .about-strip a { color: #acd5f2; }

  @media (max-width: 600px) {
    .hero h1 { font-size: 1.7rem; }
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
    <div class="icon">🤖</div>
    <h3>Agentic EDA Workflows</h3>
    <p>Building AI agents that drive EDA tools autonomously — synthesis, place &amp; route, timing closure.</p>
  </div>
  <div class="focus-card">
    <div class="icon">⚡</div>
    <h3>LLM-Assisted RTL</h3>
    <p>Using large language models to generate, review, and refactor RTL code at scale.</p>
  </div>
  <div class="focus-card">
    <div class="icon">🔬</div>
    <h3>Verification Intelligence</h3>
    <p>Applying AI to functional verification — testbench generation, coverage closure, bug triage.</p>
  </div>
  <div class="focus-card">
    <div class="icon">🏗️</div>
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
  <strong style="opacity:1;color:#fff">0xcdef</strong> &mdash;
  Engineer focused on the intersection of AI/LLM agents and modern ASIC/SoC chip design.
  Writing about EDA automation, RTL intelligence, and the future of hardware development.
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/0xcdef">GitHub</a>
  &nbsp;&middot;&nbsp;
  <a href="https://twitter.com/curliph">Twitter</a>
</div>
