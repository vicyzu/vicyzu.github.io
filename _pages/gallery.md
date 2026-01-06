---
layout: page
title: Gallery
permalink: /gallery/
description: Lab activities and photo highlights
nav: true
nav_order: 2
---

<div class="publications">

{% assign gallery_posts = site.posts | where_exp: "p", "p.categories contains 'gallery'" %}

{% if gallery_posts.size == 0 %}
<p>No gallery items yet. Add posts in <code>_posts/</code> with <code>categories: [gallery]</code>.</p>
{% endif %}

<ul class="post-list">
  {% for post in gallery_posts %}
    <li>
      <h3>
        <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>

      {% if post.description %}
        <p>{{ post.description }}</p>
      {% endif %}

      <p class="post-meta">
        {{ post.date | date: '%B %d, %Y' }}
      </p>

      {% if post.thumbnail %}
          <img class="gallery-thumb"
       src="{{ post.thumbnail | relative_url }}"
       alt="thumbnail">
{% endif %}
    </li>
  {% endfor %}
</ul>

</div>
