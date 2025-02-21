---
layout: terminal
title: Home
---

<div class="tui-section">
    <div class="tui-section-content">
        <strong style="color: var(--green-dim); font-weight: 100; font-size: 1.8rem;">Dr. Samuel Louviot, PhD</strong>
        <br>
        Scientific Software Engineer | Neural Engineer
        <br><br>
        I'm a Scientific Software Engineer specializing in Neural Engineering. I build tools and applications that bridge the gap between neuroscience and technology.
    </div>
</div>

<div class="tui-section">
    <div class="tui-section-header">
        Latest Projects
    </div>
    <div class="tui-section-content">
        {% assign sorted_pages = site.pages | where_exp: "item", "item.path contains 'projects/'" | sort: "date" | reverse %}
        {% for project in sorted_pages limit:3 %}
        <div class="project-item">
            <span class="project-name"><a href="{{ project.url | relative_url }}">{{ project.title }}</a></span>
            {% if project.description %}
            <span class="project-desc">- {{ project.description }}</span>
            {% endif %}
            {% if project.date %}
            <div class="project-date">{{ project.date | date: "%Y-%m-%d" }}</div>
            {% endif %}
        </div>
        {% endfor %}
        <div class="view-all">
            <a href="/projects">View all projects →</a>
        </div>
    </div>
</div>

<div class="tui-section">
    <div class="tui-section-header">
        Recent Posts
    </div>
    <div class="tui-section-content">
        {% for post in site.posts limit:5 %}
        <div class="post-item">
            <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
            <span class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></span>
        </div>
        {% endfor %}
        <div class="view-all">
            <a href="/blog">View all posts →</a>
        </div>
    </div>
</div>

<div class="tui-section">
    <div class="tui-section-header">
        Contact Information
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

.post-date, .project-date {
    color: var(--gray);
    font-size: 0.9em;
    margin-top: 0.2rem;
}

.post-date {
    margin-right: 1rem;
}

.project-name, .post-title {
    color: var(--dark-green);
}

.project-desc {
    color: var(--fg);
}

.contact-item a {
    color: var(--orange-dim);
}

.view-all {
    margin-top: 1rem;
    text-align: right;
}

.view-all a {
    color: var(--aqua);
    text-decoration: none;
}

.view-all a:hover {
    color: var(--light-green);
    text-decoration: underline;
}
</style>
