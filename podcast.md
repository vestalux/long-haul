---
layout: default
title: Podcast
---

<div id="articles">
  <h1>Poscast</h1>
  <ul class="posts noList">
    {% for podcast in site.podcasts %}
      <li>
      	<span class="date">{{ post.date | date_to_string }}</span>
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      	<p class="description">{% if post.intro %}{{ post.intro  | strip_html | strip_newlines | truncate: 120 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 120 }}{% endif %}</p>
      </li>
    {% endfor %}
  </ul>
</div>


