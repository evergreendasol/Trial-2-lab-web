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
  // ===== Modal elements =====
  const modal = document.getElementById('galleryModal');
  const gmImg = document.getElementById('gmImg');
  const gmTitle = document.getElementById('gmTitle');
  const gmCaption = document.getElementById('gmCaption');
  const gmClose = document.getElementById('gmClose');

  // ===== Pagination elements =====
  const grid = document.querySelector('.gallery-grid');
  const pager = document.querySelector('.gallery-pagination');
  const cards = Array.from(document.querySelectorAll('.gallery-card'));

  const itemsPerPage = 9; // ✅ 한 페이지에 몇 개 보여줄지 (원하는 숫자로)
  const totalPages = Math.max(1, Math.ceil(cards.length / itemsPerPage));

  function getPageFromURL() {
    const params = new URLSearchParams(window.location.search);
    const p = parseInt(params.get('page') || '1', 10);
    return Number.isFinite(p) ? Math.min(Math.max(p, 1), totalPages) : 1;
  }

  function setPageToURL(page) {
    const url = new URL(window.location.href);
    url.searchParams.set('page', String(page));
    window.history.replaceState({}, '', url);
  }

  function renderPager(currentPage) {
    if (!pager) return;
    pager.innerHTML = '';

    // prev
    const prev = document.createElement('button');
    prev.type = 'button';
    prev.className = 'btn btn--ghost';
    prev.textContent = 'Prev';
    prev.disabled = currentPage <= 1;
    prev.addEventListener('click', () => goToPage(currentPage - 1));
    pager.appendChild(prev);

    // page numbers (너무 많아지면 적당히 줄여서 보여주기)
    const maxButtons = 7;
    let start = Math.max(1, currentPage - Math.floor(maxButtons / 2));
    let end = Math.min(totalPages, start + maxButtons - 1);
    start = Math.max(1, end - maxButtons + 1);

    for (let p = start; p <= end; p++) {
      const b = document.createElement('button');
      b.type = 'button';
      b.className = 'btn btn--ghost';
      b.textContent = String(p);
      b.setAttribute('aria-current', p === currentPage ? 'page' : 'false');
      if (p === currentPage) b.style.borderColor = 'rgba(52,231,211,.55)';
      b.addEventListener('click', () => goToPage(p));
      pager.appendChild(b);
    }

    // next
    const next = document.createElement('button');
    next.type = 'button';
    next.className = 'btn btn--ghost';
    next.textContent = 'Next';
    next.disabled = currentPage >= totalPages;
    next.addEventListener('click', () => goToPage(currentPage + 1));
    pager.appendChild(next);
  }

  function showPage(page) {
    const startIdx = (page - 1) * itemsPerPage;
    const endIdx = startIdx + itemsPerPage;

    cards.forEach((card, i) => {
      card.style.display = (i >= startIdx && i < endIdx) ? '' : 'none';
    });

    renderPager(page);
  }

  function goToPage(page) {
    const safe = Math.min(Math.max(page, 1), totalPages);
    setPageToURL(safe);
    showPage(safe);
    // 페이지 이동 시 상단으로 살짝 올리기(원치 않으면 제거)
    grid?.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }

  // ===== Modal binding (현재 페이지에서 보이는 카드도 동일하게 동작) =====
  function bindModalHandlers() {
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
  }

  // Init
  bindModalHandlers();
  const initialPage = getPageFromURL();
  showPage(initialPage);
})();
</script>
