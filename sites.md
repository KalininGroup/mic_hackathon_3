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

.notice-box {
  background: #fff4e6; 
  border-left: 5px solid #ff8200; 
  padding: 1.25rem 1.5rem;
  margin: 1.5rem 0;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.05);
}
.notice-box h3 {
  color: #ff8200;
  margin-top: 0;
  margin-bottom: 0.5rem;
  font-size: 1.3rem;
  display: flex;
  align-items: center;
  gap: 8px;
}
.notice-box p {
  margin: 0;
  font-size: 0.95rem;
  color: #444;
}
</style>

<div class="notice-box">
  <h3><i class="bi bi-geo-alt"></i> More Locations Coming Soon!</h3>
  <p>Our list of co-hosting universities is continually expanding. We encourage you to register Online or at your nearest available site <strong>today</strong> to get early access to our Slack and Miro workspaces. Joining early gives you a head start on meeting collaborators and forming your team! If a new physical location opens closer to you before the event, you will be able to easily switch your registration before the deadline.</p>
</div>

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
    { id:"site-ncsu",  name:"North Carolina State University (NCSU)",   city:"Raleigh, NC, USA",   lat:35.7847,  lon:-78.6821 },
    { id:"site-mpi-fkf",  name:"Max Planck Institute for Solid State Research",   city:"Stuttgart, Germany",   lat:48.746562,  lon:9.082313 },
    { id:"site-skku",  name:"School of Advanced Materials Science and Engineering, Sungkyunkwan University",   city:"Seoul, South Korea",   lat:37.294688,  lon:126.976812 },
    { id:"site-hu-berlin",  name:"Department of Physics, Humboldt University of Berlin",   city:"Berlin, Germany",   lat:52.432812,  lon:13.529687 },
    { id:"site-manchester-uni",  name:"The University of Manchester",   city:"Manchester, UK",   lat:53.465688,  lon:-2.232687 },
    { id:"site-kanazawa-uni",  name:"Kanazawa University",   city:"Kanazawa, Japan",   lat:36.545938,  lon:136.707562 },
    { id:"site-tu-darmstadt",  name:"Technical University of Darmstadt",   city:"Darmstadt, German",   lat:49.874813,  lon:8.656313 },
    { id:"site-leeds-uni",  name:"University of Leeds",   city:"Leeds, United Kingdom",   lat:53.807938,  lon:-1.553313 },
    { id:"site-tcd",  name:"Trinity College Dublin",   city:"Dublin, Ireland",   lat:53.343812,  lon:-6.254563 },
    { id:"site-tcd",  name:"Ulster University",   city:"Belfast, UK",   lat:54.604687,  lon:-5.929063 },
    { id:"site-iis",  name:"Institute of Industrial Science",   city:"The University of Tokyo, Japan",   lat:35.661938,  lon:139.678187 },
    { id:"site-icmab",  name:"Institute of Materials Science of Barcelona (ICMAB-CSIC)",   city:"Barcelona, Spain",   lat:41.502063,  lon:2.110313 },
    { id:"site-kaist", name:"Korea Advanced Institute of Science & Technology (KAIST), Republic of Korea", city:"Daejeon, Republic of Korea", lat:36.3723, lon:127.3622},
    { id:"site-aiscia", name:"AISCIA Informatics – Doha, Qatar", city:"Qatar Science and Technology Park, Doha", lat:25.325, lon:51.435 },
    // { id:"site-ucl",  name:"University College London",   city:"London, UK",   lat:51.524563,  lon:-0.134063 },
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
      <h3>University of Tennessee, Knoxville</h3>
      <img class="site-logo" src="{{ '/assets/utk.svg' | relative_url }}" alt="UTK logo" style="max-height:64px;">
      <div class="site-meta">
        Knoxville, TN • Building/Room: <em>IAMM 147</em><br>
        Contact: Alla Slautina<br>
        <a href="mailto:aslautin@utk.edu">aslautin@utk.edu</a>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University+of+Tennessee+Knoxville" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Tennessee,%20Knoxville" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- IIT -->
    <div class="site-card" id="site-iit">
      <span class="badge">Italy</span>
      <h3>Italian Institute of Technology</h3>
      <img class="site-logo" src="{{ '/assets/IIT.png' | relative_url }}" alt="IIT logo" style="max-height:64px;">
      <div class="site-meta">
        Genoa, Italy • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Istituto%20Italiano%20di%20Tecnologia%20Center%20for%20Convergent%20Technologies" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Italian%20Institute%20of%20Technology%20-%20Genoa,%20Italy" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- NCSU -->
    <div class="site-card" id="site-ncsu">
      <span class="badge">North Carolina, USA</span>
      <h3>North Carolina State University</h3>
      <img class="site-logo" src="{{ '/assets/ncsu.png' | relative_url }}" alt="NCSU logo" style="max-height:64px;">
      <div class="site-meta">
        Raleigh, NC • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=North%20Carolina%20State%20University" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=North%20Carolina%20State%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- MPI-FKF -->
    <div class="site-card" id="site-mpi-fkf">
      <span class="badge">Germany</span>
      <h3>Max Planck Institute for Solid State Research</h3>
      <img class="site-logo" src="{{ '/assets/mpi-fkf.png' | relative_url }}" alt="MPI-FKF logo" style="max-height:64px;">
      <div class="site-meta">
        Stuttgart, Germany • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Max%20Planck%20Institute%20for%20Solid%20State%20Research" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Max%20Planck%20Institute%20for%20Solid%20State%20Research%20-%20Stuttgart,%20Germany" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- SKKU -->
    <div class="site-card" id="site-skku">
      <span class="badge">Republic of Korea</span>
      <h3>School of Advanced Materials Science and Engineering, Sungkyunkwan University</h3>
      <img class="site-logo" src="{{ '/assets/SKKU.jpg' | relative_url }}" alt="SKKU logo" style="max-height:64px;">
      <div class="site-meta">
        Suwon, Republic of Korea • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=School%20of%20Advanced%20Materials%20Science%20and%20Engineering%20SKKU" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Sungkyunkwan%20University%20-%20Suwon,%20Republic%20of%20Korea" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Humboldt Uni -->
    <div class="site-card" id="site-hu-berlin">
      <span class="badge">Germany</span>
      <h3>Department of Physics, Humboldt University of Berlin</h3>
      <img class="site-logo" src="{{ '/assets/hu-berlin.svg' | relative_url }}" alt="Humboldt University logo" style="max-height:64px;">
      <div class="site-meta">
        Berlin, Germany • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Institut%20für%20Physik%20der%20Humboldt-Universität%20Berlin" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Humboldt%20University%20of%20Berlin%20-%20Berlin,%20Germany" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Manchester Uni -->
    <div class="site-card" id="site-manchester-uni">
      <span class="badge">United Kingdom</span>
      <h3>The University of Manchester</h3>
      <img class="site-logo" src="{{ '/assets/manchester-uni.png' | relative_url }}" alt="Manchester University logo" style="max-height:64px;">
      <div class="site-meta">
        Manchester, UK • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=The%20University%20of%20Manchester" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=The%20University%20of%20Manchester%20-%20Manchester,%20UK" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Kanazawa Uni -->
    <div class="site-card" id="site-kanazawa-uni">
      <span class="badge">Japan</span>
      <h3>Kanazawa University</h3>
      <img class="site-logo" src="{{ '/assets/kanazawa_uni.png' | relative_url }}" alt="Kanazawa University logo" style="max-height:64px;">
      <div class="site-meta">
        Kanazawa, Japan • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Kanazawa%20University" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Kanazawa%20University%20-%20Kanazawa,%20Japan" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Technical Uni Darmstadt -->
    <div class="site-card" id="site-tu-darmstadt">
      <span class="badge">Germany</span>
      <h3>Technical University of Darmstadt</h3>
      <img class="site-logo" src="{{ '/assets/tu-darmstadt.svg' | relative_url }}" alt="TU Darmstadt logo" style="max-height:64px;">
      <div class="site-meta">
        Darmstadt, Germany • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Technical%20University%20of%20Darmstadt" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Technical%20University%20of%20Darmstadt%20-%20Darmstadt,%20Germany" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Leeds -->
    <div class="site-card" id="site-leeds-uni">
      <span class="badge">United Kingdom</span>
      <h3>University of Leeds</h3>
      <img class="site-logo" src="{{ '/assets/leeds.svg' | relative_url }}" alt="Leeds University logo" style="max-height:64px;">
      <div class="site-meta">
        Leeds, United Kingdom • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Leeds" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Leeds%20-%20Leeds,%20UK" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Trinity College Dublin-->
    <div class="site-card" id="site-tcd">
      <span class="badge">Ireland</span>
      <h3>Trinity College Dublin</h3>
      <img class="site-logo" src="{{ '/assets/tcd.png' | relative_url }}" alt="Trinity College Dublin logo" style="max-height:64px;">
      <div class="site-meta">
        Dublin, Ireland • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Trinity%20College%20Dublin" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Trinity%20College%20Dublin%20-%20Dublin,%20Ireland" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Ulster Uni-->
    <div class="site-card" id="site-ulster">
      <span class="badge">United Kingdom</span>
      <h3>Ulster University</h3>
      <img class="site-logo" src="{{ '/assets/ulster.svg' | relative_url }}" alt="Ulster University logo" style="max-height:64px;">
      <div class="site-meta">
        Belfast, UK • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Ulster%20University%20Belfast" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Ulster%20University%20-%20Belfast,%20UK" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Institute of Industrial Science, The University of Tokyo, Japan -->
    <div class="site-card" id="site-iis">
      <span class="badge">Japan</span>
      <h3>Institute of Industrial Science</h3>
      <img class="site-logo" src="{{ '/assets/iis.png' | relative_url }}" alt="Institute of Industrial Science logo" style="max-height:64px;">
      <div class="site-meta">
        The University of Tokyo, Japan • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Institute%20of%20Industrial%20Science%20Tokyo" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Institute%20of%20Industrial%20Science,%20The%20University%20of%20Tokyo%20-%20Japan" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- ICMAB-->
    <div class="site-card" id="site-icmab">
      <span class="badge">Spain</span>
      <h3>Institute of Materials Science of Barcelona (ICMAB-CSIC)</h3>
      <img class="site-logo" src="{{ '/assets/icmab.png' | relative_url }}" alt="ICMAB-CSIC logo" style="max-height:64px;">
      <div class="site-meta">
        Barcelona, Spain • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=ICMAB%20Barcelona" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Institute%20of%20Materials%20Science%20of%20Barcelona%20-%20Barcelona,%20Spain" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Korea Advanced Institute of Science & Technology (KAIST), Daejeon -->
    <div class="site-card" id="site-kaist">
      <span class="badge">Republic of Korea</span>
      <h3>Korea Advanced Institute of Science & Technology (KAIST), Republic of Korea</h3>
      <img class="site-logo" src="{{ '/assets/KAIST.png' | relative_url }}" alt="KAIST logo">
      <div class="site-meta">
        Daejeon, Republic of Korea • Building/Room: <em>TBD</em><br>
        Contact: <em>TBD</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=KAIST%20Daejeon" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Korea%20Advanced%20Institute%20of%20Science%20%26%20Technology%20(KAIST)%20-%20Republic%20of%20Korea" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- AISCIA Informatics - Doha -->
    <div class="site-card" id="site-aiscia">
      <span class="badge">Qatar</span>
      <h3>AISCIA Informatics</h3>
      <img class="site-logo" src="{{ '/assets/AISCIA.png' | relative_url }}" alt="AISCIA Informatics logo">
      <div class="site-meta">
        Qatar Science and Technology Park, Doha • Building/Room: <em>TBD</em><br>
        Contact: <em>TBD</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Qatar%20Science%20and%20Technology%20Park%20Doha" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=AISCIA%20Informatics%20-%20Doha,%20Qatar" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University College London-->
    <!-- <div class="site-card" id="site-ucl">
      <span class="badge">United Kingdom</span>
      <h3>University College London</h3>
      <img class="site-logo" src="{{ '/assets/ucl.svg' | relative_url }}" alt="University College London logo" style="max-height:64px;">
      <div class="site-meta">
        London, UK • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20College%20London" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20College%20London%20-%20London,%20UK" class="btn-primary">Register</a>
      </div>
    </div> -->
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
