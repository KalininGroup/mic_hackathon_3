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
    { id:"site-uos", name:"University of Sheffield", city:"Sheffield, United Kingdom", lat:53.381312, lon:-1.488437 },
    { id:"site-erc", name:"Ernst Ruska-Centre for Microscopy and Spectroscopy with Electrons", city:"Jülich, Germany", lat:50.908187, lon:6.413937 },
    { id:"site-ibec", name:"Institute for Bioengineering of Catalonia (IBEC)", city:"Barcelona, Spain", lat:41.382188, lon:2.118062 },
    { id:"site-dom-oxford", name:"Department of Materials, University of Oxford", city:"Oxford, United Kingdom", lat:51.760438, lon:-1.259187 },
    { id:"site-icn2",  name:"Institut Català de Nanociència i Nanotecnologia (ICN2)", city:"Barcelona, Spain", lat:41.4915, lon:2.1834 },
    { id:"site-ntnu",  name:"Norwegian University of Science and Technology (NTNU)", city:"Trondheim, Norway", lat:63.419438, lon:10.401937 },
    { id:"site-inm",  name:"Leibniz Institute for New Materials (INM)", city:"Saarbrücken, Germany", lat:49.256563, lon:7.040188 },
    { id:"site-uva",  name:"University of Virginia", city:"Charlottesville, VA, USA", lat:38.033563, lon:-78.507937 },
    { id:"site-jhu", name:"Johns Hopkins University", city:"Baltimore, MD, USA", lat:39.3299, lon:-76.6205},
    { id:"site-gatech", name:"Georgia Institute of Technology", city:"Atlanta, GA, USA", lat:33.777938, lon:-84.397937},
    { id:"site-chalmers", name:"Chalmers University of Technology", city:"Gothenburg, Sweden", lat:57.689312, lon:11.974063},
    { id:"site-psu",  name:"Pennsylvania State University", city:"State College, PA, USA", lat:40.7982, lon:-77.8599 },
    { id:"site-columbia",  name:"Columbia University", city:"New York, NY, USA", lat:40.807563, lon:-73.962563 },
    { id:"site-epfl",  name:"Swiss Federal Technology Institute of Lausanne (EPFL)", city:"Lausanne, Switzerland", lat:46.520562, lon:6.570063 },
    { id:"site-argonne",  name:"Argonne National Laboratory", city:"Lemont, IL, USA", lat:41.718312, lon:-87.979062 },
    { id:"site-nwu",   name:"Northwestern University", city:"Evanston, IL, USA",  lat:42.05598, lon:-87.67517 },
    { id:"site-tamu", name:"Texas A&M University", city:"College Station, TX, USA", lat:30.6150, lon:-96.3410},
    { id:"site-osu", name:"Oklahoma State University", city:"Stillwater, OK, USA", lat:36.1255, lon:-97.0720},
    { id:"site-ohio", name:"Ohio State University", city:"Columbus, OH, USA", lat:40.006062, lon:-83.028312},
    { id:"site-rice", name:"Rice University", city:"Houston, TX, USA", lat:29.716813, lon:-95.403562},
    { id:"site-uh", name:"University of Houston", city:"Houston, TX, USA", lat:29.720438, lon:-95.342938},
    { id:"site-iu-bloom", name:"Indiana University Bloomington", city:"Bloomington, IN, USA", lat:39.168188, lon:-86.523062},
    { id:"site-uarizona", name:"University of Arizona", city:"Tucson, AZ, USA", lat:32.231938, lon:-110.953563},
    { id:"site-mines", name:"Colorado School of Mines", city:"Golden, CO, USA", lat:39.7510, lon:-105.2226 },
    { id:"site-uta", name:"University of Texas at Arlington", city:"Arlington, TX, USA", lat:32.729188, lon:-97.115188 },
    { id:"site-cint", name:"Center for Integrated Nanotechnologies (CINT)", city:"Albuquerque, NM, USA", lat:35.060563,  lon:-106.534688 },
    { id:"site-ucolo", name:"University of Colorado", city:"Boulder, CO, USA", lat:40.0076, lon:-105.2659 },
    { id:"site-uwashington", name:"University of Washington", city:"Seattle, WA, USA", lat:47.656562, lon:-122.312687 },
    { id:"site-usc", name:"University of Southern California", city:"Los Angeles, CA, USA", lat:34.022312, lon:-118.285062 },
    { id:"site-ufl", name:"University of Florida", city:"Gainesville, FL, USA", lat:29.646563, lon:-82.353313 },
    { id:"site-caltech", name:"California Institute of Technology", city:"Pasadena, CA, USA", lat:34.137687, lon:-118.125313 },
    { id:"site-cnsi-sb", name:"California NanoSystems Institute, University of California", city:"Santa Barbara, CA, USA", lat:34.415563, lon:-119.840312 },
    { id:"site-yale", name:"Yale University", city:"New Haven, CT, USA", lat:41.316312, lon:-72.922313 },
    { id:"site-purdue", name:"Birck Nanotechnology Center, Purdue University", city:"West Lafayette, IN, USA", lat:40.422687, lon:-86.924563 },
    { id:"site-duke", name:"Duke University", city:"Durham, NC, USA", lat:36.001438, lon:-78.938187 },
    { id:"site-felmi-zfe", name:"Austrian Centre for Electron Microscopy and Nanoanalysis (FELMI-ZFE)", city:"Graz, Austria", lat:47.063938, lon:15.453312 },
    // { id:"site-ucl",  name:"University College London",   city:"London, United Kingdom", lat:51.524563, lon:-0.134063 },
  ];

  const map = L.map('worldmap', { scrollWheelZoom: false });
  L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
    subdomains: 'abcd',
    maxZoom: 19,
    minZoom: 2,
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
        Kanazawa, Japan • Building/Room: <em>Nano Life Science Institute, 4F Main Conference Room</em><br>
        Contact: Kazuki Miyata<br>
        <a href="mailto:k-miyata@staff.kanazawa-u.ac.jp">k-miyata@staff.kanazawa-u.ac.jp</a>
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
        Contact: Fumihiko Uesugi<br>
        <a href="mailto:uesugi23@iis.u-tokyo.ac.jp">uesugi23@iis.u-tokyo.ac.jp</a>
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
      <img class="site-logo" src="{{ '/assets/KAIST.png' | relative_url }}" alt="KAIST logo" style="max-height:64px;">
      <div class="site-meta">
        Daejeon, Republic of Korea • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
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
      <img class="site-logo" src="{{ '/assets/AISCIA.png' | relative_url }}" alt="AISCIA Informatics logo" style="max-height:64px;">
      <div class="site-meta">
        Qatar Science and Technology Park, Doha • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Qatar%20Science%20and%20Technology%20Park%20Doha" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=AISCIA%20Informatics%20-%20Doha,%20Qatar" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Sheffield -->
    <div class="site-card" id="site-uos">
      <span class="badge">United Kingdom</span>
      <h3>University of Sheffield</h3>
      <img class="site-logo" src="{{ '/assets/uos.svg' | relative_url }}" alt="University of Sheffield logo" style="max-height:64px;">
      <div class="site-meta">
        Sheffield, UK • Building/Room: <em><br>Dec 15: The Ideas Space, Sir Robert Hadfield Building<br>
        Dec 16-17: Mappin Hall, Sir Frederick Mappin Building</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Sheffield" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Sheffield%20-%20Sheffield,%20UK" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Ernst Ruska-Centre for Microscopy and Spectroscopy with Electrons - Jülich, Germany -->
    <div class="site-card" id="site-erc">
      <span class="badge">Germany</span>
      <h3>Ernst Ruska-Centre for Microscopy and Spectroscopy with Electrons</h3>
      <img class="site-logo" src="{{ '/assets/erc.png' | relative_url }}" alt="Ernst Ruska-Centre for Microscopy and Spectroscopy with Electrons logo" style="max-height:64px;">
      <div class="site-meta">
        Jülich, Germany • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Ernst%20Ruska-Centre" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Ernst%20Ruska-Centre%20for%20Microscopy%20and%20Spectroscopy%20with%20Electrons%20-%20Jülich,%20Germany" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Institute for Bioengineering of Catalonia (IBEC) - Barcelona, Spain -->
    <div class="site-card" id="site-ibec">
      <span class="badge">Spain</span>
      <h3>Institute for Bioengineering of Catalonia (IBEC)</h3>
      <img class="site-logo" src="{{ '/assets/ibec.png' | relative_url }}" alt="IBEC logo" style="max-height:64px;">
      <div class="site-meta">
        Barcelona, Spain • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=IBEC%20Spain" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Institute%20for%20Bioengineering%20of%20Catalonia%20(IBEC)%20-%20Barcelona,%20Spain" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Department of Materials, University of Oxford - Oxford, UK -->
    <div class="site-card" id="site-dom-oxford">
      <span class="badge">United Kingdom</span>
      <h3>Department of Materials, University of Oxford</h3>
      <img class="site-logo" src="{{ '/assets/dom-oxford.svg' | relative_url }}" alt="Department of Materials, University of Oxford logo" style="max-height:64px;">
      <div class="site-meta">
        Oxford, UK • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Department%20of%20Materials%20Parks%20Road" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Department%20of%20Materials,%20University%20of%20Oxford%20-%20Oxford,%20UK " class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Institut Català de Nanociència i Nanotecnologia (ICN2) - Barcelona, Spain -->
    <div class="site-card" id="site-icn2">
      <span class="badge">Spain</span>
      <h3>Institut Català de Nanociència i Nanotecnologia - ICN2</h3>
      <img class="site-logo" src="{{ '/assets/ICN2.png' | relative_url }}" alt="ICN2 logo" style="max-height:64px;">
      <div class="site-meta">
        Barcelona, Spain • Building/Room: <em>Campus UAB, ICN2</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=ICN2%20Barcelona" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Institut%20Catal%C3%A0%20de%20Nanoci%C3%A8ncia%20i%20Nanotecnologia%20(ICN2)%20-%20Barcelona,%20Spain" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Norwegian University of Science and Technology (NTNU) - Trondheim, Norway -->
    <div class="site-card" id="site-ntnu">
      <span class="badge">Norway</span>
      <h3>Norwegian University of Science and Technology (NTNU)</h3>
      <img class="site-logo" src="{{ '/assets/ntnu.svg' | relative_url }}" alt="NTNU logo" style="max-height:64px;">
      <div class="site-meta">
        Trondheim, Norway • Building/Room: <em>Natural Science building. Room TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Norwegian%20University%20of%20Science%20and%20Technology" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Norwegian%20University%20of%20Science%20and%20Technology%20(NTNU)%20-%20Trondheim,%20Norway" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Leibniz Institute for New Materials (INM) - Saarbrücken, Germany -->
    <div class="site-card" id="site-inm">
      <span class="badge">Germany</span>
      <h3>Leibniz Institute for New Materials (INM)</h3>
      <img class="site-logo" src="{{ '/assets/inm.png' | relative_url }}" alt="INM logo" style="max-height:64px;">
      <div class="site-meta">
        Saarbrücken, Germany • Building/Room: <em>Campus D2 2</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=INM%20Saarbrücken" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Leibniz%20Institute%20for%20New%20Materials%20(INM)%20-%20Saarbrücken,%20Germany" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Virginia -->
    <div class="site-card" id="site-uva">
      <span class="badge">Virginia, USA</span>
      <h3>University of Virginia</h3>
      <img class="site-logo" src="{{ '/assets/uva.svg' | relative_url }}" alt="University of Virginia logo" style="max-height:64px;">
      <div class="site-meta">
        Charlottesville, VA • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Virginia" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Virginia" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Johns Hopkins University -->
    <div class="site-card" id="site-jhu">
      <span class="badge">Maryland, USA</span>
      <h3>Johns Hopkins University</h3>
      <img class="site-logo" src="{{ '/assets/JHU.png' | relative_url }}" alt="Johns Hopkins University logo" style="max-height:64px;">
      <div class="site-meta">
        Baltimore, MD • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Johns%20Hopkins%20University%20Baltimore" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Johns%20Hopkins%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Georgia Institute of Technology -->
    <div class="site-card" id="site-gatech">
      <span class="badge">Georgia, USA</span>
      <h3>Georgia Institute of Technology</h3>
      <img class="site-logo" src="{{ '/assets/gatech.png' | relative_url }}" alt="Georgia Institute of Technology logo" style="max-height:64px;">
      <div class="site-meta">
        Atlanta, GA • Building/Room: <em>TBA</em><br>
        Contact: Mengkun Tian<br>
        <a href="mailto:mtian37@gatech.edu">mtian37@gatech.edu</a>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=gatech" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Georgia%20Institute%20of%20Technology" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Chalmers University of Technology - Gothenburg, Sweden -->
    <div class="site-card" id="site-chalmers">
      <span class="badge">Sweden</span>
      <h3>Chalmers University of Technology</h3>
      <img class="site-logo" src="{{ '/assets/chalmers.svg' | relative_url }}" alt="Chalmers University of Technology logo" style="max-height:64px;">
      <div class="site-meta">
        Chalmersplatsen, Gothenburg • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Chalmers%20Gothenburg" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Chalmers%20University%20of%20Technology%20-%20Gothenburg,%20Sweden" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Pennsylvania State University -->
    <div class="site-card" id="site-psu">
      <span class="badge">Pennsylvania, USA</span>
      <h3>Pennsylvania State University</h3>
      <img class="site-logo" src="{{ '/assets/PSU.png' | relative_url }}" alt="Pennsylvania State University logo" style="max-height:64px;">
      <div class="site-meta">
        State College, PA • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Pennsylvania%20State%20University%20State%20College" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Pennsylvania%20State%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Columbia University -->
    <div class="site-card" id="site-columbia">
      <span class="badge">New York, USA</span>
      <h3>Columbia University</h3>
      <img class="site-logo" src="{{ '/assets/columbia.svg' | relative_url }}" alt="Columbia University logo" style="max-height:64px;">
      <div class="site-meta">
        New York, NY • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Columbia%20University" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Columbia%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Swiss Federal Technology Institute of Lausanne (EPFL) - Lausanne, Switzerland -->
    <div class="site-card" id="site-epfl">
      <span class="badge">Switzerland</span>
      <h3>Swiss Federal Technology Institute of Lausanne (EPFL)</h3>
      <img class="site-logo" src="{{ '/assets/epfl.svg' | relative_url }}" alt="EPFL logo" style="max-height:64px;">
      <div class="site-meta">
        Lausanne, Switzerland • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=EPFL" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Swiss%20Federal%20Technology%20Institute%20of%20Lausanne%20(EPFL)%20-%20Lausanne,%20Switzerland" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Argonne National Laboratory -->
    <div class="site-card" id="site-argonne">
      <span class="badge">Illinois, USA</span>
      <h3>Argonne National Laboratory</h3>
      <img class="site-logo" src="{{ '/assets/argonne.svg' | relative_url }}" alt="Argonne National Laboratory logo" style="max-height:64px;">
      <div class="site-meta">
        Lemont, IL • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Argonne%20Laboratory" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Argonne%20National%20Laboratory" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Northwestern University -->
    <div class="site-card" id="site-nwu">
      <span class="badge">Illinois, USA</span>
      <h3>Northwestern University</h3>
      <img class="site-logo" src="{{ '/assets/northwestern.svg' | relative_url }}" alt="Northwestern logo" style="max-height:64px;">
      <div class="site-meta">
        Evanston, IL • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Northwestern%20University" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Northwestern%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Texas A&M University -->
    <div class="site-card" id="site-tamu">
      <span class="badge">Texas, USA</span>
      <h3>Texas A&M University</h3>
      <img class="site-logo" src="{{ '/assets/TAMU.png' | relative_url }}" alt="Texas A&M University logo" style="max-height:64px;">
      <div class="site-meta">
        College Station, TX • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Texas%20A%26M%20University%20College%20Station" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Texas%20A%26M%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Oklahoma State University -->
    <div class="site-card" id="site-osu">
      <span class="badge">Oklahoma, USA</span>
      <h3>Oklahoma State University</h3>
      <img class="site-logo" src="{{ '/assets/OSU.png' | relative_url }}" alt="Oklahoma State University logo" style="max-height:64px;">
      <div class="site-meta">
        Stillwater, OK • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Oklahoma%20State%20University%20Stillwater" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Oklahoma%20State%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Ohio State University -->
    <div class="site-card" id="site-ohio">
      <span class="badge">Ohio, USA</span>
      <h3>Ohio State University</h3>
      <img class="site-logo" src="{{ '/assets/ohio.svg' | relative_url }}" alt="Ohio State University logo" style="max-height:64px;">
      <div class="site-meta">
        Columbus, OH • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Ohio%20State%20University" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Ohio%20State%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Rice University -->
    <div class="site-card" id="site-rice">
      <span class="badge">Texas, USA</span>
      <h3>Rice University</h3>
      <img class="site-logo" src="{{ '/assets/rice.svg' | relative_url }}" alt="Rice University logo" style="max-height:64px;">
      <div class="site-meta">
        Houston, TX • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Rice%20University" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Rice%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Houston -->
    <div class="site-card" id="site-uh">
      <span class="badge">Texas, USA</span>
      <h3>University of Houston</h3>
      <img class="site-logo" src="{{ '/assets/UH.svg' | relative_url }}" alt="University of Houston logo" style="max-height:64px;">
      <div class="site-meta">
        Houston, TX • Building/Room: <em>TBA</em><br>
        Contact: Jacob Smith<br>
        <a href="mailto:jgsmith5@cougarnet.uh.edu">jgsmith5@cougarnet.uh.edu</a>        
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Houston" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Houston" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Indiana University Bloomington -->
    <div class="site-card" id="site-iu-bloom">
      <span class="badge">Indiana, USA</span>
      <h3>Indiana University Bloomington</h3>
      <img class="site-logo" src="{{ '/assets/IU.svg' | relative_url }}" alt="Indiana University Bloomington logo" style="max-height:64px;">
      <div class="site-meta">
        Bloomington, IN • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Indiana%20University%20Bloomington" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Indiana%20University%20Bloomington" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Arizona -->
    <div class="site-card" id="site-uarizona">
      <span class="badge">Arizona, USA</span>
      <h3>University of Arizona</h3>
      <img class="site-logo" src="{{ '/assets/uarizona.svg' | relative_url }}" alt="University of Arizona logo" style="max-height:64px;">
      <div class="site-meta">
        Tucson, AZ • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Arizona" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Arizona" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Colorado School of Mines -->
    <div class="site-card" id="site-mines">
      <span class="badge">Colorado, USA</span>
      <h3>Colorado School of Mines</h3>
      <img class="site-logo" src="{{ '/assets/Mines.png' | relative_url }}" alt="Colorado School of Mines logo" style="max-height:64px;">
      <div class="site-meta">
        Golden, CO • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Colorado%20School%20of%20Mines%20Golden" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Colorado%20School%20of%20Mines" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Texas at Arlington -->
    <div class="site-card" id="site-uta">
      <span class="badge">Texas, USA</span>
      <h3>University of Texas at Arlington</h3>
      <img class="site-logo" src="{{ '/assets/uta.svg' | relative_url }}" alt="University of Texas at Arlington logo" style="max-height:64px;">
      <div class="site-meta">
        Arlington, TX • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Texas%20Arlington" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Texas%20at%20Arlington" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Center for Integrated Nanotechnologies (CINT), Sandia National Laboratories -->
    <div class="site-card" id="site-cint">
      <span class="badge">New Mexico, USA</span>
      <h3>Center for Integrated Nanotechnologies (CINT)</h3>
      <img class="site-logo" src="{{ '/assets/cint.png' | relative_url }}" alt="Center for Integrated Nanotechnologies logo" style="max-height:64px;">
      <div class="site-meta">
        Albuquerque, NM • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=CINT%20SNL" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Center%20for%20Integrated%20Nanotechnologies%20(CINT)" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Colorado (Boulder) -->
    <div class="site-card" id="site-ucolo">
      <span class="badge">Colorado, USA</span>
      <h3>University of Colorado</h3>
      <img class="site-logo" src="{{ '/assets/UCB.png' | relative_url }}" alt="University of Colorado logo" style="max-height:64px;">
      <div class="site-meta">
        Boulder, CO • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Colorado%20Boulder" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Colorado" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Washington -->
    <div class="site-card" id="site-uwashington">
      <span class="badge">Washington, USA</span>
      <h3>University of Washington</h3>
      <img class="site-logo" src="{{ '/assets/uwashington.png' | relative_url }}" alt="University of Washington logo" style="max-height:64px;">
      <div class="site-meta">
        Seattle, WA • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Washington" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Washington" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Southern California -->
    <div class="site-card" id="site-usc">
      <span class="badge">California, USA</span>
      <h3>University of Southern California</h3>
      <img class="site-logo" src="{{ '/assets/usc.png' | relative_url }}" alt="University of Southern California logo" style="max-height:64px;">
      <div class="site-meta">
        Los Angeles, CA • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Southern%20California" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Southern%20California" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- University of Florida -->
    <div class="site-card" id="site-ufl">
      <span class="badge">Florida, USA</span>
      <h3>University of Florida</h3>
      <img class="site-logo" src="{{ '/assets/ufl.svg' | relative_url }}" alt="University of Florida logo" style="max-height:64px;">
      <div class="site-meta">
        Gainesville, FL • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=University%20of%20Florida" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=University%20of%20Florida" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- California Institute of Technology -->
    <div class="site-card" id="site-caltech">
      <span class="badge">California, USA</span>
      <h3>California Institute of Technology</h3>
      <img class="site-logo" src="{{ '/assets/caltech.png' | relative_url }}" alt="California Institute of Technology logo" style="max-height:64px;">
      <div class="site-meta">
        Pasadena, CA • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=California%20Institute%20of%20Technology" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=California%20Institute%20of%20Technology" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- California NanoSystems Institute, Santa Barbara -->
    <div class="site-card" id="site-cnsi-sb">
      <span class="badge">California, USA</span>
      <h3>California NanoSystems Institute, University of California</h3>
      <img class="site-logo" src="{{ '/assets/cnsi.png' | relative_url }}" alt="California NanoSystems Institute logo" style="max-height:64px;">
      <div class="site-meta">
        Santa Barbara, CA • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=California%20NanoSystems%20Institute%20Santa%20Barbara" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=California%20NanoSystems%20Institute,%20University%20of%20California,%20Santa%20Barbara" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Yale University -->
    <div class="site-card" id="site-yale">
      <span class="badge">Connecticut, USA</span>
      <h3>Yale University</h3>
      <img class="site-logo" src="{{ '/assets/yale.svg' | relative_url }}" alt="Yale University logo" style="max-height:64px;">
      <div class="site-meta">
        New Haven, CT • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Yale%20Universitya" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Yale%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Birck Nanotechnology Center, Purdue University -->
    <div class="site-card" id="site-purdue">
      <span class="badge">Indiana, USA</span>
      <h3>Birck Nanotechnology Center, Purdue University</h3>
      <img class="site-logo" src="{{ '/assets/purdue.svg' | relative_url }}" alt="Purdue University logo" style="max-height:64px;">
      <div class="site-meta">
        West Lafayette, IN • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Birck%20Nanotechnology%20Center" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Birck%20Nanotechnology%20Center,%20Purdue%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Duke University -->
    <div class="site-card" id="site-duke">
      <span class="badge">North Carolina, USA</span>
      <h3>Duke University</h3>
      <img class="site-logo" src="{{ '/assets/duke.svg' | relative_url }}" alt="Duke University logo" style="max-height:64px;">
      <div class="site-meta">
        Durham, NC • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=Duke%20University" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Duke%20University" class="btn-primary">Register</a>
      </div>
    </div>
    <!-- Austrian Centre for Electron Microscopy and Nanoanalysis (FELMI-ZFE) -->
    <div class="site-card" id="site-felmi-zfe">
      <span class="badge">Austria</span>
      <h3>Austrian Centre for Electron Microscopy and Nanoanalysis (FELMI-ZFE)</h3>
      <img class="site-logo" src="{{ '/assets/felmi-zfe.gif' | relative_url }}" alt="FELMI-ZFE logo" style="max-height:64px;">
      <div class="site-meta">
        Graz, Austria • Building/Room: <em>TBA</em><br>
        Contact: <em>TBA</em>
      </div>
      <div class="site-actions">
        <a href="https://maps.google.com/?q=FELMI-ZFE" target="_blank" rel="noopener">Map</a>
        <a href="{{ '/registration/' | relative_url }}?site=Austrian%20Centre%20for%20Electron%20Microscopy%20and%20Nanoanalysis%20(FELMI-ZFE)%20-%20Graz,%20Austria" class="btn-primary">Register</a>
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
