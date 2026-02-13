---
layout: default
title: Team
---

# Team

<section class="team-section">
  <div class="section__head">
    <h2>Faculty</h2>
    <p class="muted small">Principal investigators & faculty members</p>
  </div>

  <div class="grid team-grid">
  {% for p in site.data.team.faculty %}
    <div class="card">
      <div class="person">
        <div class="person__photo">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% endif %}
        </div>

        <div class="person__meta">
          <h3>{{ p.name }}</h3>
          {% if p.role %}<p class="person__role">{{ p.role }}</p>{% endif %}
          {% if p.email %}
            <p class="person__email"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>
          {% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
  </div>
</section>


<section class="team-section">
  <div class="section__head">
    <h2>PhD</h2>
    <p class="muted small">Doctoral researchers</p>
  </div>

  <div class="grid team-grid">
  {% for p in site.data.team.phd %}
    <div class="card">
      <div class="person">
        <div class="person__photo">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% endif %}
        </div>

        <div class="person__meta">
          <h3>{{ p.name }}</h3>
          {% if p.role %}<p class="person__role">{{ p.role }}</p>{% endif %}
          {% if p.email %}
            <p class="person__email"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>
          {% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
  </div>
</section>


<section class="team-section">
  <div class="section__head">
    <h2>PhD Students</h2>
    <p class="muted small">PhD candidates & students</p>
  </div>

  <div class="grid team-grid">
  {% for p in site.data.team.phd_students %}
    <div class="card">
      <div class="person">
        <div class="person__photo">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% endif %}
        </div>

        <div class="person__meta">
          <h3>{{ p.name }}</h3>
          {% if p.role %}<p class="person__role">{{ p.role }}</p>{% endif %}
          {% if p.email %}
            <p class="person__email"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>
          {% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
  </div>
</section>


<section class="team-section">
  <div class="section__head">
    <h2>MS Students</h2>
    <p class="muted small">Master’s students</p>
  </div>

  <div class="grid team-grid">
  {% for p in site.data.team.ms_students %}
    <div class="card">
      <div class="person">
        <div class="person__photo">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% endif %}
        </div>

        <div class="person__meta">
          <h3>{{ p.name }}</h3>
          {% if p.role %}<p class="person__role">{{ p.role }}</p>{% endif %}
          {% if p.email %}
            <p class="person__email"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>
          {% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
  </div>
</section>


<section class="team-section">
  <div class="section__head">
    <h2>Interns</h2>
    <p class="muted small">Interns and visiting students</p>
  </div>

  <div class="grid team-grid">
  {% for p in site.data.team.interns %}
    <div class="card">
      <div class="person">
        <div class="person__photo">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% endif %}
        </div>

        <div class="person__meta">
          <h3>{{ p.name }}</h3>
          {% if p.role %}<p class="person__role">{{ p.role }}</p>{% endif %}
          {% if p.email %}
            <p class="person__email"><a class="link" href="mailto:{{ p.email }}">{{ p.email }}</a></p>
          {% endif %}
          {% if p.note %}<p class="muted small">{{ p.note }}</p>{% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
  </div>
</section>

