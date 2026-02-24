---
title: Teaching Resources
kicker: Learning by Building
description: Course notes, books, and practical resources for classes Mike teaches now, has taught, and plans to teach.
permalink: /teaching/
---
{% assign current_courses = site.teaching | where: 'status', 'current' %}
{% assign past_courses = site.teaching | where: 'status', 'past' %}
{% assign planned_courses = site.teaching | where: 'status', 'planned' %}

<section>
  <h2>Current</h2>
  <div class="card-grid">
    {% for course in current_courses %}
      <article class="card">
        <p class="meta">{{ course.course_code }}</p>
        <h3><a href="{{ course.url | relative_url }}">{{ course.title }}</a></h3>
        <p>{{ course.summary }}</p>
      </article>
    {% endfor %}
  </div>
</section>

<section>
  <h2>Past</h2>
  <div class="card-grid">
    {% for course in past_courses %}
      <article class="card">
        <p class="meta">{{ course.course_code }}</p>
        <h3><a href="{{ course.url | relative_url }}">{{ course.title }}</a></h3>
        <p>{{ course.summary }}</p>
      </article>
    {% endfor %}
  </div>
</section>

<section>
  <h2>Planned</h2>
  <div class="card-grid">
    {% for course in planned_courses %}
      <article class="card">
        <p class="meta">{{ course.course_code }}</p>
        <h3><a href="{{ course.url | relative_url }}">{{ course.title }}</a></h3>
        <p>{{ course.summary }}</p>
      </article>
    {% endfor %}
  </div>
</section>
