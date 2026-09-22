---
layout: page
permalink: /repositories/
title: repositories
description: Research code for GPU-accelerated graph query processing.
nav: true
nav_order: 5
---

{% if site.data.repositories.github_users %}

<!--
## GitHub profile

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
</div>

---

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
{% if site.data.repositories.github_users.size > 1 %}

  <h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.liquid username=user %}
  </div>

---

{% endfor %}
{% endif %}
{% endif %}

{% if site.data.repositories.github_repos %} -->

## Research repositories

- **[Vora](https://github.com/gh8li/vora-artifact)** — a scalable single-GPU engine for subgraph query processing on large labeled graphs.
- **[GCSM-BU](https://github.com/gh8li/GCSM-BU)** — GPU-based continuous subgraph matching on batch updates.

[View all repositories on GitHub](https://github.com/gh8li?tab=repositories).

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
