---
layout: archive
title: "Blog"
permalink: /blog/
author_profile: true
---

{% include base_path %}

<p class="archive__intro" style="font-size:1.05em; line-height:1.7; margin-bottom:2em;">
Notes on research in progress, teaching, and the working life of a scholar. I write here to think in public and to leave a record that others can use. Posts appear by year; calls for papers and funding notices live separately under <a href="{{ base_path }}/opportunities/">Opportunities</a>.
</p>

{% assign written_year = '' %}
{% for post in site.posts %}
{% unless post.categories contains "opportunities" %}
{% assign year = post.date | date: '%Y' %}
{% if year != written_year %}

<h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>

{% assign written_year = year %}
{% endif %}
{% include archive-single.html %}
{% endunless %}
{% endfor %}
