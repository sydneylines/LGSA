---
title: Illustrators
layout: page-narrow
permalink: /illustrators.html
---

{%- assign items = site.data[site.metadata] | where_exp: 'item','item.objectid and item.parentid == nil' -%}
{% assign illustrators = items | map: 'illustrator' | compact | uniq %}

## Browse Illustrators

{% for i in illustrators %}
### {{ i }}

{% assign related = items | where: 'illustrator',i %}
{% for r in related %}
- [{{ r.title }}]({{ '/items/' | relative_url }}{{ r.objectid }}.html){% endfor %}
{% endfor %}