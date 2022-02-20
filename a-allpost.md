---
bg: "./base/bg.jpeg"
layout: default
title: "all post"
crawlertitle: "ALL POST"
permalink: /a-allpost/
summary: "모든 게시물이 시간순으로 정렬되었습니다!"
active: all
---

{% for post in site.posts limit: 20 %}
  <article class="index-page">
	<h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
	{{ post.excerpt }}
  </article>
{% endfor %}