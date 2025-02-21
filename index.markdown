---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: terminal
title: Home
---

<div class="tui-section">
    <div class="tui-section-header">
        >_ Profile
    </div>
    <div class="tui-section-content">
        <strong>Samuel Louviot</strong>
        <br>
        Scientific Software Engineer | Neural Engineer
        <br><br>
        I'm a Scientific Software Engineer specializing in Neural Engineering. I build tools and applications that bridge the gap between neuroscience and technology.
    </div>
</div>

<div class="tui-section">
    <div class="tui-section-header">
        >_ Latest Projects
    </div>
    <div class="tui-section-content">
        {% for project in site.data.projects limit:3 %}
        <div class="project-item">
            <span class="project-name"><a href="{{ project.url }}">{{ project.name }}</a></span>
            <span class="project-desc">- {{ project.description }}</span>
        </div>
        {% endfor %}
    </div>
</div>

<div class="tui-section">
    <div class="tui-section-header">
        >_ Recent Posts
    </div>
    <div class="tui-section-content">
        {% for post in site.posts limit:5 %}
        <div class="post-item">
            <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
            <span class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></span>
        </div>
        {% endfor %}
    </div>
</div>

<div class="tui-section">
    <div class="tui-section-header">
        >_ Contact Information
    </div>
    <div class="tui-section-content">
        <div class="contact-item">Email: <a href="mailto:samuel.louviot@pm.me">samuel.louviot@pm.me</a></div>
        <div class="contact-item">GitHub: <a href="https://github.com/Sam54000">Sam54000</a></div>
        <div class="contact-item">LinkedIn: <a href="https://www.linkedin.com/in/samuel-louviot">samuel-louviot</a></div>
    </div>
</div>

<style>
.project-item, .post-item, .contact-item {
    margin-bottom: 0.5rem;
}

.post-date {
    color: var(--gray);
    margin-right: 1rem;
}

.project-name, .post-title {
    color: var(--dark-green);
}

.project-desc {
    color: var(--fg);
}

.contact-item a {
    color: var(--dark-green);
}
</style>
