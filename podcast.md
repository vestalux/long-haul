---
layout: default
title: Podcast
---

<div id="articles">
{% for podcast in site.podcasts %}
  <ul class="posts noList">
   <li>
   <h3><a href="{{ podcast.url }}">{{ podcast.title }}</a></h3>
   {{ podcast.content | strip_html | strip_newlines | truncate: 120 }}
     </li>
  </ul>
{% endfor %}

</div>



