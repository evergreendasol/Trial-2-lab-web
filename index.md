---
layout: default
title: Home
---

{% include hero.html
  image="/assets/img/hero-bg.svg"
  pill="Greenhouse Horticulture and Plant Factory Lab"
  title="Integrating plant biology and environmental control"
  subtitle="For next-generation plant production systems."
  primary_text="Meet the Lab"
  primary_link="/team"
  secondary_text="Explore Research"
  secondary_link="/research"
%}

{% include carousel.html %}

<section class="section" id="main-content">
  <div class="container">
    <div class="section__head">
      <h2>Highlights</h2>
    </div>

    <div class="grid">
      <article class="card">
        <h3>Plant Growth Optimization</h3>
        <p class="muted">Enhancing productivity through environmental regulation and physiological analysis.</p>
        <a class="link" href="{{ '/research' | relative_url }}">Learn more →</a>
      </article>

      <article class="card">
        <h3>Smart Greenhouse Systems</h3>
        <p class="muted">Integrating sensor data and environmental control for precision cultivation.</p>
        <a class="link" href="{{ '/research' | relative_url }}">Explore →</a>
      </article>

      <article class="card">
        <h3>Plant Factory Innovation</h3>
        <p class="muted">Advancing sustainable and efficient plant production systems.</p>
        <a class="link" href="{{ '/research' | relative_url }}">Discover →</a>
      </article>
    </div>
  </div>
</section>
