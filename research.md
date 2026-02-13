---
layout: default
title: Research
---

<div class="container">

<section class="section">
  <div class="section__head">
    <h1 class="page-title">Research</h1>
    <p class="muted small">Our research areas and focus topics</p>
  </div>
</section>

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
