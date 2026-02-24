---
title: AI Leadership
kicker: Executive + Practical
description: AI transformation resources for engineering managers who need measurable outcomes, strong governance, and durable team adoption.
permalink: /ai-leadership/
---
{% assign ai_posts = site.posts | where_exp: 'post', "post.tags contains 'ai-leadership'" %}
{% assign workshop = site.data.profile.offers.workshop %}

## AI Leadership for Engineering Managers

This page centralizes the practical playbooks, workshop outcomes, and implementation guidance used to help engineering teams move from AI experimentation to repeatable execution.

## Who This Is For

- Engineering managers responsible for delivery outcomes and technical quality.
- Technical leaders aligning AI adoption across multiple teams.
- Organizations that want to modernize execution without adding operational risk.

## Primary Offer: {{ workshop.name | default: 'AI Leadership Workshop for Engineering Managers' }}

- <strong>Audience:</strong> {{ workshop.audience | default: 'Engineering managers and technical leaders guiding AI adoption' }}
- <strong>Format:</strong> {{ workshop.format | default: '90-minute working session (virtual or onsite)' }}

### Workshop Outcomes

<ul class="simple-list">
  {% if workshop and workshop.outcomes and workshop.outcomes.size > 0 %}
    {% for outcome in workshop.outcomes %}
      <li>{{ outcome }}</li>
    {% endfor %}
  {% else %}
    <li>Identify the highest-value AI workflow opportunities for the next 90 days.</li>
    <li>Define quality, reliability, and responsible AI guardrails for delivery teams.</li>
    <li>Build a manager enablement plan with clear milestones and ownership.</li>
  {% endif %}
</ul>

<div class="contact-actions">
  <a class="button-link primary" href="{{ '/contact/' | relative_url }}">Request Workshop</a>
  <a class="button-link" href="{{ '/about/' | relative_url }}">About Mike</a>
</div>

## Core Playbook Themes

1. AI adoption strategy tied to business and delivery goals.
2. Manager enablement systems for coaching and execution.
3. Governance and decision quality for reliable AI integration.

## AI Leadership Articles

{% if ai_posts and ai_posts.size > 0 %}
<div class="card-grid">
  {% for post in ai_posts limit:4 %}
    <article class="card">
      <p class="meta">{{ post.date | date: '%B %-d, %Y' }}</p>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.summary }}</p>
    </article>
  {% endfor %}
</div>
{% else %}
<p>AI-focused articles are being added. Review the broader <a href="{{ '/blog/' | relative_url }}">blog</a> for leadership and execution playbooks in the meantime.</p>
{% endif %}
