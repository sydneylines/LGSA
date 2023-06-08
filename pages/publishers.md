---
title: Publishers
layout: page-narrow
permalink: /publishers.html
---
{%- assign items = site.data[site.metadata] | where_exp: 'item','item.objectid and item.parentid == nil' -%}
{% assign publishers = items | map: 'publisher' | compact | uniq %}

## Browse Publishers

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum

{% for p in publishers %}
### {{ p }}

{% assign related = items | where: 'publisher',p %}
{% for r in related %}
- [{{ r.title }}]({{ '/items/' | relative_url }}{{ r.objectid }}.html){% endfor %}
{% endfor %}