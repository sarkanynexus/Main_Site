---
layout: default
title: "Home"
---
<section class="hero">
  <h1>Hi, I’m Sándor.<br/>I write stories and design board games.</h1>
  <p>Jekyll + Markdown + Decap CMS starter. Add stories from /admin.</p>
  <div style="margin-top:16px; display:flex; gap:12px; flex-wrap:wrap">
    <a class="btn" href="{{ '/stories/' | relative_url }}">Read stories</a>
  </div>
</section>

<section>
  <h2>Latest Stories</h2>
  <div class="grid">
  {% assign latest = site.stories | sort: 'date' | reverse | slice: 0, 3 %}
  {% for story in latest %}
    <article class="card">
      <div class="thumb" role="img" aria-label="Cover"></div>
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
