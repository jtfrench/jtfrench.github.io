---
layout: default
title: Home
---

<div class="home-header">
  <h1 class="home-title">{{ site.title }}</h1>
  <p class="home-description">{{ site.description }}</p>
</div>

{% if site.posts.size > 0 %}
<ul class="post-list">
  {% for post in site.posts %}
  <li class="post-list-item">
    <h2 class="post-list-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>
    <p class="post-list-meta">
      {{ post.date | date: "%B %-d, %Y" }}
    </p>
    {% if post.excerpt %}
    <p class="post-list-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    {% endif %}
  </li>
  {% endfor %}
</ul>
{% else %}
<p>No posts yet.</p>
{% endif %}
