---
layout: splash
title: "Problems Archive"
permalink: /problems/
---

## Problems Archive

<ul>
{% for post in site.posts %}
  {% if post.categories contains "Problems" %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endif %}
{% endfor %}
</ul>
