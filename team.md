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


<section class="section">
  <div class="section__head">
    <h2>PhD / PhD Students</h2>
    <p class="muted small">All doctoral members</p>
  </div>

  <div class="grid">
    {% for p in site.data.team.phd %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
      </div>
    {% endfor %}

    {% for p in site.data.team.phd_students %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
      </div>
    {% endfor %}
  </div>
</section>


<section class="section">
  <div class="section__head">
    <h2>MS / Undergraduate</h2>
    <p class="muted small">Master’s students and undergraduate researchers</p>
  </div>

  <div class="grid">
    {% for p in site.data.team.ms_students %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
      </div>
    {% endfor %}

    {% for p in site.data.team.interns %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
      </div>
    {% endfor %}
  </div>
</section>

</div>
