---
layout: default
title: Publications
---

<div class="container">

<section class="section">
  <div class="section__head">
    <h1 class="page-title"><span class="i18n-en">Publications</span><span class="i18n-ko">논문</span></h1>
    <p class="muted small"><span class="i18n-en">Selected publications and research outputs</span><span class="i18n-ko">주요 논문 및 연구 성과</span></p>
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
      {% if pub.tags.size > 0 %}
      <div class="pub-card__tags">
        {% for tag in pub.tags %}<span class="badge">{{ tag }}</span>{% endfor %}
      </div>
      {% endif %}
      <p class="pub-card__authors">{{ pub.authors }}</p>
      <p class="pub-card__venue">{{ pub.venue }}</p>
      {% if pub.url and pub.url != "" %}
        <p class="pub-card__link">
          <a class="link" href="{{ pub.url }}"><span class="i18n-en">View Paper</span><span class="i18n-ko">논문 보기</span> &rarr;</a>
        </p>
      {% endif %}
    </div>

{% endfor %}

{% if current_year != "" %}
  </div>
</section>
{% endif %}

</div>
