---
layout: default
title: Events
---

<div id="articles">
{% for event in site.events %}
  <ul class="posts noList">
   <li>
   <h3><a href="{{ event.url }}">{{ event.title }}</a></h3>
   {{ event.content | strip_html | strip_newlines | truncate: 120 }}
     </li>
  </ul>
{% endfor %}

</div>


