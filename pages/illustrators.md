---
title: Illustrators
layout: page-narrow
permalink: /illustrators.html
---

{%- assign items = site.data[site.metadata] | where_exp: 'item','item.objectid and item.parentid == nil' -%}
{% assign illustrators = items | map: 'illustrator' | compact | uniq %}

## Browse Illustrators

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. 

{% for i in illustrators %}
### {{ i }}

{% assign related = items | where: 'illustrator',i %}
{% for r in related %}
- [{{ r.title }}]({{ '/items/' | relative_url }}{{ r.objectid }}.html){% endfor %}
{% endfor %}