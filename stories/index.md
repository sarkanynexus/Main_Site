---
layout: default
title: "Stories"
---

<section class="hero">
  <h1>Stories</h1>
  <p class="muted">All published pieces.</p>
</section>

<section>
  <div class="grid">
    {% assign sorted = site.stories | sort: 'date' | reverse %}
    {% for story in sorted %}
    <article class="card">
      {% if story.cover %}
        <img class="thumb-img" src="{{ story.cover | relative_url }}" alt="{{ story.title }} cover" loading="lazy">
      {% else %}
        <div class="thumb" aria-hidden="true"></div>
      {% endif %}
      <div class="body">
        <h3><a href="{{ story.url | relative_url }}">{{ story.title }}</a></h3>
        <p class="muted">{{ story.date | date: "%Y-%m-%d" }}{% if story.length %} • {{ story.length }}{% endif %}</p>
        <div class="tags">
          {% for t in story.tags %}<span class="tag">{{ t }}</span>{% endfor %}
        </div>
        <p>{{ story.excerpt }}</p>
        <p><a class="btn" href="{{ story.url | relative_url }}">Read</a></p>
      </div>
    </article>
    {% endfor %}
  </div>
</section>
