---
layout: home
title: navigation.news
---
{%- for post in site.posts -%}
<h3 style="margin-bottom: 0px"><a href="{{ post.url | relative_url }}">{{post.title}}</a></h3>
<p class="post-date">
{{ post.date | date: "%d %b %y" }}
</p>
<p>
{{ post.excerpt | strip_html | truncatewords:30 }} 
</p>
{%- endfor -%}