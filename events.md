---
layout: default
title: HopBot - Events
---

<div class="home" id="home">
  <h1 class="pageTitle">Upcoming Events</h1>
  <ul class="posts noList">

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

      
  <li>
  <span class="date">{{ event.event-start-date | date: '%B %d, %Y' }}{% if event.event-end-date %} &#8211; {{ event.event-end-date | date: '%B %d, %Y' }}{% endif %}</span>
    <h3><a class="post-link" href="{{ event.url | prepend: site.baseurl }}">{{ event.title }}</a></h3>
    {% if post.image %}<a class="post-link" href="{{ post.url | prepend: site.baseurl }}"><img src="{{ '/uploads/' | prepend: site.baseurl | append: post.image }}" alt=""></a> {% endif %}
           
        <span class="date">{{ event.location-text }}</span>
           <span class="date">{{ event.event-start-time }}</span>
          
  </li>
    {% endif %}

    {% endfor %}

  </ul>

</div>



