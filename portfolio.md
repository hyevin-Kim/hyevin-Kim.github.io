---
bg: 'bg.jpeg'
layout: page
permalink: /posts/
title: 'all post'
crawlertitle: 'all post'
summary: '모든 게시물이 시간순으로 정렬되었습니다!'
active: portfolio
---

{% for post in site.posts limit: 5 %}

<article class="index-page">
	<h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
	{{ post.excerpt }}
</article>

{% endfor %}
