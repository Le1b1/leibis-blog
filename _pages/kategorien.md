---
title: Kategorien
date: 2017-01-24T11:47:42+00:00
layout: page
permalink: /kategorien/
order: 1
---

<ul>
  {% for tag in site.tags %}
  {% assign t = tag | first %}
    <li><a href="/{{ site.tag_page_dir }}/{{ t | slugify: 'pretty' }}/">{{ t }}</a></li>
  {% endfor %}
</ul>