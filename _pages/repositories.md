---
layout: page
permalink: /repositories/
title: repositories
description: Open-source projects and code on GitHub.
nav: true
nav_order: 4
---

{% for user in site.data.repositories.github_users %}

<p><a href="https://github.com/{{ user }}" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> github.com/{{ user }}</a></p>
{% endfor %}

<div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1rem;">
  {% for item in site.data.repositories.github_repos %}
  <a href="https://github.com/{{ item.repo }}" target="_blank" rel="noopener" style="display: block; padding: 1rem; border: 1px solid currentColor; border-radius: 0.5rem; text-decoration: none; color: inherit;">
    <strong><i class="fa-regular fa-folder"></i> {{ item.repo | split: '/' | last }}</strong>
    {% if item.description %}<p style="margin: 0.5rem 0 0;">{{ item.description }}</p>{% endif %}
    {% if item.language %}<small style="opacity: 0.7;">{{ item.language }}</small>{% endif %}
  </a>
  {% endfor %}
</div>
