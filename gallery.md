---
layout: page
title: Gallery
permalink: /gallery/
description: "A collection of pictures from our projects"
---

<section id="photos">
{% for image in site.static_files %}
{% if image.path contains '/gallery' %}
<a href="{{  image.path }}">
<img src="{{ image.path }}" alt="{{ image.name | capitalize }}" loading="lazy">
</a>
{% endif %}
{% endfor %}
</section>