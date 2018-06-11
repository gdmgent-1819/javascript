---
layout: course
title: Presentaties
title_long: Presentaties
permalink: presentations/
---

{% capture wherevalue %}item.path contains 'pages/presentations'{% endcapture %}
{% assign pages = site.pages | where_exp:"item", wherevalue %}
{% if pages %}
<ul class="cards-list">
  {% for page in pages %}
    {% if page.path != 'pages/presentations/index.md' %}
      <li class="ahs-g__cl-xxs-12 ahs-g__cl-xs-12 ahs-g__cl-sm-12 ahs-g__cl-md-6 ahs-g__cl-lg-6 ahs-g__cl-xlg-4">
      {% include presentation/presentation-item.small.html presentation=page %}
      </li>
    {% endif %}
  {% endfor %}
</ul>
{% endif %}