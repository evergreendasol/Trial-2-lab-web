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

{% assign faculty_count = site.data.team.faculty | size %}
{% assign postdoc_count = site.data.team.phd | size %}
{% assign phd_students_count = site.data.team.phd_students | size %}
{% assign ms_count = site.data.team.ms_students | size %}
{% assign ug_count = site.data.team.interns | size %}

<!-- Summary -->
<section class="section">
  <div class="grid">
    <a href="#professor" class="card team-summary-card">
      <h3>Professor</h3>
      <p class="muted">{{ faculty_count }} member(s)</p>
    </a>

    <a href="#postdoc" class="card team-summary-card">
      <h3>Postdoctoral Researcher</h3>
      <p class="muted">{{ postdoc_count }} member(s)</p>
    </a>

    <a href="#phd" class="card team-summary-card">
      <h3>Ph.D. Students</h3>
      <p class="muted">{{ phd_students_count }} member(s)</p>
    </a>

    <a href="#ms" class="card team-summary-card">
      <h3>MS Students</h3>
      <p class="muted">{{ ms_count }} member(s)</p>
    </a>

    <a href="#ug" class="card team-summary-card">
      <h3>Undergraduate</h3>
      <p class="muted">{{ ug_count }} member(s)</p>
    </a>
  </div>
</section>

<!-- Professor (from faculty) -->
<section class="section team-section" id="professor">
  <div class="section__head">
    <h2>Professor</h2>
  </div>

  <div class="grid team-grid">
    {% for p in site.data.team.faculty %}
      <div class="card team-card">
        <h3>{{ p.name }}</h3>
        {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
        {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
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
        <h3>{{ p.name }}</h3>
        {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
        {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
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
        <h3>{{ p.name }}</h3>
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
        {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
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
        <h3>{{ p.name }}</h3>
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
        {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
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
        <h3>{{ p.name }}</h3>
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
        {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
      </div>
    {% endfor %}
  </div>
</section>

</div>
