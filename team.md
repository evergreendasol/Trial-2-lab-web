---
layout: default
title: Team
---

<div class="container">

# Team

<section class="team-section">
  <div class="section__head">
    <h2>Faculty</h2>
    <p class="muted small">Principal investigators & faculty members</p>
  </div>

  <div class="grid team-grid">
  {% for p in site.data.team.faculty %}
    <div class="card team-card">
      <div class="person person--compact">
        <div class="avatar">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% else %}
            <span class="avatar__txt">TEMP</span>
          {% endif %}
        </div>

        <div class="person__meta">
          <div class="person__top">
            <h3 class="person__name">{{ p.name }}</h3>
            {% if p.role %}<span class="badge person__role">{{ p.role }}</span>{% endif %}
          </div>

          <div class="person__sub">
            {% if p.email %}<a class="link small" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}
            {% if p.note %}<span class="muted small"> · {{ p.note }}</span>{% endif %}
          </div>
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
    <div class="card team-card">
      <div class="person person--compact">
        <div class="avatar">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% else %}
            <span class="avatar__txt">TEMP</span>
          {% endif %}
        </div>

        <div class="person__meta">
          <div class="person__top">
            <h3 class="person__name">{{ p.name }}</h3>
            {% if p.role %}<span class="badge person__role">{{ p.role }}</span>{% endif %}
          </div>

          <div class="person__sub">
            {% if p.email %}<a class="link small" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}
            {% if p.note %}<span class="muted small"> · {{ p.note }}</span>{% endif %}
          </div>
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
    <div class="card team-card">
      <div class="person person--compact">
        <div class="avatar">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% else %}
            <span class="avatar__txt">TEMP</span>
          {% endif %}
        </div>

        <div class="person__meta">
          <div class="person__top">
            <h3 class="person__name">{{ p.name }}</h3>
            {% if p.role %}<span class="badge person__role">{{ p.role }}</span>{% endif %}
          </div>

          <div class="person__sub">
            {% if p.email %}<a class="link small" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}
            {% if p.note %}<span class="muted small"> · {{ p.note }}</span>{% endif %}
          </div>
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
    <div class="card team-card">
      <div class="person person--compact">
        <div class="avatar">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% else %}
            <span class="avatar__txt">TEMP</span>
          {% endif %}
        </div>

        <div class="person__meta">
          <div class="person__top">
            <h3 class="person__name">{{ p.name }}</h3>
            {% if p.role %}<span class="badge person__role">{{ p.role }}</span>{% endif %}
          </div>

          <div class="person__sub">
            {% if p.email %}<a class="link small" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}
            {% if p.note %}<span class="muted small"> · {{ p.note }}</span>{% endif %}
          </div>
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
    <div class="card team-card">
      <div class="person person--compact">
        <div class="avatar">
          {% if p.photo %}
            <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
          {% else %}
            <span class="avatar__txt">TEMP</span>
          {% endif %}
        </div>

        <div class="person__meta">
          <div class="person__top">
            <h3 class="person__name">{{ p.name }}</h3>
            {% if p.role %}<span class="badge person__role">{{ p.role }}</span>{% endif %}
          </div>

          <div class="person__sub">
            {% if p.email %}<a class="link small" href="mailto:{{ p.email }}">{{ p.email }}</a>{% endif %}
            {% if p.note %}<span class="muted small"> · {{ p.note }}</span>{% endif %}
          </div>
        </div>
      </div>
    </div>
  {% endfor %}
  </div>
</section>

</div>
