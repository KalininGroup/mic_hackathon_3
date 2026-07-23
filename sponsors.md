---
layout: page
title: Sponsorship
menu_title: Sponsors
menu_icon: handshake
permalink: /sponsors/
---

<style>
/* --- Sponsorship Page Styles --- */
.sponsor-intro {
  font-size: 1.1rem;
  line-height: 1.6;
  color: #334155;
  margin-bottom: 2rem;
}

.value-prop-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin-bottom: 3rem;
}

.value-card {
  background: #fafbfd;
  border: 1px solid #eef0f5;
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px rgba(0,0,0,0.03);
}

.value-card h3 {
  color: #1d2a56;
  margin-top: 0;
  font-size: 1.2rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.value-card p {
  margin-bottom: 0;
  font-size: 0.95rem;
  color: #475569;
}

/* --- Sponsor Logo Grid --- */
.sponsor-tier-title {
  text-align: center;
  margin: 3rem 0 1.5rem;
  color: #1d2a56;
  font-weight: 700;
}

.sponsor-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1.5rem;
  margin-bottom: 3rem;
}

.sponsor-logo-card {
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fff;
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  padding: 1.5rem;
  width: 260px;
  height: 120px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.sponsor-logo-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.08);
}

.sponsor-logo-card img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

/* --- Call to Action Banner --- */
.cta-banner {
  background: #eef2ff;
  border: 1px solid #c7d2fe;
  border-radius: 12px;
  padding: 2rem;
  text-align: center;
  margin-top: 2rem;
}

.cta-banner h3 {
  color: #1d4ed8;
  margin-top: 0;
  margin-bottom: 1rem;
}

.cta-banner p {
  margin-bottom: 1.5rem;
  color: #334155;
}

.btn-primary {
  display: inline-block;
  background: #3a7bd5;
  color: #fff;
  padding: 0.7rem 1.5rem;
  border-radius: 8px;
  font-weight: 600;
  text-decoration: none;
  transition: background 0.2s ease;
}

.btn-primary:hover {
  background: #2d55a9;
  color: #fff !important;
  text-decoration: none;
}
</style>

<p class="sponsor-intro">
  The Microscopy Hackathon is made possible through the generous support of our industry and institutional partners. Their contributions drive the future of materials science and autonomous microscopy by enabling open collaboration on a global scale.
</p>

<div class="value-prop-grid">
  <div class="value-card">
    <h3><i class="bi bi-rocket-takeoff"></i> For Innovation</h3>
    <p>Sponsorship directly fuels the development of open-source tools and AI-driven solutions, giving participants the resources they need to push the boundaries of digital twins and active learning.</p>
  </div>
  <div class="value-card">
    <h3><i class="bi bi-people"></i> For Community</h3>
    <p>By covering operational logistics and essential event infrastructure, sponsors ensure a seamless, high-quality hybrid experience for researchers joining us from all over the world.</p>
  </div>
  <div class="value-card">
    <h3><i class="bi bi-trophy"></i> For Excellence</h3>
    <p>Several of our partners go above and beyond by sponsoring specific challenges and awards, directly recognizing and rewarding the outstanding talent of our winning teams.</p>
  </div>
</div>

<p style="text-align: center; font-size: 1.05rem; color: #444; max-width: 800px; margin: 0 auto;">
  We are incredibly grateful to the following organizations for their support. Specific details regarding sponsor-backed challenges and the final prize structures will be announced closer to the event!
</p>

<h2 class="sponsor-tier-title">Our Generous Sponsors</h2>

<div class="sponsor-grid">
  <!-- Thermo Fisher -->
  <a href="https://www.thermofisher.com" class="sponsor-logo-card" target="_blank" rel="noopener" title="Thermo Fisher Scientific">
    <img src="{{ '/assets/tf_logo.svg' | relative_url }}" alt="Thermo Fisher Scientific Logo">
  </a>

  <!-- Renaissance Philanthropy -->
  <a href="https://www.renaissancephilanthropy.org/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Renaissance Philanthropy">
    <img src="{{ '/assets/renaissance.png' | relative_url }}" alt="Renaissance Philanthropy Logo">
  </a>

  <!-- Nanosurf -->
  <a href="https://www.nanosurf.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Nanosurf">
    <img src="{{ '/assets/nanosurf.svg' | relative_url }}" alt="Nanosurf Logo">
  </a>

  <!-- Zurich Instruments -->
  <a href="https://www.zhinst.com" class="sponsor-logo-card" target="_blank" rel="noopener" title="Zurich Instruments">
    <img src="{{ '/assets/zhinst.svg' | relative_url }}" alt="Zurich Instruments Logo">
  </a>
</div>

<div class="cta-banner">
  <h3>More sponsors to be announced soon!</h3>
  <p>We are continually welcoming new partners. This list will be updated regularly as new organizations join forces with us.</p>
  <p style="font-weight: 500;">Interested in becoming a sponsor? Contact Sergei Kalinin: <a href="mailto:sergei2@utk.edu">sergei2@utk.edu</a>.</p>
  
</div>