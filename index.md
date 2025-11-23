---
layout: default
title: Home
---

<div class="home-header">
  <h1 class="home-title">Monkeys In Shoes</h1>
  <p class="home-description">A detailed and interactive analysis of the human condition.</p>
</div>

## Table of Contents

{% assign sorted_posts = site.posts | sort: 'chapter' %}
<ol class="toc-list">
{% for post in sorted_posts %}
  <li class="toc-item">
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ol>

<p style="margin-top: 2rem;"><a href="/about/">About this project</a></p>
