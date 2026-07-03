---
layout: page
title: Sites
menu_title: Sites
menu_icon: geo-alt
permalink: /sites/
published: true
---

<style>
  #worldmap { height: 520px; border-radius: 14px; border:1px solid #e6e6e6; margin: 1rem 0 1.5rem; }
  .leaflet-popup-content { margin: 8px 10px; }
  .leaflet-popup-content h4 { margin: 0 0 .25rem; font-size: 1rem; }
  .leaflet-popup-content p { margin: 0; font-size: .92rem; color:#444; }
  /* Card logos + highlight */
  .site-card .site-logo{ display:block; max-height:44px; margin:.2rem 0 .6rem; object-fit:contain; }
  .site-card.highlight{ animation: sitePulse 1.8s ease 1; box-shadow: 0 10px 24px rgba(58,123,213,.25); }
  @keyframes sitePulse{
    0%{box-shadow:0 0 0 rgba(58,123,213,0)}
    30%{box-shadow:0 10px 28px rgba(58,123,213,.35)}
    100%{box-shadow:0 10px 24px rgba(58,123,213,.10)}
  }
</style>

<style>
.site-logo-row img {
  background:#fff;
  border-radius:10px;
  padding:2px;
  border:1px solid #e6e6e6;
}
</style>

<div id="worldmap"></div>

<!-- Leaflet (no key needed) -->
<link
  rel="stylesheet"
  href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
  integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY="
  crossorigin=""
/>
<script
  src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"
  integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo="
  crossorigin=""
></script>

{% raw %}
<script>
  // UTK orange pin
  const utkIcon = new L.Icon({
    iconUrl: "https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-orange.png",
    shadowUrl: "https://unpkg.com/leaflet@1.9.4/dist/images/marker-shadow.png",
    iconSize: [25,41], iconAnchor: [12,41], popupAnchor: [1,-34], shadowSize: [41,41]
  });

  // Site list for the map (ids MUST match the card ids below)
  const sites = [
    { id:"site-utk",  name:"University of Tennessee, Knoxville (UTK)", city:"Knoxville, TN, USA", lat:35.954,   lon:-83.929,  icon:utkIcon },
    { id:"site-iit",  name:"Italian Institute of Technology (IIT)",   city:"Genoa, Italy",   lat:44.4749,  lon:8.9062 },
  ];

  const map = L.map('worldmap', { scrollWheelZoom: false });
  L.tileLayer('https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}{r}.png', {
    attribution: '&copy; OpenStreetMap contributors, &copy; CARTO',
    subdomains: 'abcd',
    maxZoom: 19
  }).addTo(map);

  // Scroll to and highlight a card
  window.focusSite = function(id){
    const cards = document.querySelectorAll('.site-card');
    cards.forEach(c => c.classList.remove('expanded'));   // collapse any open one

    const el = document.getElementById(id);
    if(!el) return;

    el.classList.add('expanded');                         // expand this one
    el.scrollIntoView({ behavior:'smooth', block:'start' });

    // Optional: briefly pulse the border to draw the eye
    el.style.willChange = 'box-shadow, border-color';
    setTimeout(() => { el.style.willChange = 'auto'; }, 600);
  };
  // Add markers
  const markers = [];
  sites.forEach(s => {
    const m = L.marker([s.lat, s.lon], s.icon ? {icon:s.icon} : {}).addTo(map);
    m.bindPopup(`
      <h4>${s.name}</h4>
      <p>${s.city}</p>
      <p style="margin-top:.4rem"><a href="#" onclick="focusSite('${s.id}'); return false;">More details</a></p>
    `);
    markers.push(m);
  });

  // Fit bounds
  if (markers.length) {
    const group = L.featureGroup(markers);
    map.fitBounds(group.getBounds().pad(0.2));
  } else {
    map.setView([20, 0], 2);
  }

  window.addEventListener('resize', () => map.invalidateSize());
</script>
{% endraw %}

<p class="hint">Pick the site that’s closest to you (or choose <strong><a href="#" onclick="focusSite('site-online'); return false;" style="color: #3a7bd5; text-decoration: underline; cursor: pointer;">Online</a></strong>). Final room details and building access instructions will be emailed to registered participants.</p>

<style>
/* Sites page card styles */
.sites-wrap, .sites-wrap * { box-sizing: border-box; }
.sites-grid{ display:grid; gap:1rem; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); margin: 1rem 0 2rem; }
.site-card{ background:#fff; border:1px solid #e6e6e6; border-radius:14px; padding:1rem 1rem 1.1rem; box-shadow:0 6px 18px rgba(0,0,0,.05); }
.site-card h3{ margin:.2rem 0 .4rem; font-size:1.1rem; }
.site-meta{ color:#555; font-size:.95rem; margin:.3rem 0 .6rem; }
.site-actions a{ display:inline-block; padding:.5rem .75rem; border-radius:10px; margin-right:.4rem; margin-top:.3rem; text-decoration:none; font-weight:600; border:1px solid #d6d6d6; background:#fafafa; }
.site-actions a:hover{ border-color:#3a7bd5; box-shadow:0 4px 12px rgba(58,123,213,.18); }
.badge{ display:inline-block; font-size:.78rem; padding:.18rem .5rem; border-radius:999px; background:#eef2ff; color:#334155; border:1px solid #c7d2fe; }
.btn-primary{ display:inline-block; padding:.6rem 1rem; border-radius:10px; border:1px solid #2e6bd6; background:#3a7bd5; color:#fff; font-weight:700; text-decoration:none; }
.hint{ font-size:.95rem; color:#555; }
</style>

<style>
/* Fix: make Register buttons always look like buttons */
.site-actions .btn-primary,
.site-actions .btn-primary:link,
.site-actions .btn-primary:visited {
  background: #3a7bd5 !important;
  border-color: #2e6bd6 !important;
  color: #fff !important;
}

.site-actions .btn-primary:hover,
.site-actions .btn-primary:focus {
  background: #325fbf !important;
  color: #fff !important;
  text-decoration: none;
}

.site-actions .btn-primary:active {
  background: #2d55a9 !important;
  color: #fff !important;
}
</style>

<div class="sites-wrap">
  <div class="sites-grid">
    <!-- UTK -->
    <div class="site-card" id="site-utk">
      <span class="badge">Tennessee, USA</span>
      <h3>University of Tennessee, Knoxville (UTK)</h3>
      <img class="site-logo" src="{{ '/assets/UTK.jpg' | relative_url }}" alt="UTK logo">
      <div class="site-meta">
        Knoxville, TN • Building/Room: <em>TBA</em><br>
        Local lead: <a href="mailto:sergei2@utk.edu">sergei2@utk.edu</a>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University+of+Tennessee+Knoxville" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Tennessee,%20Knoxville" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- IIT -->
    <div class="site-card" id="site-iit">
      <span class="badge">Genoa, Italy</span>
      <h3>Italian Institute of Technology (IIT)</h3>
      <img class="site-logo" src="{{ '/assets/IIT.png' | relative_url }}" alt="IIT logo">
      <div class="site-meta">
        Genoa, Italy • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Istituto+Italiano+di+Tecnologia+Center+for+Convergent+Technologies" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Italian%20Institute%20of%20Technology%20-%20Genoa,%20Italy" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Online (no pin) -->
    <div class="site-card" id="site-online">
      <span class="badge">Global</span>
      <h3>Online</h3>
      <div class="site-meta">
        Participate remotely via Zoom + Slack<br>
        Access details will be emailed after registration.
      </div>
      <div class="site-actions">
        <a href="{{ '/registration/' | relative_url }}?site=Online" class="btn-primary">Register</a>
      </div>
    </div>

  </div>
</div>
<style>
/* allow grid items to re-pack when one expands */
.sites-grid{
  grid-auto-flow: dense;   /* let items fill gaps */
}
/* default card transitions */
.site-card{
  transition: box-shadow .2s ease, transform .2s ease, border-color .2s ease;
}
/* the expanded state */
.site-card.expanded{
  grid-column: span 2;                     /* take two columns */
  border-color: #3a7bd5;
  box-shadow: 0 12px 28px rgba(58,123,213,.22);
  transform: translateY(-2px);
}
/* optional: reveal extra content area only when expanded */
.site-card .site-more{ display:none; }
.site-card.expanded .site-more{ display:block; margin-top:.6rem; color:#333; }
/* on narrow screens, keep normal size */
@media (max-width: 720px){
  .site-card.expanded{ grid-column: span 1; transform:none; }
}
/* on very wide screens, let expanded cards take 2 columns */
@media (min-width: 1200px){
  .site-card.expanded { grid-column: span 2; }
}
</style>
