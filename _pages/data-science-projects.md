---
layout: archive
permalink: /data-science-projects/
title: "Data Science Projects by Topic"
header:
  images: "/assets/images/bruges-coverphoto.jpg"
# {% include group-by-array collection=site.posts field="tags" %}

# {% for tag in group_names %}
  # {% assign posts = group_items[forloop.index0] %}
  #<h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
#  {% for post in posts %}
#    {% include archive-single.html %}
#  {% endfor %}
# {% endfor %}

---

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
  {% unless collection.output == false or collection.label == "posts" %}
    {% capture label %}{{ collection.label }}{% endcapture %}
    {% if label != written_label %}
      <h2 id="{{ label | slugify }}" class="archive__subtitle">{{ label }}</h2>
      {% capture written_label %}{{ label }}{% endcapture %}
    {% endif %}
  {% endunless %}
  {% for post in collection.docs %}
    {% unless collection.output == false or collection.label == "posts" %}
      {% include archive-single.html %}
    {% endunless %}
  {% endfor %}
{% endfor %}
