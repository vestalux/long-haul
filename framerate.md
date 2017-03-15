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
	padding: 0 0px;}

li.teaser:before{background:none;}
}
  
  </style>
<div id="articles">
 <ul class="posts noList">
 
    {% for post in site.framerates %}
      <li class="teaser">
    {% if post.image %}<a class="post-link" href="{{ framerate.url | prepend: site.baseurl }}"><img src="{{ '/uploads/' | prepend: site.baseurl | append: framerate.image }}" alt=""></a> {% endif %}
	   </li>
     {% endfor %}
    </ul>

</div>


  
 
