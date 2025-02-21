---
layout: page
title: Projects
permalink: /projects/
---

# My Projects

COMING SOON!

{% for project in site.pages %}
  {% if project.path contains 'projects/' %}
    <div class="project-entry">
      <h2><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
      {% if project.description %}
        <p>{{ project.description }}</p>
      {% endif %}
    </div>
  {% endif %}
{% endfor %}
