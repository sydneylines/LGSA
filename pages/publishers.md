---
title: Publishers
layout: page-narrow
permalink: /publishers.html
---
{%- assign items = site.data[site.metadata] | where_exp: 'item','item.objectid and item.parentid == nil' -%}
{% assign publishers = items | map: 'publisher' | compact | uniq %}

## Browse Publishers

{% for p in publishers %}
### {{ p }}

{% assign related = items | where: 'publisher',p %}
{% for r in related %}
- [{{ r.title }}]({{ '/items/' | relative_url }}{{ r.objectid }}.html){% endfor %}
{% endfor %}