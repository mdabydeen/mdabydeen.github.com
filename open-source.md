---
title: Open Source
kicker: Build in Public
description: Selected repositories and engineering artifacts with practical implementation value.
permalink: /open-source/
---
{% assign featured_projects = site.projects | where: 'featured', true %}
{% assign other_projects = site.projects | where_exp: 'item', 'item.featured != true' %}

<section>
  <h2>Featured</h2>
  <div class="card-grid">
    {% for project in featured_projects %}
      <article class="card">
        <p class="meta">{{ project.role }}</p>
        <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
        <p>{{ project.summary }}</p>
        {% if project.repo_url %}
          <a href="{{ project.repo_url }}" target="_blank" rel="noopener">Repository</a>
        {% endif %}
      </article>
    {% endfor %}
  </div>
</section>

<section>
  <h2>More Work</h2>
  <div class="card-grid">
    {% for project in other_projects %}
      <article class="card">
        <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
        <p>{{ project.summary }}</p>
      </article>
    {% endfor %}
  </div>
</section>

<section>
  <h2>GitHub Profile</h2>
  <p>For a complete repository list, visit <a href="https://github.com/mdabydeen" target="_blank" rel="noopener">github.com/mdabydeen</a>.</p>
</section>
