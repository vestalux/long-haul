---
layout: default
title: Framerate
---

<div id="articles">
{% for framerate in site.framerates %}
  <ul class="posts noList">
   <li>
   <h3><a href="{{ framerate.url }}">{{ framerate.title }}</a></h3>
   {{ framerate.content | strip_html | strip_newlines | truncate: 120 }}
     </li>
  </ul>
{% endfor %}

</div>



