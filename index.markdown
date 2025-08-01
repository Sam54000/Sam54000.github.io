---
layout: terminal
title: Home
---
<div class="tui-section">
    <div class="tui-section-content">
        <strong class="main-title">Dr. Samuel Louviot, PhD</strong>
        <span class="subtitle">Neuroscientist</span>
            <p>I am a neuroscientist who has experience and skills in a vast 
            spectrum of engineering domains. I like building tools and 
            applications to solve technical and scientific challenges
            in neuroscience.</p>
    </div>
</div>

<div class="tui-section">
    <div class="tui-section-header">
        Latest Projects
    </div>
    <div class="tui-section-content">
        {% assign sorted_projects = site.projects | sort: 'date' | reverse %}
        {% for project in sorted_projects limit:3 %}
        <div class="project-item">
            <span class="project-name"><a href="{{ project.url | relative_url }}">{{ project.title }}</a></span>
            {% if project.description %}
            <span class="project-desc"> - {{ project.description }}</span>
            {% endif %}
            {% if project.status %}
            <div class="project-meta">
                <span class="project-status">Status: {{ project.status }}</span>
                {% if project.date %}
                <span class="project-date">{{ project.date | date: "%B %-d, %Y" }}</span>
                {% endif %}
            </div>
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

<style>
.project-item, .post-item {
    margin-bottom: 1rem;
    padding: 0.5rem;
    background-color: transparent;
}

.post-date, .project-date {
    color: var(--gray);
    font-size: 0.9em;
}

.project-meta {
    margin-top: 0.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.project-status {
    color: var(--orange);
}

.post-date {
    margin-right: 1rem;
}

.project-name, .post-title {
    color: var(--green);
}

.project-name a {
    color: var(--green);
    text-decoration: none;
}

.project-name a:hover {
    color: var(--light-green);
    text-decoration: underline;
}

.project-desc {
    color: var(--fg2);
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

.main-title {
    color: var(--green);
    font-weight: 400;
    font-size: 2.4rem;
    font-family: 'Sometype Mono', monospace;
    display: block;
    margin-bottom: 0rem;
}

.subtitle {
    color: var(--fg);
    font-family: 'Sometype Mono', monospace;
    display: block;
    color: var(--gray);
    font-weight: 400;
    font-size: 1.4rem;
    margin-bottom: 1rem;

}
</style>
