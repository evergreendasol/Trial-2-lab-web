---
layout: default
title: Research
---

<!-- ===== HERO BANNER + AREA CARDS ===== -->
<section class="hero hero--photo research-hero">
  <div class="container hero__inner">
    <p class="pill">GHPF Lab</p>
    <h1>Our Research</h1>
    <p class="lead">Advancing knowledge in controlled environment agriculture through integrated plant science, environmental engineering, and data-driven optimization.</p>

    <div class="research-grid">
      {% for area in site.data.research %}
      <a href="#{{ area.id }}" class="research-card research-card--hero" style="--card-accent:{{ area.color }}">
        <div class="research-card__icon">
          {% if area.icon == 'greenhouse' %}
          <svg width="36" height="36" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 48 48"><path d="M4 26L24 10l20 16"/><rect x="8" y="24" width="32" height="18" rx="2"/><line x1="24" y1="10" x2="24" y2="42"/><line x1="8" y1="33" x2="40" y2="33"/><ellipse cx="16" cy="38" rx="4" ry="4" fill="rgba(74,222,128,0.3)" stroke="none"/><ellipse cx="32" cy="38" rx="4" ry="4" fill="rgba(74,222,128,0.3)" stroke="none"/></svg>
          {% elsif area.icon == 'plant' %}
          <svg width="36" height="36" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 48 48"><path d="M24 44V24"/><path d="M24 32C24 24 16 20 10 20c0 8 8 12 14 12z" fill="rgba(74,222,128,0.2)"/><path d="M24 24C24 16 32 12 38 12c0 8-8 12-14 12z" fill="rgba(74,222,128,0.2)"/><path d="M24 18C24 12 20 8 16 6c-2 6 2 12 8 12z" fill="rgba(74,222,128,0.15)"/><circle cx="24" cy="44" r="3" fill="none"/></svg>
          {% elsif area.icon == 'sensor' %}
          <svg width="36" height="36" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 48 48"><rect x="18" y="28" width="12" height="14" rx="2"/><circle cx="24" cy="35" r="2"/><path d="M16 22a12 12 0 0116 0"/><path d="M12 17a17 17 0 0124 0"/><path d="M8 12a22 22 0 0132 0"/><line x1="24" y1="28" x2="24" y2="24"/></svg>
          {% elsif area.icon == 'data' %}
          <svg width="36" height="36" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 48 48"><rect x="6" y="6" width="36" height="36" rx="4"/><line x1="6" y1="16" x2="42" y2="16"/><polyline points="14,34 20,26 26,30 34,20"/><circle cx="14" cy="34" r="2" fill="currentColor"/><circle cx="20" cy="26" r="2" fill="currentColor"/><circle cx="26" cy="30" r="2" fill="currentColor"/><circle cx="34" cy="20" r="2" fill="currentColor"/></svg>
          {% endif %}
        </div>
        <h3 class="research-card__title">{{ area.title }}</h3>
        <p class="research-card__tagline">{{ area.tagline }}</p>
        <span class="research-card__arrow">&darr;</span>
      </a>
      {% endfor %}
    </div>
  </div>
</section>

<div class="container">

<!-- ===== DETAIL SECTIONS ===== -->
{% for area in site.data.research %}
<section class="section research-detail" id="{{ area.id }}" style="--card-accent:{{ area.color }}">
  <div class="research-detail__header">
    <div class="research-detail__icon">
      {% if area.icon == 'greenhouse' %}
      <svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 48 48"><path d="M4 26L24 10l20 16"/><rect x="8" y="24" width="32" height="18" rx="2"/><line x1="24" y1="10" x2="24" y2="42"/><line x1="8" y1="33" x2="40" y2="33"/></svg>
      {% elsif area.icon == 'plant' %}
      <svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 48 48"><path d="M24 44V24"/><path d="M24 32C24 24 16 20 10 20c0 8 8 12 14 12z"/><path d="M24 24C24 16 32 12 38 12c0 8-8 12-14 12z"/></svg>
      {% elsif area.icon == 'sensor' %}
      <svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 48 48"><rect x="18" y="28" width="12" height="14" rx="2"/><circle cx="24" cy="35" r="2"/><path d="M16 22a12 12 0 0116 0"/><path d="M12 17a17 17 0 0124 0"/><path d="M8 12a22 22 0 0132 0"/></svg>
      {% elsif area.icon == 'data' %}
      <svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 48 48"><rect x="6" y="6" width="36" height="36" rx="4"/><line x1="6" y1="16" x2="42" y2="16"/><polyline points="14,34 20,26 26,30 34,20"/></svg>
      {% endif %}
    </div>
    <h2 class="research-detail__title">{{ area.title }}</h2>
  </div>
  <p class="research-detail__desc">{{ area.description }}</p>
  <div class="research-detail__topics">
    {% for topic in area.topics %}
    <span class="badge research-badge">{{ topic }}</span>
    {% endfor %}
  </div>
</section>
{% endfor %}

</div>
