---
layout: default
title: Podcast
---
{% for podcast in site.podcasts %}
  <div class="podcast">
    <h2>{{ podcast.title }}</h2>
    {{ podcast.content }}
  </div>
{% endfor %}
