---
layout: default
title: Publications
---

# Publications

{% assign pubs = site.data.publications | sort: "year" | reverse %}
{% assign current_year = "" %}

{% for pub in pubs %}
  {% if pub.year != current_year %}
## {{ pub.year }}
  {% assign current_year = pub.year %}
  {% endif %}

- **{{ pub.title }}**  
  {{ pub.authors }} — *{{ pub.venue }}*  
  {% if pub.url and pub.url != "" %}[Link]({{ pub.url }}){% endif %}

{% endfor %}
