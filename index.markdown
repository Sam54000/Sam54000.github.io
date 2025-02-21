---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: terminal
title: Home
---

# Welcome to my place

```bash
> whoami
Samuel Louviot
Scientific Software Engineer | Neural Engineer
```

## Latest Projects
{% for project in site.data.projects limit:3 %}
- [{{ project.name }}]({{ project.url }}) - {{ project.description }}
{% endfor %}

## Recent Posts
{% for post in site.posts limit:5 %}
- <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span> [{{ post.title }}]({{ post.url }})
{% endfor %}

```bash
> cat contact.txt
Email: samuel.louviot@pm.me
GitHub: Sam54000
LinkedIn: samuel.louviot
```
