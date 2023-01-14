---
layout: page
title: news
permalink: /news/
nav: true
nav_order: 1
dropdown: false
---

{% if site.news != blank -%} {%- assign news_size = site.news | size -%}
3 %}style="max-height: 10vw"{% endif %}> {%- assign news = site.news | reverse -%} {% assign news_limit = news_size %} {% for item in news limit: news_limit %} {%- endfor %}
{{ item.date | date: "%b %-d, %Y" }}	{% if item.inline -%} {{ item.content | remove: '
' | remove: '

' | emojify }} {%- else -%} {{ item.title }} {%- endif %}
{%- else -%}
No news so far...

{%- endif %}