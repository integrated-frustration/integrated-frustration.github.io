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
We hope you find our experiences useful and we would love to hear from you!
{:.about_text}

{% assign social = site.data.social %}
{% for author in site.data.authors %}
{% if forloop.first %}

<div class="sidebar-social" align="center">
<ul> 
<li> <a href="{{ author.email | prepend: social.email.prepend }}" title="{{ social.email.name }}" class="no-mark-external">
<span class="{{ social.email.icon }}"></span></a></li>
<li> <a href="{{ author.github | prepend: social.github.prepend }}" title="{{ social.github.name }}" class="no-mark-external">
<span class="{{ social.github.icon }}"></span></a></li>
</ul>
</div>

<hr>
{% endif %}


{% unless forloop.first %}
<h2 align="center"> {{ author.name }} </h2>

<div class="wrapper">
<div class="about">
<img src="{{ author.picture.path | relative_url }}" alt="{{ author.name }}" class="about_img">

<div class="sidebar-social">
<ul> 
<li> <a href="{{ author.email | prepend: social.email.prepend }}" title="{{ social.email.name }}" class="no-mark-external">
<span class="{{ social.email.icon }}"></span></a></li>
<li> <a href="{{ author.linkedin | prepend: social.linkedin.prepend }}" title="{{ social.linkedin.name }}" class="no-mark-external">
<span class="{{ social.linkedin.icon }}"></span></a></li>
</ul>
</div>

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