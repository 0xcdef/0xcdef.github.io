---
layout: default
title: 0xcdef — AI & Agents for ASIC/SoC Design
---

<!-- Hero -->
<div class="hero">
  <div class="hero-eyebrow">0xcdef &middot; Research &amp; Engineering</div>
  <h1>AI &amp; Agents for<br><em>Modern ASIC/SoC Design</em></h1>
  <p class="hero-sub">
    Exploring how large language models and autonomous agents can transform
    the way we design, verify, and optimize application-specific integrated circuits &mdash;
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
    <p>Building AI agents that drive EDA tools autonomously &mdash; synthesis, place &amp; route, timing closure.</p>
  </div>
  <div class="focus-card">
    <span class="icon">⚡</span>
    <h3>LLM-Assisted RTL</h3>
    <p>Using large language models to generate, review, and refactor RTL code at scale.</p>
  </div>
  <div class="focus-card">
    <span class="icon">🔬</span>
    <h3>Verification Intelligence</h3>
    <p>Applying AI to functional verification &mdash; testbench generation, coverage closure, bug triage.</p>
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
  <p>Introducing skill-loop &mdash; a step-by-step guide built on the Skills 2.0 methodology, covering creation, eval testing, A/B benchmarking, and trigger optimization.</p>
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
