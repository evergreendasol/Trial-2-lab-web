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
  <nav class="gallery-pagination" aria-label="Gallery pages"></nav>
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

  const grid = document.querySelector('.gallery-grid');
  const pager = document.querySelector('.gallery-pagination');
  const cards = Array.from(document.querySelectorAll('.gallery-card'));

  const perPage = 6;
  const totalPages = Math.max(1, Math.ceil(cards.length / perPage));

  function showPage(page) {
    const start = (page - 1) * perPage;
    const end = start + perPage;
    cards.forEach((c, i) => c.style.display = (i >= start && i < end) ? '' : 'none');
    renderPager(page);
  }

  function renderPager(cur) {
    if (!pager || totalPages <= 1) return;
    pager.innerHTML = '';

    const prev = btn('Prev', cur <= 1);
    prev.addEventListener('click', () => go(cur - 1));
    pager.appendChild(prev);

    for (let p = 1; p <= totalPages; p++) {
      const b = btn(String(p), false);
      if (p === cur) b.classList.add('gallery-pagination__active');
      b.addEventListener('click', () => go(p));
      pager.appendChild(b);
    }

    const next = btn('Next', cur >= totalPages);
    next.addEventListener('click', () => go(cur + 1));
    pager.appendChild(next);
  }

  function btn(text, disabled) {
    const b = document.createElement('button');
    b.type = 'button';
    b.className = 'btn btn--ghost';
    b.textContent = text;
    b.disabled = disabled;
    return b;
  }

  function go(page) {
    const safe = Math.min(Math.max(page, 1), totalPages);
    showPage(safe);
    grid?.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }

  // Modal
  document.querySelectorAll('.gallery-btn').forEach(b => {
    b.addEventListener('click', () => {
      gmImg.src = b.dataset.src;
      gmImg.alt = b.dataset.title || 'Gallery image';
      gmTitle.textContent = b.dataset.title || '';
      gmCaption.textContent = b.dataset.caption || '';
      modal.showModal();
    });
  });
  gmClose.addEventListener('click', () => modal.close());
  modal.addEventListener('click', (e) => { if (e.target === modal) modal.close(); });

  // Init
  showPage(1);
})();
</script>
