---
layout: default
title: Framerate
---
<style>
@media only screen and (min-width: 800px) {
   .teaser {
	float: left;
	width: 33%;
	box-sizing: border-box;
	padding: 0 5px;}

li.teaser:before{background:none;}
.image {width: 254px;height: 254px;background-size: cover;
   background-position: center center;}
}
  
  </style>
<div id="articles">

 <h1 class="pageTitle">Framerate</h1>
 <div class="post">
 <blockquote>Framrate captures the moments that wouldn't be enough for a story but without them we wouldn't see the big picture</blockquote>
 </div>
 <ul class="posts noList">
 
    {% for post in site.framerates reversed %}
      <li class="teaser">
    {% if post.image %}<a class="post-link" href="{{ post.url | prepend: site.baseurl }}"><div class="image" style="background: url({{ '/uploads/' | prepend: site.baseurl | append: post.image }} );"></div></a> {% endif %}
    	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
	   </li>
     {% endfor %}
    </ul>


</div>


  
 
