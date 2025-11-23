---
layout: default
title: Home
---

<div class="home-header">
  <h1 class="home-title">Monkeys In Shoes</h1>
  <p class="home-description">A detailed and interactive analysis of the human condition.</p>
</div>

## Table of Contents

{% assign sorted_chapters = site.chapters | sort: 'chapter' %}
<ol class="toc-list">
{% for chapter in sorted_chapters %}
  <li class="toc-item">
    <a href="{{ chapter.url | relative_url }}">{{ chapter.title }}</a>
  </li>
{% endfor %}
</ol>

<p style="margin-top: 2rem;"><a href="/about/">About this project</a></p>
