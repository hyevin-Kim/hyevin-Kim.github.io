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
  <div class ="all-box">
    <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
    <div class ="all-box_datebox">
      <span class="all-box_date">{{ post.date | date: "%Y-%m-%d" }}</span>
    </div>
  </div>
	<p class ="index-page_p">{{ post.summary }}</p>
  </article>
{% endfor %}