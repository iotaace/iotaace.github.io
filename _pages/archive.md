---
layout: archive
permalink: /archive/
title: "Posts by Year"
author_profile: true
---

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
{% if year != written_year %}
<h1 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h1>
{% capture written_year %}{{ year }}{% endcapture %}
{% endif %}
{% include archive-single.html %}
{% endfor %}