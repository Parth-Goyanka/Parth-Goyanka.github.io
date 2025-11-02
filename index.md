---
layout: default
title: Home
---

<div class="hero">
  <div class="hero-content">
    <div class="icon floating">📚</div>
    <h1>{{ site.author.name }}</h1>
    <p class="subtitle">Theoretical Researcher</p>
    <p class="tagline">Exploring Control Systems & Power Systems Theory</p>
    <a href="#writings" class="cta-button">Read My Thoughts</a>
  </div>
</div>

<section class="section white-section">
  <h2>Research Interests</h2>
  <div class="research-grid">
    <div class="card">
      <div class="icon">🎛️</div>
      <h3>Control Theory</h3>
      <p>Deep diving into optimal control, robust control, Lyapunov stability, and nonlinear systems. Exploring the mathematical foundations that govern dynamic system behavior.</p>
    </div>
    <div class="card">
      <div class="icon">⚡</div>
      <h3>Power Systems Theory</h3>
      <p>Studying power flow analysis, stability theory, voltage control, and the mathematical modeling of electrical networks and grid dynamics.</p>
    </div>
    <div class="card">
      <div class="icon">🔬</div>
      <h3>Mathematical Foundations</h3>
      <p>Investigating optimization theory, differential equations, linear algebra, and functional analysis as applied to system dynamics and control.</p>
    </div>
  </div>
</section>

<section class="section gradient-section" id="writings">
  <h2>Recent Blog Posts</h2>
  <div class="blog-grid">
    {% for post in site.posts limit:3 %}
    <article class="blog-card">
      <div class="blog-meta">
        <span class="date">{{ post.date | date: "%B %d, %Y" }}</span>
        {% if post.tags %}
        <div class="tags">
          {% for tag in post.tags limit:2 %}
          <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
        {% endif %}
      </div>
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
      <a href="{{ post.url }}" class="read-more">Continue Reading →</a>
    </article>
    {% endfor %}
  </div>
  <div style="text-align: center; margin-top: 2rem;">
    <a href="/blog" class="cta-button">View All Posts</a>
  </div>
</section>

<section class="section white-section">
  <h2>Publications & Papers</h2>
  <div class="papers-list">
    {% for paper in site.papers %}
    <div class="paper-item">
      <div class="paper-content">
        <h3>{{ paper.title }}</h3>
        <p class="paper-authors">{{ paper.authors }}</p>
        <p class="paper-venue">{{ paper.venue }}, {{ paper.year }}</p>
        <p class="paper-description">{{ paper.description }}</p>
      </div>
      <div class="paper-links">
        {% if paper.pdf %}
        <a href="{{ paper.pdf }}" class="paper-link">📄 PDF</a>
        {% endif %}
        {% if paper.arxiv %}
        <a href="{{ paper.arxiv }}" class="paper-link">arXiv</a>
        {% endif %}
        {% if paper.doi %}
        <a href="{{ paper.doi }}" class="paper-link">DOI</a>
        {% endif %}
      </div>
    </div>
    {% endfor %}
  </div>
</section>

<section class="section gradient-section">
  <h2>Currently Reading</h2>
  <div class="reading-grid">
    <div class="book-card">
      <div class="book-icon">📖</div>
      <h3>Nonlinear Systems</h3>
      <p class="book-author">Hassan K. Khalil</p>
      <p class="book-note">Exploring Lyapunov stability theory and its applications to nonlinear control design.</p>
    </div>
    <div class="book-card">
      <div class="book-icon">📖</div>
      <h3>Power System Stability and Control</h3>
      <p class="book-author">Prabha Kundur</p>
      <p class="book-note">Deep dive into voltage stability, frequency control, and transient dynamics in power systems.</p>
    </div>
    <div class="book-card">
      <div class="book-icon">📖</div>
      <h3>Optimal Control Theory</h3>
      <p class="book-author">Donald E. Kirk</p>
      <p class="book-note">Studying calculus of variations, Pontryagin's principle, and dynamic programming.</p>
    </div>
  </div>
  <div style="text-align: center; margin-top: 2rem;">
    <a href="/reading" class="cta-button">Full Reading List</a>
  </div>
</section>

<section class="section white-section">
  <h2>About Me</h2>
  <div class="about-content">
    <div>
      <div class="about-text">
        <p>I'm an undergraduate researcher with a passion for theoretical exploration at the intersection of control systems and power systems. My work focuses on understanding the mathematical foundations and theoretical principles that govern complex dynamic systems.</p>
        <br>
        <p>I believe in the power of deep reading and careful thinking. Through my blog, I share insights, summaries, and reflections on papers, books, and concepts I encounter in my research journey.</p>
      </div>
    </div>
    <div>
      <h3 class="skills-title">Research Areas</h3>
      <div class="skills">
        <span class="skill-tag">Stability Theory</span>
        <span class="skill-tag">Optimal Control</span>
        <span class="skill-tag">Nonlinear Systems</span>
        <span class="skill-tag">Power Flow Analysis</span>
        <span class="skill-tag">Optimization</span>
        <span class="skill-tag">Mathematical Modeling</span>
        <span class="skill-tag">System Dynamics</span>
        <span class="skill-tag">Control Theory</span>
      </div>
    </div>
  </div>
</section>

<section class="section contact-section">
  <h2>Let's Connect</h2>
  <p class="contact-intro">Interested in discussing research ideas or theoretical concepts?</p>
  <div class="contact-links">
    <a href="mailto:{{ site.author.email }}" class="contact-link">
      <span>📧</span>
      <span>Email</span>
    </a>
    <a href="https://github.com/{{ site.author.github }}" class="contact-link" target="_blank">
      <span>💻</span>
      <span>GitHub</span>
    </a>
    <a href="https://linkedin.com/in/{{ site.author.linkedin }}" class="contact-link" target="_blank">
      <span>💼</span>
      <span>LinkedIn</span>
    </a>
    <a href="https://scholar.google.com/citations?user={{ site.author.scholar }}" class="contact-link" target="_blank">
      <span>📚</span>
      <span>Google Scholar</span>
    </a>
  </div>
</section>
