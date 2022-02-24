---
bg: "./base/bg.svg"
layout: post
title: "맥(macOS)에서 자바(java) 설치, 이클립스 설치"
crawlertitle: "how to install java"
date: 2022-02-23
summary: "macOS, java, eclipse"
excerpt: "맥(macOS)에서 자바(java) 설치, 이클립스 설치"
#category: "test"
tags: [java, eclipse, macOS]
author: vvney
---

{% assign category =  page.category| default: page.title %}
{% for post in site.categories[category] %}
<article class="index-page">
    <h4>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h4>
    {{ post.excerpt }}
</article>
{% endfor %}