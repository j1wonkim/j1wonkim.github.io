---
layout: archive
title: "Teaching"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

## Human Rights
{% for post in site.teaching reversed %}
  {% include archive-single.html %}
{% endfor %}

## Statistics and Coding
{% for post in site.teachingqtm reversed %}
  {% include archive-single.html %}
{% endfor %}
