---
title: Contact
kicker: Request Workshop
description: Request an AI leadership workshop or advisory session focused on practical adoption for engineering managers.
permalink: /contact/
---
{% assign contact = site.data.profile.contact %}
{% assign form_endpoint = contact.form_endpoint | default: '' | strip %}
{% assign email = contact.email | default: site.email | strip %}

## Request an AI Leadership Workshop

If you are an engineering manager or technical leader planning AI adoption, use this page to start a workshop request.

<div class="contact-actions">
  {% if contact.issue_form_url %}
    <a class="button-link primary" href="{{ contact.issue_form_url }}" target="_blank" rel="noopener">Request Workshop (GitHub Form)</a>
  {% endif %}

  {% if email != '' %}
    <a class="button-link" href="mailto:{{ email }}">Email Mike</a>
  {% endif %}

  {% for link in site.data.profile.social_links %}
    <a class="button-link" href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>
  {% endfor %}
</div>

{% if contact.issue_form_url %}
<p class="form-note">The GitHub workshop request form is the default contact path from this site.</p>
{% endif %}

## Workshop Intake (What to Include)

- Team size and current leadership structure
- AI adoption stage (exploring, piloting, scaling)
- Main constraint (quality, speed, governance, change management)
- Desired outcomes over the next 90 days

## Direct Form Submission

{% if form_endpoint != '' %}
<form class="contact-form" action="{{ form_endpoint }}" method="POST">
  <label for="name">Name</label>
  <input id="name" name="name" type="text" required>

  <label for="email">Email</label>
  <input id="email" name="email" type="email" required>

  <label for="organization">Organization</label>
  <input id="organization" name="organization" type="text" required>

  <label for="team_size">Engineering team size</label>
  <input id="team_size" name="team_size" type="text" placeholder="e.g., 12 engineers across 2 teams" required>

  <label for="adoption_stage">AI adoption stage</label>
  <select id="adoption_stage" name="adoption_stage" required>
    <option value="">Select a stage</option>
    <option>Exploring use cases</option>
    <option>Running pilots</option>
    <option>Scaling adoption</option>
    <option>Reworking current approach</option>
  </select>

  <label for="main_constraint">Main constraint</label>
  <select id="main_constraint" name="main_constraint" required>
    <option value="">Select a constraint</option>
    <option>Quality and reliability risk</option>
    <option>Delivery speed and prioritization</option>
    <option>Manager capability and team enablement</option>
    <option>Governance and responsible AI practices</option>
    <option>Cross-functional alignment</option>
  </select>

  <label for="message">Workshop goals and context</label>
  <textarea id="message" name="message" rows="6" required></textarea>

  <label for="timeline">Desired timeline</label>
  <input id="timeline" name="timeline" type="text" placeholder="e.g., Start within 4 weeks">

  <input type="hidden" name="_subject" value="New workshop request from Mike Dabydeen site">
  <input class="visually-hidden" type="text" name="_gotcha" tabindex="-1" autocomplete="off">

  <button class="button-link primary" type="submit">Send Request</button>
</form>
<p class="form-note">This form submits to the configured external endpoint.</p>
{% else %}
<p>An external form endpoint is not configured yet. Set <code>contact.form_endpoint</code> in <code>_data/profile.yml</code> to enable on-site form submission.</p>
<p>Use the workshop request button above in the meantime.</p>
{% endif %}

## Collaboration Topics

- AI leadership workshops for engineering managers
- Manager enablement and coaching systems
- Engineering operating playbooks for AI-era delivery
- Speaking and teaching collaborations on practical AI adoption
