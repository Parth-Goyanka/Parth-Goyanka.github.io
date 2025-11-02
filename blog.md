---
layout: page
title: Blog
permalink: /blog/
---

<div class="blog-header">
  <h1>Research Blog</h1>
  <p>Thoughts, learnings, and explorations in control systems and power systems theory</p>
</div>

<div class="blog-list">
  {% for post in paginator.posts %}
  <article class="blog-post-preview">
    <div class="post-meta">
      <span class="date">{{ post.date | date: "%B %d, %Y" }}</span>
      {% if post.tags %}
      <div class="tags">
        {% for tag in post.tags %}
        <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </div>
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p>{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
    <a href="{{ post.url }}" class="read-more">Read More →</a>
  </article>
  {% endfor %}
</div>

{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}" class="pagination-link">← Newer Posts</a>
  {% endif %}
  
  <span class="pagination-info">Page {{ paginator.page }} of {{ paginator.total_pages }}</span>
  
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="pagination-link">Older Posts →</a>
  {% endif %}
</div>
{% endif %}
