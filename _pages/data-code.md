---
layout: archive
title: "Data & Code"
permalink: /data-code/
author_profile: true
---

{% include base_path %}

<!-- 新样式：按类别分组渲染 -->
{% if site.data-code_category %}
  {% for category in site.data-code_category %}
    {% assign title_shown = false %}
    {% for post in site.data-code reversed %}
      {% if post.category != category[0] %}
        {% continue %}
      {% endif %}
      {% unless title_shown %}
        <h2>{{ category[1].title }}</h2><hr />
        {% assign title_shown = true %}
      {% endunless %}
      {% include archive-single.html %}
    {% endfor %}
  {% endfor %}
{% else %}
  <!-- 没有定义类别时的平铺显示 -->
  {% for post in site.data-code reversed %}
    {% include archive-single.html %}
  {% endfor %}
{% endif %}



