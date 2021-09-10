---
layout: page
title: Projects
description: >
  A showcase of our projects
hide_description: true
permalink: /projects/
---


{% assign categories = site["featured_categories"] %}
{% for item in categories %}
<h2>[{{ item.title }}]({{ item.url | relative_url }})</h2>
{{ item.description }} {:.note title="Description"}
<a href="{{ item.url | relative_url }}">
<img src="{{ item.image_url | relative_url }}" alt="{{ item.slug }}" loading="lazy" width="1000px" style="border-radius:25px" class="photos_img">
</a>
{% endfor %}
