---
layout: default
title: "Projects"
---
<section class="hero">
  <h1>Projects</h1>
  <p class="muted">Portfolio items.</p>
</section>

<section>
  <div class="grid">
    {% assign projects = site.projects | sort: "date" | reverse %}
    {% for p in projects %}
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
          <p><a class="btn" href="{{ p.url | relative_url }}">Open</a></p>
        </div>
      </article>
    {% endfor %}
  </div>
</section>

