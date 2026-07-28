---
layout: default
title: "Home"
---

{% if site.coming_soon %}
<section class="hero-plane" aria-label="Sarkany Nexus">
  <div class="hero-atmos" aria-hidden="true"></div>
  <div class="hero-copy">
    <span class="hero-rule" aria-hidden="true"></span>
    <h1 class="brand-title">Sarkany Nexus</h1>
    <p class="promise">Stories, tabletop worlds, and strange inventions — assembling.</p>
    <p><a class="btn" href="mailto:info@sarkanynexus.com">Signal us</a></p>
  </div>
</section>
{% else %}
<section class="hero-plane" aria-label="Sarkany Nexus">
  <div class="hero-atmos" aria-hidden="true"></div>
  <div class="hero-copy">
    <span class="hero-rule" aria-hidden="true"></span>
    <h1 class="brand-title">Sarkany Nexus</h1>
    <p class="promise">Dark fantasy fiction, boardgame design, and maker projects from one orbit.</p>
    <p><a class="btn" href="{{ '/stories/' | relative_url }}">Enter the archive</a></p>
  </div>
</section>

<section class="section">
  <div class="section-head">
    <h2>Latest stories</h2>
    <a class="muted" href="{{ '/stories/' | relative_url }}">All stories</a>
  </div>
  <div class="grid">
  {% assign latest_stories = site.stories | where_exp: "item", "item.published != false" | sort: "date" | reverse | slice: 0, 3 %}
  {% for story in latest_stories %}
    <article class="card">
      {% if story.cover %}
        <img class="thumb-img" src="{{ story.cover | relative_url }}" alt="{{ story.title }} cover" loading="lazy">
      {% else %}
        <div class="thumb" aria-hidden="true"></div>
      {% endif %}
      <div class="body">
        <h3><a href="{{ story.url | relative_url }}">{{ story.title }}</a></h3>
        <p class="muted">{{ story.length }} {% if story.tags %}• {{ story.tags | join: ", " }}{% endif %}</p>
        <p>{{ story.excerpt }}</p>
        <p><a class="btn btn-ghost" href="{{ story.url | relative_url }}">Read</a></p>
      </div>
    </article>
  {% endfor %}
  </div>
</section>

<section class="section">
  <div class="section-head">
    <h2>Boardgame updates</h2>
    <a class="muted" href="{{ '/boardgame/' | relative_url }}">All updates</a>
  </div>
  {% assign latest_updates = site.updates | where_exp: "item", "item.published != false" | sort: "date" | reverse | slice: 0, 3 %}
  <ul class="update-list">
    {% for u in latest_updates %}
      <li>
        <a href="{{ u.url | relative_url }}">{{ u.title }}</a>
        <span class="muted">{{ u.date | date: "%Y-%m-%d" }}</span>
      </li>
    {% endfor %}
  </ul>
</section>

<section class="section">
  <div class="section-head">
    <h2>Projects</h2>
    <a class="muted" href="{{ '/projects/' | relative_url }}">All projects</a>
  </div>
  <div class="grid">
  {% assign latest_projects = site.projects | where_exp: "item", "item.published != false" | sort: "date" | reverse | slice: 0, 3 %}
  {% for p in latest_projects %}
    <article class="card">
      {% if p.cover %}
        <img class="thumb-img" src="{{ p.cover | relative_url }}" alt="{{ p.title }} cover" loading="lazy">
      {% else %}
        <div class="thumb" aria-hidden="true"></div>
      {% endif %}
      <div class="body">
        <h3><a href="{{ p.url | relative_url }}">{{ p.title }}</a></h3>
        <p class="muted">{% if p.tags %}{{ p.tags | join: ", " }}{% endif %}</p>
        {% if p.excerpt %}
          <p>{{ p.excerpt }}</p>
        {% endif %}
        <p><a class="btn btn-ghost" href="{{ p.url | relative_url }}">Open</a></p>
      </div>
    </article>
  {% endfor %}
  </div>
</section>
{% endif %}
