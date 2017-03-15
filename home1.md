---
layout: default
title: Your New Jekyll Site
---
<style>
.teaser {
	float: left;
	width: 33%;
	box-sizing: border-box;
	padding: 0 30px;}

li.tesaer:before{background:none;}

@media only screen and (max-device-width : 800px) {
  .teaser {
    float: none;
    position: static;
    width: auto;
    height: auto;
  }
  
  </style>

<div id="articles">
  <h1 class="pageTitle">Recent Stories</h1>
  <ul class="posts noList">
    {% for post in site.posts limit:1 %}
      <li>
      	<span class="date">{{ post.date | date_to_string }}</span>
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
	 {% if post.image %}<a class="post-link" href="{{ post.url | prepend: site.baseurl }}"><img src="{{ '/uploads/' | prepend: site.baseurl | append: post.image }}" alt=""></a> {% endif %}
      	<p class="description">{% if post.description %}{{ post.description  | strip_html | strip_newlines | truncate: 120 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 120 }}{% endif %}</p>
      </li>
    {% endfor %}
    </ul>
    
  
  <ul class="posts noList">
 
    {% for post in site.posts limit:3 offset:1 %}
      <li class="teaser">
    {% if post.image %}<a class="post-link" href="{{ post.url | prepend: site.baseurl }}"><img src="{{ '/uploads/' | prepend: site.baseurl | append: post.image }}" alt=""></a> {% endif %}
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
	   </li>
     {% endfor %}
    </ul>
  

</div>
