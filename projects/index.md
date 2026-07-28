---
layout: default
title: "Projects"
---
<section class="hero">
  <span class="hero-rule" aria-hidden="true"></span>
  <h1>Projects</h1>
  <p class="lede">Builds, experiments, and artifacts worth keeping on the map.</p>
</section>

<section class="section">
  <div class="grid">
    {% assign projects = site.projects | where_exp: "item", "item.published != false" | sort: "date" | reverse %}
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
          <p><a class="btn btn-ghost" href="{{ p.url | relative_url }}">Open</a></p>
        </div>
      </article>
    {% endfor %}
  </div>
</section>
