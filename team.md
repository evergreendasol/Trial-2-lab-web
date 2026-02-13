---
layout: default
title: Team
---

<div class="container">

<section class="section">
  <div class="section__head">
    <h1 class="page-title">Team</h1>
    <p class="muted small">Members of the Greenhouse Horticulture & Plant Factory Lab</p>
  </div>
</section>

{% assign default_photo = '/assets/img/team/default.svg' | relative_url %}

<!-- Professor (from faculty) -->
<section class="section team-section" id="professor">
  <div class="section__head">
    <h2>Professor</h2>
  </div>

  {% for p in site.data.team.faculty %}
  <div class="prof-card">
    <div class="prof-card__photo">
      <img src="{{ p.photo | default: 'assets/img/team/default.svg' | relative_url }}" alt="{{ p.name }}" onerror="this.src='{{ default_photo }}'">
    </div>
    <div class="prof-card__body">
      <h3 class="prof-card__name">{{ p.name }}</h3>
      {% if p.role %}<p class="prof-card__role">{{ p.role }}</p>{% endif %}
      {% if p.email %}
      <p class="prof-card__email">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
        <a href="mailto:{{ p.email }}">{{ p.email }}</a>
      </p>
      {% endif %}

      {% if p.education.size > 0 %}
      <div class="prof-card__edu">
        <h4 class="prof-card__edu-title">Education</h4>
        <ul class="prof-card__edu-list">
          {% for e in p.education %}
          <li class="prof-card__edu-item">
            <svg class="prof-card__edu-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c0 1.1 2.7 3 6 3s6-1.9 6-3v-5"/></svg>
            <div>
              <span class="prof-card__edu-degree">{{ e.degree }}</span>
              <span class="prof-card__edu-field">{{ e.field }}</span>
              <span class="prof-card__edu-meta">{{ e.university }}, {{ e.year }}</span>
            </div>
          </li>
          {% endfor %}
        </ul>
      </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
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
