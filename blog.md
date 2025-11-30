---
layout: page
title: Blog
permalink: /blog/
---

<div class="section-header">
  <h2>Research Blog</h2>
  <p>Thoughts, learnings, and explorations in control systems and power systems theory.</p>
</div>

<div class="blog-grid">
  {% for post in site.posts %}
  <article class="blog-card glass-card">
    <div class="blog-meta">
      <span class="date">{{ post.date | date: "%B %d, %Y" }}</span>
      {% if post.tags %}
      <div class="tags">
        {% for tag in post.tags %}
        <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </div>
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    <a href="{{ post.url }}" class="read-more">Read Article <i class="fas fa-arrow-right"></i></a>
  </article>
  {% endfor %}
</div>
