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


<!-- Professor (기존 faculty 배열) -->
<section class="section">
  <div class="section__head">
    <h2>Professor</h2>
  </div>

  <div class="grid">
    {% for p in site.data.team.faculty %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
        {% if p.email %}
          <p class="small">
            <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>
          </p>
        {% endif %}
      </div>
    {% endfor %}
  </div>
</section>


<!-- Postdoctoral Researcher (기존 phd 배열) -->
<section class="section">
  <div class="section__head">
    <h2>Postdoctoral Researcher</h2>
  </div>

  <div class="grid">
    {% for p in site.data.team.phd %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
        {% if p.email %}
          <p class="small">
            <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>
          </p>
        {% endif %}
      </div>
    {% endfor %}
  </div>
</section>


<!-- PhD Students -->
<section class="section">
  <div class="section__head">
    <h2>PhD Students</h2>
  </div>

  <div class="grid">
    {% for p in site.data.team.phd_students %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.email %}
          <p class="small">
            <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>
          </p>
        {% endif %}
      </div>
    {% endfor %}
  </div>
</section>


<!-- MS Students -->
<section class="section">
  <div class="section__head">
    <h2>MS Students</h2>
  </div>

  <div class="grid">
    {% for p in site.data.team.ms_students %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.email %}
          <p class="small">
            <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>
          </p>
        {% endif %}
      </div>
    {% endfor %}
  </div>
</section>


<!-- Undergraduate -->
<section class="section">
  <div class="section__head">
    <h2>Undergraduate</h2>
  </div>

  <div class="grid">
    {% for p in site.data.team.interns %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.email %}
          <p class="small">
            <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>
          </p>
        {% endif %}
      </div>
    {% endfor %}
  </div>
</section>

</div>
