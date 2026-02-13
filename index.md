---
layout: default
title: Home
---

{% include hero.html
  image="/assets/img/hero-bg.svg"
  pill="Greenhouse Horticulture and Plant Factory Lab"
  pill_ko="온실원예 및 식물공장 연구실"
  title="Integrating plant biology and environmental control"
  title_ko="식물생물학과 환경 제어의 융합"
  subtitle="For next-generation plant production systems."
  subtitle_ko="차세대 식물 생산 시스템을 위하여."
  primary_text="Meet the Lab"
  primary_text_ko="연구실 소개"
  primary_link="/team"
  secondary_text="Explore Research"
  secondary_text_ko="연구 분야"
  secondary_link="/research"
%}

{% include carousel.html %}

<section class="section" id="highlights">
  <div class="container">
    <div class="section__head">
      <h2><span class="i18n-en">Highlights</span><span class="i18n-ko">주요 연구</span></h2>
    </div>

    <div class="grid">
      <article class="card">
        <h3><span class="i18n-en">Plant Growth Optimization</span><span class="i18n-ko">식물 생장 최적화</span></h3>
        <p class="muted"><span class="i18n-en">Enhancing productivity through environmental regulation and physiological analysis.</span><span class="i18n-ko">환경 조절과 생리 분석을 통한 생산성 향상.</span></p>
        <a class="link" href="{{ '/research' | relative_url }}"><span class="i18n-en">Learn more →</span><span class="i18n-ko">자세히 보기 →</span></a>
      </article>

      <article class="card">
        <h3><span class="i18n-en">Smart Greenhouse Systems</span><span class="i18n-ko">스마트 온실 시스템</span></h3>
        <p class="muted"><span class="i18n-en">Integrating sensor data and environmental control for precision cultivation.</span><span class="i18n-ko">센서 데이터와 환경 제어를 통합한 정밀 재배.</span></p>
        <a class="link" href="{{ '/research' | relative_url }}"><span class="i18n-en">Explore →</span><span class="i18n-ko">탐색하기 →</span></a>
      </article>

      <article class="card">
        <h3><span class="i18n-en">Plant Factory Innovation</span><span class="i18n-ko">식물공장 혁신</span></h3>
        <p class="muted"><span class="i18n-en">Advancing sustainable and efficient plant production systems.</span><span class="i18n-ko">지속 가능하고 효율적인 식물 생산 시스템 발전.</span></p>
        <a class="link" href="{{ '/research' | relative_url }}"><span class="i18n-en">Discover →</span><span class="i18n-ko">알아보기 →</span></a>
      </article>
    </div>
  </div>
</section>

<section class="section news-section">
  <div class="container">
    <div class="section__head">
      <h2><span class="i18n-en">News</span><span class="i18n-ko">소식</span></h2>
    </div>

    <div class="news-list">
      {% for item in site.data.news %}
      <article class="news-item">
        <time class="news-item__date" datetime="{{ item.date }}">{{ item.date }}</time>
        <div class="news-item__body">
          <h3 class="news-item__title"><span class="i18n-en">{{ item.title }}</span><span class="i18n-ko">{{ item.title_ko | default: item.title }}</span></h3>
          <p class="news-item__summary muted"><span class="i18n-en">{{ item.summary }}</span><span class="i18n-ko">{{ item.summary_ko | default: item.summary }}</span></p>
        </div>
      </article>
      {% endfor %}
    </div>
  </div>
</section>
