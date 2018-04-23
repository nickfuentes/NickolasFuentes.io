---
layout: archive
permalink: /web-development-blogs/
title: "Web Development Posts by Tags"
author_profile: true
---

{% include base_path %}
{% include group-by-array collections=site.posts field='tags' %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive_subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
