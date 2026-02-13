---
layout: default
title: Gallery
---

<div class="container">

<section class="section">
  <div class="section__head">
    <h1 class="page-title">Gallery</h1>
    <p class="muted small">Research scenes, facilities, and lab activities</p>
  </div>
</section>

<section class="section team-section">
  <div class="gallery-grid">
    {% for item in site.data.gallery %}
      <figure class="card gallery-card">
        <button class="gallery-btn" type="button"
          data-src="{{ item.src | relative_url }}"
          data-title="{{ item.title | escape }}"
          data-caption="{{ item.caption | escape }}"
          aria-label="Open image: {{ item.title | escape }}">
          <img class="gallery-img" src="{{ item.src | relative_url }}" alt="{{ item.title | escape }}" loading="lazy">
        </button>

        <figcaption class="gallery-cap">
          <div class="person__top">
            <h3 class="gallery-title">{{ item.title }}</h3>
            {% if item.tag %}<span class="badge person__role">{{ item.tag }}</span>{% endif %}
          </div>
          {% if item.caption %}<p class="muted small gallery-sub">{{ item.caption }}</p>{% endif %}
        </figcaption>
      </figure>
    {% endfor %}
  </div>
</section>

</div>

<!-- Modal -->
<dialog class="gallery-modal" id="galleryModal">
  <div class="gallery-modal__inner card">
    <div class="gallery-modal__top">
      <div>
        <p class="pill" id="gmTag">Gallery</p>
        <h2 id="gmTitle" style="margin:0; font-size:22px;">Title</h2>
        <p class="muted small" id="gmCaption" style="margin:8px 0 0;">Caption</p>
      </div>
      <button class="btn btn--ghost" type="button" id="gmClose">Close</button>
    </div>

    <div class="gallery-modal__imgwrap">
      <img id="gmImg" alt="" src="" />
    </div>
  </div>
</dialog>

<script>
(() => {
  const modal = document.getElementById('galleryModal');
  const gmImg = document.getElementById('gmImg');
  const gmTitle = document.getElementById('gmTitle');
  const gmCaption = document.getElementById('gmCaption');
  const gmClose = document.getElementById('gmClose');

  document.querySelectorAll('.gallery-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      gmImg.src = btn.dataset.src;
      gmImg.alt = btn.dataset.title || 'Gallery image';
      gmTitle.textContent = btn.dataset.title || '';
      gmCaption.textContent = btn.dataset.caption || '';
      modal.showModal();
    });
  });

  gmClose.addEventListener('click', () => modal.close());
  modal.addEventListener('click', (e) => {
    if (e.target === modal) modal.close();
  });
})();
</script>
