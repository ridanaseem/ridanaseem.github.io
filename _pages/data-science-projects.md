---
layout: archive
permalink: /data-science-projects/
title: "Data Science Projects by Tag"
header:
  image: #"/assets/images/bruges-coverphoto.jpg"
layout: collection

---

{% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
