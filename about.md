---
layout: page
hide_description: true
permalink: /about/
redirect_from:
  - /download/
---

# About
{% for author in site.data.authors %}
{% unless forloop.first%}
<h2 align="center"> {{ author.name }} </h2>
<p align="center">
![{{ author.name }}]({{ author.picture.path | relative_url }}){: align="center" width="250px" loading="lazy" style="border-radius:50%"}
</p>


{{ author.about }}

{% unless forloop.last %}
-------- 
{% endunless %}
{% endunless %}
{% endfor %}

<h2 align="center"> Thanks for coming! </h2>