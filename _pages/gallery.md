---
layout: page
title: Gallery
permalink: /gallery/
description: A visual archive of VIC Lab activities, collaborations, visits, and academic events.
nav: true
nav_order: 2
---

{% assign gallery_posts = site.posts
  | where_exp: "post", "post.categories contains 'gallery'"
  | sort: "date"
  | reverse
%}

<div class="gallery-archive">

  <section class="gallery-category">
    <div class="gallery-category-heading">
      <span class="gallery-category-icon">🔬</span>
      <div>
        <h2>Lab Life</h2>
        <p>Student activities, defenses, internships, meetings, celebrations, and everyday life at VIC Lab.</p>
      </div>
    </div>

    <div class="gallery-card-grid">
      {% assign category_posts = gallery_posts | where: "gallery_type", "lab" %}

      {% for post in category_posts %}
        {% include gallery_card.liquid post=post %}
      {% else %}
        <p class="gallery-empty">No gallery items are available in this category yet.</p>
      {% endfor %}
    </div>
  </section>

  <section class="gallery-category">
    <div class="gallery-category-heading">
      <span class="gallery-category-icon">🤝</span>
      <div>
        <h2>Collaborations & Visitors</h2>
        <p>International collaborators, visiting researchers, university visits, and partner activities.</p>
      </div>
    </div>

    <div class="gallery-card-grid">
      {% assign category_posts = gallery_posts | where: "gallery_type", "collaboration" %}

      {% for post in category_posts %}
        {% include gallery_card.liquid post=post %}
      {% else %}
        <p class="gallery-empty">No gallery items are available in this category yet.</p>
      {% endfor %}
    </div>
  </section>

  <section class="gallery-category">
    <div class="gallery-category-heading">
      <span class="gallery-category-icon">🌏</span>
      <div>
        <h2>Conferences & Academic Events</h2>
        <p>Conference participation, workshops, presentations, invited talks, and academic events.</p>
      </div>
    </div>

    <div class="gallery-card-grid">
      {% assign category_posts = gallery_posts | where: "gallery_type", "conference" %}

      {% for post in category_posts %}
        {% include gallery_card.liquid post=post %}
      {% else %}
        <p class="gallery-empty">No gallery items are available in this category yet.</p>
      {% endfor %}
    </div>
  </section>

</div>