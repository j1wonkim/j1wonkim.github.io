---
layout: archive
title: "Teaching"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

{% for post in site.teaching reversed %}
  {% include archive-single.html %}
{% endfor %}

## TA

{% include base_path %}

{% for post in site.ta reversed %}
  {% include archive-single.html %}
{% endfor %}
