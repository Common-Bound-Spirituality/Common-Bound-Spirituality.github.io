---
layout: archive
permalink: /blog-archive/
title: "Blog Posts by Year"
author_profile: true
header:
  overlay_image: /assets/images/grancanyon1.jpg
  overlay_filter: rgba(0, 0, 0, 0)
  # cta_label: "Start Learning"
  # cta_url: /Learn More/
---

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'"  %}
{% for year in postsByYear %}
  <h2 id="{{ year.name | slugify }}" class="archive__subtitle">{{ year.name }}</h2>
  {% for post in year.items %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}