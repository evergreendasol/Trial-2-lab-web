---
layout: default
title: Team
---

# Team

## Faculty
<ul class="list">
{% for p in site.data.team.faculty %}
  <li><strong>{{ p.name }}</strong>{% if p.email %} — <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}</li>
{% endfor %}
</ul>

## PhD
<ul class="list">
{% for p in site.data.team.phd %}
  <li><strong>{{ p.name }}</strong>{% if p.email %} — <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}</li>
{% endfor %}
</ul>

## PhD Students
<ul class="list">
{% for p in site.data.team.phd_students %}
  <li><strong>{{ p.name }}</strong>{% if p.email %} — <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}</li>
{% endfor %}
</ul>

## MS Students
<ul class="list">
{% for p in site.data.team.ms_students %}
  <li><strong>{{ p.name }}</strong>
    {% if p.email %} — <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}
    {% if p.note %} <span class="muted small">({{ p.note }})</span>{% endif %}
  </li>
{% endfor %}
</ul>

## Interns
<ul class="list">
{% for p in site.data.team.interns %}
  <li><strong>{{ p.name }}</strong>{% if p.email %} — <a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}</li>
{% endfor %}
</ul>
