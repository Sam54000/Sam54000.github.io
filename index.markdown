---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: terminal
title: Home
---

<div class="command-block">
    <span class="prompt">guest@samuel.louviot.site</span>:<span class="path">~</span>$ <span class="command">whoami</span>
</div>
<div class="command-output">
Samuel Louviot
Scientific Software Engineer | Neural Engineer
</div>

<div class="command-block">
    <span class="prompt">guest@samuel.louviot.site</span>:<span class="path">~</span>$ <span class="command">cat about.txt</span>
</div>
<div class="command-output">
I'm a Scientific Software Engineer specializing in Neural Engineering. I build tools and applications that bridge the gap between neuroscience and technology.
</div>

<div class="command-block">
    <span class="prompt">guest@samuel.louviot.site</span>:<span class="path">~</span>$ <span class="command">ls projects/</span>
</div>
<div class="command-output">
{% for project in site.data.projects limit:3 %}
<div class="project-item">
    <span class="project-name"><a href="{{ project.url }}">{{ project.name }}</a></span>
    <span class="project-desc">- {{ project.description }}</span>
</div>
{% endfor %}
</div>

<div class="command-block">
    <span class="prompt">guest@samuel.louviot.site</span>:<span class="path">~</span>$ <span class="command">ls posts/</span>
</div>
<div class="command-output">
{% for post in site.posts limit:5 %}
<div class="post-item">
    <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
    <span class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></span>
</div>
{% endfor %}
</div>

<div class="command-block">
    <span class="prompt">guest@samuel.louviot.site</span>:<span class="path">~</span>$ <span class="command">cat contact.txt</span>
</div>
<div class="command-output">
Email: samuel.louviot@pm.me
GitHub: <a href="https://github.com/Sam54000">Sam54000</a>
LinkedIn: <a href="https://www.linkedin.com/in/samuel-louviot">samuel-louviot</a>
</div>

<style>
.project-item, .post-item {
    margin-bottom: 0.5rem;
}

.post-date {
    color: var(--gray);
    margin-right: 1rem;
}

.project-name, .post-title {
    color: var(--blue);
}
