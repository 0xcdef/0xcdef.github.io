---
layout: default
title: 0xcdef
---

<style>
.home-hero {
  padding: 32px 0 24px;
  border-bottom: 1px solid rgba(255,255,255,0.1);
  margin-bottom: 36px;
}
.home-hero h1 {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 8px;
}
.home-hero p {
  font-size: 1.05rem;
  opacity: 0.8;
  max-width: 560px;
}
.featured-post {
  background: rgba(255,255,255,0.07);
  border: 1px solid rgba(255,255,255,0.15);
  border-radius: 10px;
  padding: 28px 32px;
  margin-bottom: 40px;
  display: block;
  text-decoration: none;
  color: inherit;
}
.featured-post:hover { background: rgba(255,255,255,0.11); text-decoration: none; }
.featured-label {
  font-size: 11px;
  font-weight: 700;
  letter-spacing: .12em;
  text-transform: uppercase;
  color: #acd5f2;
  margin-bottom: 10px;
}
.featured-post h2 {
  font-size: 1.5rem;
  font-weight: 700;
  margin: 0 0 10px;
  color: #fff;
  line-height: 1.25;
}
.featured-post p {
  opacity: 0.7;
  font-size: 0.95rem;
  line-height: 1.6;
  margin: 0 0 10px;
}
.featured-meta {
  font-size: 12px;
  opacity: 0.4;
}
.read-link {
  display: inline-block;
  margin-top: 10px;
  font-size: 13px;
  font-weight: 600;
  color: #acd5f2;
}
.section-heading {
  font-size: 11px;
  font-weight: 700;
  letter-spacing: .12em;
  text-transform: uppercase;
  opacity: 0.45;
  margin-bottom: 16px;
  margin-top: 40px;
}
.post-list {
  list-style: none;
  padding: 0;
  margin: 0;
}
.post-list li {
  padding: 14px 0;
  border-bottom: 1px solid rgba(255,255,255,0.08);
}
.post-list li a {
  font-size: 1rem;
  font-weight: 600;
  color: #acd5f2;
}
.post-list li .post-date {
  font-size: 12px;
  opacity: 0.4;
  margin-left: 10px;
}
</style>

<div class="home-hero">
  <h1>👋 Hello, World!</h1>
  <p>Welcome to <strong>0xcdef's</strong> corner of the internet — writing about AI, Claude skills, and developer tooling.</p>
</div>

<div class="section-heading">Featured Post</div>

<a class="featured-post" href="/blog/skill-loop.html">
  <div class="featured-label">Methodology &middot; March 2026</div>
  <h2>Stop hoping your Claude skills work. Prove it.</h2>
  <p>Introducing skill-loop — a step-by-step guide built on the Skills 2.0 methodology, covering creation, eval testing, A/B benchmarking, and trigger optimization.</p>
  <div class="featured-meta">7 min read</div>
  <span class="read-link">Read the post &rarr;</span>
</a>

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
