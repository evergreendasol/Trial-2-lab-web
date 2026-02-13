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
