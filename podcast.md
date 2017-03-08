---
layout: default
title: Cookies
---
{% for cookie in site.podcasts %}
  <div class="podcast">
    <h2><img src="{{ podcast.image_path }}" alt="{{ podcast.title }}">{{ podcast.title }}</a></h2>
    {{ podcast.content }}
  </div>
{% endfor %}
