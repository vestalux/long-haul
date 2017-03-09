---
layout: default
title: Podcast
---

<div id="articles">
  <h1>Poscast</h1>
  <ul class="posts noList">
    {% for podcast in site.podcasts %}
      <li>
      	<span class="date">{{ podcast.date | date_to_string }}</span>
      	<h3><a href="{{ podcast.url }}">{{ podcast.title }}</a></h3>
      	<p class="description">{% if podcast.intro %}{{ podcast.intro  | strip_html | strip_newlines | truncate: 120 }}{% else %}{{ podcast.content | strip_html | strip_newlines | truncate: 120 }}{% endif %}</p>
      </li>
    {% endfor %}
  </ul>
</div>


