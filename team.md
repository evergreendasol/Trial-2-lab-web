---
layout: default
title: Team
---

# Team

## Faculty
<div class="grid">
{% for p in site.data.team.faculty %}
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


## PhD
<div class="grid">
{% for p in site.data.team.phd %}
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


## PhD Students
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


## MS Students
<div class="grid">
{% for p in site.data.team.ms_students %}
  <div class="card">
    <h3>{{ p.name }}</h3>
    {% if p.email %}
      <p class="small">
        <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>
      </p>
    {% endif %}
    {% if p.note %}
      <p class="muted small">{{ p.note }}</p>
    {% endif %}
  </div>
{% endfor %}
</div>


## Interns
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

