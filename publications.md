---
layout: default
title: Publications
---

<div class="container">

<section class="section">
  <div class="section__head">
    <h1 class="page-title">Publications</h1>
    <p class="muted small">Selected publications and research outputs</p>
  </div>
</section>

{% assign pubs = site.data.publications | sort: "year" | reverse %}
{% assign current_year = "" %}

{% for pub in pubs %}
  {% if pub.year != current_year %}
    {% if current_year != "" %}
      </div>
    </section>
    {% endif %}

    <section class="section team-section">
      <div class="section__head">
        <h2>{{ pub.year }}</h2>
      </div>
      <div class="pub-grid">
    {% assign current_year = pub.year %}
  {% endif %}

    <div class="card pub-card">
      <h3 class="pub-card__title">{{ pub.title }}</h3>
      <p class="pub-card__authors">{{ pub.authors }}</p>
      <p class="pub-card__venue">{{ pub.venue }}</p>
      {% if pub.url and pub.url != "" %}
        <p class="pub-card__link">
          <a class="link" href="{{ pub.url }}">View Paper &rarr;</a>
        </p>
      {% endif %}
    </div>

{% endfor %}

{% if current_year != "" %}
  </div>
</section>
{% endif %}

</div>
