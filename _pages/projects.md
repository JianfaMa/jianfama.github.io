---
layout: page
title: Projects
permalink: /projects/
description: Selected work in embodied AI, autonomous driving, aerial robotics, and continuous control.
nav: true
nav_order: 3
---

<p class="projects-intro">
  Selected research and engineering projects spanning perception, reasoning, planning, and control. Each case study highlights the problem, my contribution, the technical stack, and the result.
</p>

<div class="projects">
  {% assign sorted_projects = site.projects | sort: 'importance' %}
  <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
</div>
