---
layout: page
hide_description: true
permalink: /about/
redirect_from:
  - /download/
---

# About

Our vision is to share the __*frustration*__ that is inevitably __*integrated*__ into DIY projects.
{:.lead}
We want to contribute the knowledge and skills we gained by __making mistakes__, __troubleshooting__ our work and 
__refining__ our creative and cognitive processes.
We hope you find our experiences useful and we would love to [hear from you!][mail]
{:.about_text}

[mail]: mailto:integratedfrustration@gmail.com

<hr>

{% for author in site.data.authors %}
{% unless forloop.first%}
<h2 align="center"> {{ author.name }} </h2>

<div class="wrapper">
<div class="about">
<img src="{{ author.picture.path | relative_url }}" alt="{{ author.name }}" class="about_img">
</div>  
<div>
<p class="about_text">
{{ author.about }}
</p>
</div> 
</div>

{% unless forloop.last %}
<hr style="clear:both">


{% endunless %}
{% endunless %}
{% endfor %}

<h2 align="center" style="clear:both"> Thanks for visiting! </h2>