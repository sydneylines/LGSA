---
title: Genre
layout: page-narrow
permalink: /genre.html
---

{%- assign items = site.data[site.metadata] | where_exp: 'item','item.objectid and item.parentid == nil' -%}
{% assign genre = items | map: 'genre' | compact | uniq %}

## Browse by Genre

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum

{% for g in genre %}
### {{ g }}

{% assign related = items | where: 'genre',g %}
{% for r in related %}
- [{{ r.title }}]({{ '/items/' | relative_url }}{{ r.objectid }}.html){% endfor %}
{% endfor %}