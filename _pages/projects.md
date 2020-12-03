---
layout: page
title: projects
permalink: /projects/
nav: true
---

<div class="projects">
  {% assign sorted_projects = site.projects | sort: "importance" %}
  {% for project in sorted_projects %}
  <div class="project">
    <div class="project-header">
      <h2 class="project-title">
        {% if project.redirect %}
        <a href="{{ project.redirect }}" target="_blank">{{ project.title }}</a>
        {% elsif project.nolink %}
        <span class="nolink">{{ project.title }}</span>
        {% else %}
        <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
        {% endif %}
      </h2>
      <h3 class="project-date">{{ project.timespan }}</h3>
    </div>
    <div class="project-body">
      <img src="{{ project.img | relative_url }}" alt="{{ project.img_alt }}" width="{{ project.img_width }}" height="{{ project.img_height }}" class="project-image">
      <div class="project-text">{{ project.content | markdownify }}</div>
    </div>
  </div>
{% endfor %}

</div>
