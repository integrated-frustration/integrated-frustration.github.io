---
layout: page
title: Projects
description: >
  Here you should be able to find everything you need to know to accomplish the most common tasks when blogging with Hydejack.
hide_description: true
sitemap: false
permalink: /projects/
---


{% assign categories = site["featured_categories"] %}
{% for item in categories %}
  <h2>[{{ item.title }}]({{ item.url | relative_url }})</h2>
  {{ item.description }} {:.note title="Description"}
  ![{{ item.slug }}]({{ item.image_url | relative_url }}){: width="1000px" loading="lazy" style="border-radius:25px"}
{% endfor %}
