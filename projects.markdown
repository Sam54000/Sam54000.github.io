---
layout: page
title: Projects
permalink: /projects/
---

<div class="project-list">
  {% assign sorted_projects = site.projects | sort: 'date' | reverse %}
  {% for project in sorted_projects %}
    <div class="project-entry">
      <h2>
        <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
      </h2>
      <div class="project-meta">
        {% if project.date %}
          <span class="project-date">{{ project.date | date: "%B %-d, %Y" }}</span>
        {% endif %}
        {% if project.status %}
          <span class="project-status">Status: {{ project.status }}</span>
        {% endif %}
        {% if project.technologies %}
          <div class="project-tech">
            {% for tech in project.technologies %}
              <span class="tech-tag">{{ tech }}</span>
            {% endfor %}
          </div>
        {% endif %}
      </div>
      {% if project.description %}
        <p class="project-description">{{ project.description }}</p>
      {% endif %}
      {% if project.github %}
        <div class="project-links">
          <a href="{{ project.github }}" class="github-link">View on GitHub →</a>
        </div>
      {% endif %}
    </div>
  {% endfor %}
</div>

<style>
  .project-list {
    margin-top: 2rem;
  }

  .project-entry {
    margin-bottom: 2rem;
    padding: 1rem;
    border: 1px dashed var(--dark-green);
    background-color: var(--bg_h);
  }

  .project-entry h2 {
    margin-top: 0;
    margin-bottom: 0.5rem;
  }

  .project-entry h2 a {
    color: var(--green);
    text-decoration: none;
  }

  .project-entry h2 a:hover {
    color: var(--light-green);
    text-decoration: underline;
  }

  .project-meta {
    color: var(--gray);
    font-size: 0.9em;
    margin: 0.5rem 0;
  }

  .project-date {
    margin-right: 1rem;
  }

  .project-status {
    color: var(--orange);
  }

  .project-tech {
    margin: 0.5rem 0;
  }

  .tech-tag {
    display: inline-block;
    padding: 0.2rem 0.5rem;
    margin: 0.2rem;
    background-color: var(--bg3);
    color: var(--aqua);
    border-radius: 3px;
    font-size: 0.8em;
  }

  .project-description {
    color: var(--fg2);
    margin: 0.5rem 0;
    line-height: 1.6;
  }

  .project-links {
    margin-top: 1rem;
  }

  .github-link {
    color: var(--aqua);
    text-decoration: none;
  }

  .github-link:hover {
    color: var(--light-green);
    text-decoration: underline;
  }
</style>
