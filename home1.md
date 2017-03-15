---
layout: default
title: Your New Jekyll Site
---
<style>
@media only screen and (min-width: 800px) {
   .teaser {
	float: left;
	width: 33%;
	box-sizing: border-box;
	padding: 0 5px;}

li.teaser:before{background:none;}
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
      	<p class="description">{% if post.description %}{{ post.description  | strip_html | strip_newlines | truncate: 200 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 200 }}{% endif %}</p>
      </li>
    {% endfor %}
    </ul>
    
  
  <ul class="posts noList">
 
    {% for post in site.posts limit:3 offset:1 %}
      <li class="teaser">
    {% if post.image %}<a class="post-link" href="{{ post.url | prepend: site.baseurl }}"><img src="{{ '/uploads/' | prepend: site.baseurl | append: post.image }}" alt=""></a> {% endif %}
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
	      	<span class="date">{{ post.date | date_to_string }}</span>

	   </li>
     {% endfor %}
    </ul>
 <div class="post">
 <blockquote>
<h3>Good times are made of great moments</h3>
 </blockquote>
 </div>

 <div class="featuredImage">
 {% for post in site.framerates limit:1 %}
     
    {% if post.image %}<a class="post-link" href="{{ post.url | prepend: site.baseurl }}"><img src="{{ '/uploads/' | prepend: site.baseurl | append: post.image }}" alt="" ></a> {% endif %}
 {% endfor %}
</div>
  </div>
