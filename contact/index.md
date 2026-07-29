---
layout: default
title: "Contact"
---
<section class="hero">
  <span class="hero-rule" aria-hidden="true"></span>
  <h1>Contact</h1>
  <p class="lede">Reach the nexus. Slow replies welcome; thoughtful ones preferred.</p>
</section>
<section class="box">
  <p>Email: <a href="mailto:info@sarkanynexus.com">info@sarkanynexus.com</a></p>
</section>
{% assign social_items = site.social | where_exp: "s", "s.url != nil and s.url != ''" %}
{% if social_items.size > 0 %}
<section class="section">
  <div class="section-head">
    <h2>Elsewhere</h2>
  </div>
  {% include social-icons.html size="lg" %}
</section>
{% endif %}
