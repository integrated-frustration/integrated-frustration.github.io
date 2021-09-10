---
layout: page
title: About Us
hide_description: true
permalink: /about/
redirect_from:
  - /download/
---

Our vision is to share the __*frustration*__ that is inevitably __*integrated*__ into DIY projects.
{:.lead}

We want to contribute the knowledge and skills we gained by __making mistakes__, __troubleshooting__ our work and 
__refining__ our creative and cognitive processes.
We hope you find our experiences useful and we would love to hear from you!


<hr>

{% assign social = site.data.social %}
{% for author in site.data.authors %}

{% unless forloop.first %}

<div class="wrapper">

## {{ author.name }}
<div id="img">
<img src="{{ author.picture.path | relative_url }}" alt="{{ author.name }}" class="about_img">
</div>

<div id="txt">
<p class="about_text">
{{ author.about }}
</p>
</div>

<div class="sidebar-social" id="ico">
<ul> 
<li> <a href="{{ author.email | prepend: social.email.prepend }}" title="{{ social.email.name }}" class="no-mark-external">
<span class="{{ social.email.icon }}"></span></a></li>
<li> <a href="{{ author.linkedin | prepend: social.linkedin.prepend }}" title="{{ social.linkedin.name }}" class="no-mark-external">
<span class="{{ social.linkedin.icon }}"></span></a></li>
</ul>
</div>

</div>

<hr style="clear:both">
{% endunless %}
{% endfor %}


## Contact Us!
{% assign author = site.data.authors[0] %}

Send us an email:
~~~
{{ author.email }}
~~~

Check out our Github to see how this site was made:
~~~
{{ author.github | prepend: social.github.prepend }}
~~~

<h2 align="center" style="clear:both"> Thanks for visiting! </h2>