---
title: Blog
kicker: AI Leadership Playbooks
description: Practical notes for engineering managers on AI adoption, delivery systems, and leadership execution.
permalink: /blog/
---
{% assign ai_posts = site.posts | where_exp: 'post', "post.tags contains 'ai-leadership'" %}

<section>
  <h2>Editorial Pillars</h2>
  <div class="card-grid">
    <article class="card">
      <p class="meta">Pillar 1</p>
      <h3>AI Adoption Strategy</h3>
      <p>How engineering managers prioritize AI initiatives that support business and delivery outcomes.</p>
    </article>
    <article class="card">
      <p class="meta">Pillar 2</p>
      <h3>Manager Enablement</h3>
      <p>Playbooks to help managers coach teams, define guardrails, and scale practical AI habits.</p>
    </article>
    <article class="card">
      <p class="meta">Pillar 3</p>
      <h3>Governance and Decision Quality</h3>
      <p>Operational patterns that keep adoption responsible, measurable, and aligned with engineering standards.</p>
    </article>
  </div>
</section>

<section>
  <h2>Recent Posts</h2>
  <div class="card-grid">
    {% for post in site.posts %}
      <article class="card">
        <p class="meta">{{ post.date | date: '%B %-d, %Y' }}</p>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.summary }}</p>
        {% if post.tags and post.tags.size > 0 %}
          <div class="chip-row">
            {% for tag in post.tags %}
              <span class="chip">{{ tag }}</span>
            {% endfor %}
          </div>
        {% endif %}
      </article>
    {% endfor %}
  </div>
</section>

<section>
  <h2>AI Leadership Stream</h2>
  {% if ai_posts and ai_posts.size > 0 %}
    <div class="card-grid">
      {% for post in ai_posts %}
        <article class="card">
          <p class="meta">{{ post.date | date: '%B %-d, %Y' }}</p>
          <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
          <p>{{ post.summary }}</p>
        </article>
      {% endfor %}
    </div>
  {% else %}
    <p>AI leadership posts are in progress. Check back soon for new workshop-backed playbooks.</p>
  {% endif %}
</section>

<section>
  <h2>Tags</h2>
  <div class="chip-row">
    {% for tag in site.tags %}
      <span class="chip">{{ tag[0] }} ({{ tag[1] | size }})</span>
    {% endfor %}
  </div>
</section>
