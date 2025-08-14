---
layout: default
title: "Home"
---

<section class="hero">
  <h1>Sarkany Nexus</h1>
  <p>Stories, boardgame design updates, and portfolio.</p>
</section>

<section>
  <h2>Latest Stories</h2>
  <div class="grid">
  {% assign latest_stories = site.stories | sort: 'date' | reverse | slice: 0, 3 %}
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
        <p><a class="btn" href="{{ story.url | relative_url }}">Read</a></p>
      </div>
    </article>
  {% endfor %}
  </div>
</section>

<section>
  <h2>Boardgame Updates</h2>
  {% assign latest_updates = site.updates | sort: 'date' | reverse | slice: 0, 3 %}
  <ul>
    {% for u in latest_updates %}
      <li><a href="{{ u.url | relative_url }}">{{ u.title }}</a> — <span class="muted">{{ u.date | date: "%Y-%m-%d" }}</span></li>
    {% endfor %}
  </ul>
  <p><a class="btn" href="{{ '/boardgame/' | relative_url }}">All updates</a></p>
</section>

<section>
  <h2>Recent Projects</h2>
  <div class="grid">
  {% assign latest_projects = site.projects | sort: 'date' | reverse | slice: 0, 3 %}
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
        <p>{{ p.excerpt }}</p>
        <p><a class="btn" href="{{ p.url | relative_url }}">Open</a></p>
      </div>
    </article>
  {% endfor %}
  </div>
</section>
