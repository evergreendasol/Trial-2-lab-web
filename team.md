---
layout: default
title: Team
---

<div class="container">

# Team

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
        {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
      </div>
    {% endfor %}

    {% for p in site.data.team.phd_students %}
      <div class="card">
        <h3>{{ p.name }}</h3>
        {% if p.role %}<p class="muted small">{{ p.role }}</p>{% endif %}
        {% if p.email %}<p class="small"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
        {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
      </div>
    {% endfor %}
  </div>
</section>

</div>
