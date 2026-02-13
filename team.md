---
layout: default
title: Team
---

{% assign faculty_count = site.data.team.faculty | size %}
{% assign postdoc_count = site.data.team.phd | size %}
{% assign phd_students_count = site.data.team.phd_students | size %}
{% assign ms_count = site.data.team.ms_students | size %}
{% assign ug_count = site.data.team.interns | size %}
{% assign alumni_count = site.data.team.alumni | size %}

<!-- ===== HERO + SUMMARY CARDS ===== -->
<section class="hero hero--photo hero--sub team-hero">
  <div class="container hero__inner">
    <p class="pill">GHPF Lab</p>
    <h1>Our Team</h1>
    <p class="lead">Members of the Greenhouse Horticulture & Plant Factory Lab</p>

    <div class="team-summary-grid team-summary-grid--hero">
      <a href="#professor" class="team-summary-card team-summary-card--hero" style="--card-accent:#0f766e">
        <span class="team-summary-card__icon">
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 24 24"><path d="M20 21v-2a4 4 0 00-4-4H8a4 4 0 00-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
        </span>
        <span class="team-summary-card__count">{{ faculty_count }}</span>
        <span class="team-summary-card__label">Professor</span>
      </a>
      <a href="#postdoc" class="team-summary-card team-summary-card--hero" style="--card-accent:#a16207">
        <span class="team-summary-card__icon">
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 24 24"><path d="M9 3H5a2 2 0 00-2 2v4m6-6h10a2 2 0 012 2v4M9 3v18m0 0h10a2 2 0 002-2V9M9 21H5a2 2 0 01-2-2V9m0 0h18"/></svg>
        </span>
        <span class="team-summary-card__count">{{ postdoc_count }}</span>
        <span class="team-summary-card__label">Postdoctoral</span>
      </a>
      <a href="#phd" class="team-summary-card team-summary-card--hero" style="--card-accent:#134e4a">
        <span class="team-summary-card__icon">
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 24 24"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c0 2 3 3 6 3s6-1 6-3v-5"/></svg>
        </span>
        <span class="team-summary-card__count">{{ phd_students_count }}</span>
        <span class="team-summary-card__label">Ph.D.</span>
      </a>
      <a href="#ms" class="team-summary-card team-summary-card--hero" style="--card-accent:#0d9488">
        <span class="team-summary-card__icon">
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 24 24"><path d="M4 19.5A2.5 2.5 0 016.5 17H20"/><path d="M6.5 2H20v20H6.5A2.5 2.5 0 014 19.5v-15A2.5 2.5 0 016.5 2z"/></svg>
        </span>
        <span class="team-summary-card__count">{{ ms_count }}</span>
        <span class="team-summary-card__label">Master's</span>
      </a>
      <a href="#ug" class="team-summary-card team-summary-card--hero" style="--card-accent:#78350f">
        <span class="team-summary-card__icon">
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 24 24"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87M16 3.13a4 4 0 010 7.75"/></svg>
        </span>
        <span class="team-summary-card__count">{{ ug_count }}</span>
        <span class="team-summary-card__label">Undergraduate</span>
      </a>
      <a href="#alumni" class="team-summary-card team-summary-card--hero" style="--card-accent:#64748b">
        <span class="team-summary-card__icon">
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        </span>
        <span class="team-summary-card__count">{{ alumni_count }}</span>
        <span class="team-summary-card__label">Alumni</span>
      </a>
    </div>
  </div>
</section>

<div class="container">

{% assign default_photo = '/assets/img/team/default.svg' | relative_url %}

<!-- Professor (from faculty) -->
<section class="section team-section" id="professor">
  <div class="section__head">
    <h2>Professor</h2>
  </div>

  <div class="grid team-grid">
    {% for p in site.data.team.faculty %}
      <div class="card team-card">
        <div class="team-card__photo">
          <img src="{{ p.photo | default: 'assets/img/team/default.svg' | relative_url }}" alt="{{ p.name }}" onerror="this.src='{{ default_photo }}'">
        </div>
        <div class="team-card__info">
          <h3>{{ p.name }}</h3>
          {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
          {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
</section>

<!-- Postdoctoral Researcher (from phd) -->
<section class="section team-section" id="postdoc">
  <div class="section__head">
    <h2>Postdoctoral Researcher</h2>
  </div>

  <div class="grid team-grid">
    {% for p in site.data.team.phd %}
      <div class="card team-card">
        <div class="team-card__photo">
          <img src="{{ p.photo | default: 'assets/img/team/default.svg' | relative_url }}" alt="{{ p.name }}" onerror="this.src='{{ default_photo }}'">
        </div>
        <div class="team-card__info">
          <h3>{{ p.name }}</h3>
          {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
          {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
</section>

<!-- Ph.D. Students -->
<section class="section team-section" id="phd">
  <div class="section__head">
    <h2>Ph.D. Students</h2>
  </div>

  <div class="grid team-grid">
    {% for p in site.data.team.phd_students %}
      <div class="card team-card">
        <div class="team-card__photo">
          <img src="{{ p.photo | default: 'assets/img/team/default.svg' | relative_url }}" alt="{{ p.name }}" onerror="this.src='{{ default_photo }}'">
        </div>
        <div class="team-card__info">
          <h3>{{ p.name }}</h3>
          {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
</section>

<!-- MS Students -->
<section class="section team-section" id="ms">
  <div class="section__head">
    <h2>MS Students</h2>
  </div>

  <div class="grid team-grid">
    {% for p in site.data.team.ms_students %}
      <div class="card team-card">
        <div class="team-card__photo">
          <img src="{{ p.photo | default: 'assets/img/team/default.svg' | relative_url }}" alt="{{ p.name }}" onerror="this.src='{{ default_photo }}'">
        </div>
        <div class="team-card__info">
          <h3>{{ p.name }}</h3>
          {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
</section>

<!-- Undergraduate (from interns) -->
<section class="section team-section" id="ug">
  <div class="section__head">
    <h2>Undergraduate</h2>
  </div>

  <div class="grid team-grid">
    {% for p in site.data.team.interns %}
      <div class="card team-card">
        <div class="team-card__photo">
          <img src="{{ p.photo | default: 'assets/img/team/default.svg' | relative_url }}" alt="{{ p.name }}" onerror="this.src='{{ default_photo }}'">
        </div>
        <div class="team-card__info">
          <h3>{{ p.name }}</h3>
          {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
</section>

<!-- Alumni -->
<section class="section team-section" id="alumni">
  <div class="section__head">
    <h2>Alumni</h2>
  </div>

  {% if site.data.team.alumni.size > 0 %}
  <div class="grid team-grid">
    {% for p in site.data.team.alumni %}
      <div class="card team-card">
        <div class="team-card__photo">
          <img src="{{ p.photo | default: 'assets/img/team/default.svg' | relative_url }}" alt="{{ p.name }}" onerror="this.src='{{ default_photo }}'">
        </div>
        <div class="team-card__info">
          <h3>{{ p.name }}</h3>
          {% if p.degree %}<p class="muted small">{{ p.degree }}</p>{% endif %}
          {% if p.year %}<p class="muted small">{{ p.year }}</p>{% endif %}
          {% if p.current %}<p class="small">{{ p.current }}</p>{% endif %}
          {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
  {% else %}
  <p class="muted">Alumni will be listed here.</p>
  {% endif %}
</section>

</div>
