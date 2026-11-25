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
  margin: 2.5rem 0 1.25rem;
  color: #1d2a56;
  font-weight: 700;
}

.sponsor-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 2.5rem;
}

.sponsor-logo-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  background: #fff;
  border: 1px solid #e2e8f0;
  border-radius: 10px;
  padding: 12px 14px 10px;
  width: 210px;
  height: 120px;
  box-sizing: border-box;
  text-decoration: none;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.sponsor-logo-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.08);
  text-decoration: none;
}

.sponsor-logo-card img {
  margin: auto 0;
  max-width: 100%;
  max-height: 100%;
  min-height: 0;
  object-fit: contain;
}

.sponsor-site-tag {
  flex-shrink: 0;
  font-size: 0.7rem;
  font-weight: 600;
  color: #475569;
  background: #f1f5f9;
  border-radius: 999px;
  padding: 2px 8px;
  line-height: 1.2;
  white-space: nowrap;
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
  We are incredibly grateful to the following organizations for their support. <br>
  The prize list is available on the <a href="{{ '/awards/' | relative_url }}"><strong>Awards</strong></a> page.
</p>

<h2 class="sponsor-tier-title">Our Generous Sponsors</h2>

<div class="sponsor-grid">
  <!-- Renaissance Philanthropy -->
  <!-- <a href="https://www.renaissancephilanthropy.org/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Renaissance Philanthropy">
    <img src="{{ '/assets/renaissance.png' | relative_url }}" alt="Renaissance Philanthropy Logo">
  </a> -->

  <!-- Nanosurf -->
  <a href="https://www.nanosurf.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Nanosurf">
    <img src="{{ '/assets/nanosurf.svg' | relative_url }}" alt="Nanosurf Logo">
  </a>

  <!-- Zurich Instruments -->
  <a href="https://www.zhinst.com" class="sponsor-logo-card" target="_blank" rel="noopener" title="Zurich Instruments">
    <img src="{{ '/assets/zhinst.svg' | relative_url }}" alt="Zurich Instruments Logo">
  </a>

  <!-- Park Systems -->
  <a href="https://www.parksystems.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Zurich Instruments">
    <img src="{{ '/assets/parksystems.svg' | relative_url }}" alt="Park Systems Logo">
  </a>

  <!-- Waviks -->
  <a href="https://waviks.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Waviks">
    <img src="{{ '/assets/waviks.png' | relative_url }}" alt="Waviks Logo">
  </a>

  <!-- DENS solutions -->
  <a href="https://denssolutions.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="DENS solutions">
    <img src="{{ '/assets/DENS.png' | relative_url }}" alt="DENS solutions Logo">
  </a>

  <!-- DECTRIS -->
  <a href="https://www.dectris.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="DECTRIS">
    <img src="{{ '/assets/DECTRIS.png' | relative_url }}" alt="DECTRIS Logo">
  </a>

  <!-- Quantum Design -->
  <a href="https://qdusa.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Quantum Design">
    <img src="{{ '/assets/QD.svg' | relative_url }}" alt="Quantum Design Logo">
  </a>

  <!-- Oxford Instruments - Asylum Research -->
  <a href="https://afm.oxinst.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Oxford Instruments - Asylum Research">
    <img src="{{ '/assets/asylum.png' | relative_url }}" alt="Oxford Instruments - Asylum Research Logo">
  </a>

<!-- JEOL -->
  <a href="https://jeol.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="JEOL">
    <img src="{{ '/assets/Jeol.png' | relative_url }}" alt="JEOL">
  </a>

<!-- Anthropic -->
  <a href="https://www.anthropic.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Anthropic">
    <img src="{{ '/assets/Anthropic.svg' | relative_url }}" alt="Anthropic">
  </a>
      
<!-- Constructor Labs -->
  <a href="https://constructorlabs.org/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Constructor Labs">
    <img src="{{ '/assets/C-Labs.png' | relative_url }}" alt="Constructor Labs">
  </a>

<!-- Covalent Metrology -->
  <a href="https://covalentmetrology.com" class="sponsor-logo-card" target="_blank" rel="noopener" title="Covalent Metrology">
    <img src="{{ '/assets/covalent.png' | relative_url }}" alt="Covalent Metrology">
  </a>

<!-- Theia Scientific -->
  <a href="https://theiascientific.com" class="sponsor-logo-card" target="_blank" rel="noopener" title="Theia Scientific">
    <img src="{{ '/assets/TheiaScientific.png' | relative_url }}" alt="Theia Scientific">
  </a>

<!-- NTT DATA -->
  <a href="https://www.nttdata.com/en-us" class="sponsor-logo-card" target="_blank" rel="noopener" title="NTT DATA">
    <img src="{{ '/assets/nttdata.svg' | relative_url }}" alt="NTT DATA">
  </a>

<!-- MSA Student Council -->
  <a href="https://microscopy.org/the-student-council-stc/" class="sponsor-logo-card" target="_blank" rel="noopener" title="MSA Student Counci">
    <img src="{{ '/assets/msa_stc.png' | relative_url }}" alt="MSA Student Counci">
  </a>

<!-- COMMAT -->
  <a href="https://www.sciencedirect.com/journal/computational-materials-science" class="sponsor-logo-card" target="_blank" rel="noopener" title="Computational Material Science">
    <img src="{{ '/assets/commat.png' | relative_url }}" alt="Computational Material Science">    
    <span class="sponsor-site-tag">Toronto</span>
  </a>  
<!-- Hitachi -->
  <a href="https://www.hitachi-hightech.com/ca/en/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Hitachi High-Tech Canada Inc.">
    <img src="{{ '/assets/hitachi.png' | relative_url }}" alt="Hitachi High-Tech Canada Inc.">
    <span class="sponsor-site-tag">Toronto</span>
  </a>

<!-- Thermo Fisher -->
  <a href="https://www.thermofisher.com" class="sponsor-logo-card" target="_blank" rel="noopener" title="Thermo Fisher Scientific">
    <img src="{{ '/assets/tf_logo.svg' | relative_url }}" alt="Thermo Fisher Scientific Logo">
    <div style="display:flex; gap:6px; justify-content:center; flex-wrap:wrap;">
      <span class="sponsor-site-tag">Eindhoven</span>
      <span class="sponsor-site-tag">Tokyo</span>
    </div>
  </a>

<!-- Gatan Ametek -->
  <a href="https://www.gatan.com/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Gatan AMETEK">
    <img src="{{ '/assets/gatan.png' | relative_url }}" alt="Gatan AMETEK">    
    <span class="sponsor-site-tag">Tokyo</span>
  </a>

<!-- Euro Bioimaging -->
  <a href="https://www.eurobioimaging.eu/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Euro Bioimaging">
    <img src="{{ '/assets/EPFL_Eurobioimaging.png' | relative_url }}" alt="Euro Bioimaging">    
    <span class="sponsor-site-tag">Lausanne</span>
  </a>
<!-- Institute of Bioengineering (IBI) – EPFL -->
  <a href="https://www.epfl.ch/research/domains/bioengineering/" class="sponsor-logo-card" target="_blank" rel="noopener" title="Institute of Bioengineering (IBI) – EPFL">
    <img src="{{ '/assets/EPFL_BioEngineering.png' | relative_url }}" alt="Institute of Bioengineering (IBI) – EPFL">    
    <span class="sponsor-site-tag">Lausanne</span>
  </a>
<!-- EPFL AI center -->
  <a href="https://ai.epfl.ch/" class="sponsor-logo-card" target="_blank" rel="noopener" title="EPFL AI center">
    <img src="{{ '/assets/EPFL-AI-Center.svg' | relative_url }}" alt="EPFL AI center" style="max-height:35px;">    
    <span class="sponsor-site-tag">Lausanne</span>
  </a>
<!-- EPFL Center for Imaging -->
  <a href="https://imaging.epfl.ch/" class="sponsor-logo-card" target="_blank" rel="noopener" title="EPFL Center for Imaging">
    <img src="{{ '/assets/EPFL-Center-for-Imaging.svg' | relative_url }}" alt="EPFL Center for Imaging">    
    <span class="sponsor-site-tag">Lausanne</span>
  </a>
  
</div>

<div class="cta-banner">
  <h3>More sponsors to be announced soon!</h3>
  <p>We are continually welcoming new partners. This list will be updated regularly as new organizations join forces with us.</p>
  <p style="font-weight: 500;">Interested in becoming a sponsor? Contact Sergei Kalinin: <a href="mailto:sergei2@utk.edu">sergei2@utk.edu</a>.</p>
  
</div>