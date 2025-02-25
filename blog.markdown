---
layout: page
title: Blog
permalink: /blog/
---

<div class="post-list">
  {% for post in site.posts %}
    <article class="post-entry">
      <h2>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      <div class="post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%B %-d, %Y" }}
        </time>
      </div>
      {% if post.description %}
        <p>{{ post.description }}</p>
      {% else %}
        <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
      {% endif %}
    </article>
  {% endfor %}
</div>
