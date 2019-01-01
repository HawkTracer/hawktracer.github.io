---
layout: page
title: Features
---
{% include featureslist.html %}

{% for feature in site.data.features %}
  <h4 id="#{{ feature.ref }}">{{ feature.name }}</h4>
{% endfor %}
