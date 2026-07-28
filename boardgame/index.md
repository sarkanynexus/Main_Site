---
layout: default
title: "Boardgame Updates"
---
<section class="hero">
  <span class="hero-rule" aria-hidden="true"></span>
  <h1>Boardgame</h1>
  <p class="lede">Design notes, playtest scars, and rules that refuse to sit still.</p>
</section>

<section class="section">
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
          <p><a class="btn btn-ghost" href="{{ u.url | relative_url }}">Read</a></p>
        </div>
      </article>
    {% endfor %}
  </div>
</section>
