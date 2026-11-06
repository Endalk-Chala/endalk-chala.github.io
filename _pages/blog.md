---
layout: archive
title: "Blog"
permalink: /blog/
author_profile: true
---

{% include base_path %}

<p class="archive__intro" style="font-size:1.05em; line-height:1.7; margin-bottom:2em;">
Notes on research in progress, teaching, and the working life of a scholar. I write here to think in public and to leave a record that others can use. Posts appear by year; calls for papers and funding notices live separately under <a href="{{ base_path }}/opportunities/">Field Opportunities</a>.
</p>

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% unless post.categories contains "opportunities" %}
    {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
    {% if year != written_year %}
      <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
      {% capture written_year %}{{ year }}{% endcapture %}
    {% endif %}
    {% include archive-single.html %}
  {% endunless %}
{% endfor %}
