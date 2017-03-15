---
layout: default
title: Your New Jekyll Site
---
<style>
.cupcakes {
	margin: 40px 0 0 0;
}

.cupcake {
	float: left;
	width: 33%;
	box-sizing: border-box;
	padding: 0 30px;
	height: 450px;
}</style>

<div id="articles">
  <h1>Articles</h1>
  <ul class="posts noList">
    {% for post in site.posts limit:1 %}
      <li>
      	<span class="date">{{ post.date | date_to_string }}</span>
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      	<p class="description">{% if post.description %}{{ post.description  | strip_html | strip_newlines | truncate: 120 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 120 }}{% endif %}</p>
      </li>
    {% endfor %}
  </ul>
  <div class="cupcakes">

    <ul class="posts noList">
    {% for post in site.posts limit:3 offset:1 %}
      <div class="cupcake">

      <li>
      	<span class="date">{{ post.date | date_to_string }}</span>
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      	<p class="description">{% if post.description %}{{ post.description  | strip_html | strip_newlines | truncate: 120 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 120 }}{% endif %}</p>
      </li>
        </div>

    {% endfor %}
  </ul>
  </div>

</div>
