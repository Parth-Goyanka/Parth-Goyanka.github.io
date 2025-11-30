---
layout: default
title: Home
---

<header class="hero">
  <div class="hero-grid-bg"></div>
  <div class="hero-content">
    <div class="hero-badge">
      <i class="fas fa-atom"></i> Theoretical Research
    </div>
    <h1>Exploring the <span class="gradient-text">Mathematical Foundations</span> of Complex Systems</h1>
    <p class="subtitle">Researching at the intersection of Control Theory, Power Systems, and Differential Geometry.</p>
    <div class="hero-actions">
      <a href="#research" class="primary-btn">Explore Research</a>
      <a href="#writings" class="secondary-btn">Read Blog</a>
    </div>
  </div>
  <div class="hero-visual">
    <div class="abstract-shape"></div>
    <div class="math-overlay">
      <span>$\dot{x} = f(x, u)$</span>
      <span>$\nabla_X Y$</span>
    </div>
  </div>
</header>

<section class="section" id="research">
  <div class="section-header">
    <h2>Research Interests</h2>
    <p>Uncovering the fundamental principles governing dynamic systems.</p>
  </div>
  <div class="research-grid">
    <div class="card glass-card">
      <div class="card-icon"><i class="fas fa-wave-square"></i></div>
      <h3>Control Theory</h3>
      <p>Deep diving into optimal control, robust control, Lyapunov stability, and nonlinear systems. Exploring the mathematical foundations that govern dynamic system behavior.</p>
    </div>
    <div class="card glass-card">
      <div class="card-icon"><i class="fas fa-bolt"></i></div>
      <h3>Power Systems Theory</h3>
      <p>Studying power flow analysis, stability theory, voltage control, and the mathematical modeling of electrical networks and grid dynamics.</p>
    </div>
    <div class="card glass-card">
      <div class="card-icon"><i class="fas fa-project-diagram"></i></div>
      <h3>Differential Geometry</h3>
      <p>Applying geometric methods to control theory, studying manifolds, curvature, and their implications for system stability and optimization.</p>
    </div>
  </div>
</section>

<section class="section alt-bg" id="writings">
  <div class="section-header">
    <h2>Recent Thoughts</h2>
    <p>Reflections on papers, books, and theoretical concepts.</p>
  </div>
  <div class="blog-grid">
    {% for post in site.posts limit:3 %}
    <article class="blog-card glass-card">
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
      <p>{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
      <a href="{{ post.url }}" class="read-more">Read Article <i class="fas fa-arrow-right"></i></a>
    </article>
    {% endfor %}
  </div>
  <div class="center-btn">
    <a href="/blog" class="secondary-btn">View All Posts</a>
  </div>
</section>

<section class="section">
  <div class="section-header">
    <h2>Publications</h2>
    <p>Selected works and contributions.</p>
  </div>
  <div class="papers-list">
    {% for paper in site.papers %}
    <div class="paper-item glass-card">
      <div class="paper-content">
        <h3>{{ paper.title }}</h3>
        <p class="paper-authors">{{ paper.authors }}</p>
        <div class="paper-meta-row">
            <span class="paper-venue"><i class="fas fa-landmark"></i> {{ paper.venue }}, {{ paper.year }}</span>
        </div>
        <p class="paper-description">{{ paper.description }}</p>
      </div>
      <div class="paper-links">
        {% if paper.pdf %}
        <a href="{{ paper.pdf }}" class="icon-link" title="PDF"><i class="far fa-file-pdf"></i></a>
        {% endif %}
        {% if paper.arxiv %}
        <a href="{{ paper.arxiv }}" class="icon-link" title="arXiv"><i class="fas fa-archive"></i></a>
        {% endif %}
        {% if paper.doi %}
        <a href="{{ paper.doi }}" class="icon-link" title="DOI"><i class="fas fa-link"></i></a>
        {% endif %}
      </div>
    </div>
    {% endfor %}
  </div>
</section>

<section class="section alt-bg">
  <div class="section-header">
    <h2>Currently Reading</h2>
    <p>Books on my desk.</p>
  </div>
  <div class="reading-grid">
    <div class="book-card glass-card">
      <div class="book-icon"><i class="fas fa-book"></i></div>
      <h3>Nonlinear Systems</h3>
      <p class="book-author">Hassan K. Khalil</p>
      <p class="book-note">Exploring Lyapunov stability theory and its applications to nonlinear control design.</p>
    </div>
    <div class="book-card glass-card">
      <div class="book-icon"><i class="fas fa-book"></i></div>
      <h3>Power System Stability and Control</h3>
      <p class="book-author">Prabha Kundur</p>
      <p class="book-note">Deep dive into voltage stability, frequency control, and transient dynamics in power systems.</p>
    </div>
    <div class="book-card glass-card">
      <div class="book-icon"><i class="fas fa-book"></i></div>
      <h3>Optimal Control Theory</h3>
      <p class="book-author">Donald E. Kirk</p>
      <p class="book-note">Studying calculus of variations, Pontryagin's principle, and dynamic programming.</p>
    </div>
  </div>
  <div class="center-btn">
    <a href="/reading" class="secondary-btn">Full Reading List</a>
  </div>
</section>

<section class="section contact-section" id="contact">
  <div class="contact-container glass-card">
    <h2>Let's Connect</h2>
    <p class="contact-intro">Interested in discussing research ideas or theoretical concepts?</p>
    <div class="contact-links">
      <a href="mailto:{{ site.author.email }}" class="contact-link">
        <i class="fas fa-envelope"></i>
        <span>Email</span>
      </a>
      <a href="https://github.com/{{ site.author.github }}" class="contact-link" target="_blank">
        <i class="fab fa-github"></i>
        <span>GitHub</span>
      </a>
      <a href="https://linkedin.com/in/{{ site.author.linkedin }}" class="contact-link" target="_blank">
        <i class="fab fa-linkedin"></i>
        <span>LinkedIn</span>
      </a>
      <a href="https://scholar.google.com/citations?user={{ site.author.scholar }}" class="contact-link" target="_blank">
        <i class="fas fa-graduation-cap"></i>
        <span>Google Scholar</span>
      </a>
    </div>
  </div>
</section>
