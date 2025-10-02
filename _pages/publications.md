---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

### International human rights shaming

___

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

<br><br>

### Populist rhetoric

___

{% for post in site.populism %}
  {% include archive-single.html %}
{% endfor %}
