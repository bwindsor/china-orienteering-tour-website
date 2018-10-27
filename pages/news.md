---
layout: home
title: navigation.news
---
{%- for post in site.posts -%}

<h3 id="{{post.title}}"><a href="{{ post.url | relative_url }}">{{post.title}}</a></h3>

{{ post.excerpt | strip_html | truncatewords:30 }} 

{%- endfor -%}