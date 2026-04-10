---
layout: page
title: Creative Portfolio
subtitle: Conference stickers, character designs, and science-inspired visual storytelling
permalink: /portfolio/
---

{% assign portfolio_items = site.data.portfolio %}

<section class="portfolio-intro">
  <p class="portfolio-kicker">Creative Work</p>
  <p class="portfolio-lede">
    Alongside my research, I love making fun designs that help scientific spaces feel more human, welcoming, and memorable.
    This page highlights my creative work including stickers, character design, and science-inspired visuals. I create my work using Procreate on an iPad with an Apple Pencil.
  </p>
</section>

{% if portfolio_items and portfolio_items.size > 0 %}
<section class="portfolio-grid" aria-label="Creative portfolio gallery">
  {% for item in portfolio_items %}
  <article class="portfolio-card">
    <div class="portfolio-image-wrap">
      <img src="{{ item.image | relative_url }}" alt="{{ item.alt }}" class="portfolio-image">
    </div>
    <div class="portfolio-content">
      <p class="portfolio-type">{{ item.type }}</p>
      <h2 class="portfolio-title">{{ item.title }}</h2>
      {% if item.event %}
      <p class="portfolio-event">{{ item.event }}</p>
      {% endif %}
      {% if item.summary %}
      <p class="portfolio-summary">{{ item.summary }}</p>
      {% endif %}
      {% if item.details %}
      <ul class="portfolio-detail-list">
        {% for detail in item.details %}
        <li>{{ detail }}</li>
        {% endfor %}
      </ul>
      {% endif %}
    </div>
  </article>
  {% endfor %}
</section>
{% endif %}
