---
layout: page
title: Gallery
permalink: /gallery/
description: "A collection of pictures from our projects"
---

<section class="photos">
{% for image in site.static_files %}
{% if image.path contains '/gallery' %}
<a href="{{  image.path }}">
<img src="{{ image.path }}" alt="{{ image.name | capitalize }}" loading="lazy" class="photos_img">
</a>
{% endif %}
{% endfor %}
</section>