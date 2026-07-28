---
layout: default
title: "Boardgame Updates"
---
<section class="hero">
  <h1>Boardgame Updates</h1>
  <p class="muted">Boardgame design notes and devlogs.</p>
</section>

<section>
  <div class="grid">
    {% assign updates = site.updates | where_exp: "item", "item.published != false" | sort: "date" | reverse %}
    {% for u in updates %}
      <article class="card">
        <div class="thumb" aria-hidden="true"></div>
        <div class="body">
          <h3><a href="{{ u.url | relative_url }}">{{ u.title }}</a></h3>
          <p class="muted">{{ u.date | date: "%Y-%m-%d" }}</p>
          {% if u.excerpt %}
            <p>{{ u.excerpt }}</p>
          {% endif %}
          <p><a class="btn" href="{{ u.url | relative_url }}">Read</a></p>
        </div>
      </article>
    {% endfor %}
  </div>
</section>
