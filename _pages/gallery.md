---
layout: page
title: Gallery
permalink: /gallery/
description: Lab activities and photo highlights (click a title to view more images)
nav: true
nav_order: 2
---

<div class="gallery-list">

  {% assign gallery_posts = site.posts | where_exp: "p", "p.categories contains 'gallery'" | sort: "date" | reverse %}

  {% if gallery_posts.size == 0 %}
    <p>
      No gallery items yet. Add posts in <code>_posts/</code> with <code>categories: [gallery]</code>.
    </p>
  {% else %}

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
            <a href="{{ post.url | relative_url }}">
              <img
                class="gallery-thumb"
                src="{{ post.thumbnail | relative_url }}"
                alt="{{ post.title }} thumbnail">
            </a>
          {% endif %}
        </li>
      {% endfor %}
    </ul>

  {% endif %}

</div>
