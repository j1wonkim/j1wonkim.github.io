---
layout: single
title: "Sitemap"
permalink:/sitemap/
author_profile: true
site_pages:
  - /
  - /about.md
  - /publications.md
  - /teaching.html
  - /portfolio.html
  - /cv.md
  - /contact.md
---

<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
{% for site_page in page.site_pages %}
<url>
  <loc>http://tagaholic.me{{site_page}}</loc>
  <lastmod>{{ site.time | date_to_xmlschema }}</lastmod>
  <changefreq>hourly</changefreq>
</url>
{% endfor %}
{% for post in site.posts %}
<url>
  <loc>http://tagaholic.me{{ post.url }}</loc>
  <lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
  <changefreq>hourly</changefreq>
</url>
{% endfor %}
</urlset>