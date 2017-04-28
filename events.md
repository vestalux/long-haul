---
layout: default
title: Events
---

<div id="articles">

    {% assign events = site.events | sort: 'event-start-date'%}

    {% for event in events %}

    {% capture now-unix-seconds %}{{'now' | date: '%s' }}{% endcapture %}

    {% if event.event-end-date %}

        {% capture event-time-seconds %}{{event.event-end-date | date: '%s' }}{% endcapture %}

    {% else %}

        {% capture event-time-seconds %}{{event.event-start-date | date: '%s' }}{% endcapture %}

    {% endif %}

    {% capture event-time %}{{ event-time-seconds | divided_by: 86400}}{% endcapture %}

    {% capture now-unix %}{{ now-unix-seconds | divided_by: 86400}}{% endcapture %}

    {% if now-unix <= event-time %}

      

          <a href="{{ event.url }}">{{ event.title }}</a>     
          {{ event.location-text }}
          {{ event.event-start-date | date: "%a %-d %b, %Y" }}{% if event.event-end-date %} &#8211; {{ event.event-end-date | date: "%a %-d %b, %Y" }}{% endif %}
           {{ event.event-start-time }}

    {% endif %}

    {% endfor %}








{% for event in site.events %}
  <ul class="posts noList">
   <li>
   <h3><a href="{{ event.url }}">{{ event.title }}</a></h3>
   {{ event.content | strip_html | strip_newlines | truncate: 120 }}
     </li>
  </ul>
{% endfor %}

</div>


