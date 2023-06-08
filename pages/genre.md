---
title: Genre
layout: page-narrow
permalink: /genre.html
---

{%- assign items = site.data[site.metadata] | where_exp: 'item','item.objectid and item.parentid == nil' -%}
{% assign genre = items | map: 'genre' | compact | uniq %}

## Browse by Genre

{% for g in genre %}
### {{ g }}

{% assign related = items | where: 'genre',g %}
{% for r in related %}
- [{{ r.title }}]({{ '/items/' | relative_url }}{{ r.objectid }}.html){% endfor %}
{% endfor %}