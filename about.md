---
layout: page
title: About the Hackathon
menu_title: About
menu_icon: info-circle
permalink: /about/
published: true
---

<style>
.section-card {
  background: #fafbfd;
  border: 1px solid #e8ecf3;
  border-radius: 14px;
  padding: 26px 24px;
  margin: 32px 0;
  box-shadow: 0 1px 2px rgba(16, 24, 40, .04);
}

.section-card h2 {
  font-size: 1.3rem;
  color: #1d2a56;
  margin-top: 0;
  margin-bottom: 10px;
  font-weight: 600;
  border-left: 4px solid #b4c8ff;
  padding-left: 10px;
}

.grid-2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 14px;
}

@media (max-width: 760px) {
  .grid-2 { grid-template-columns: 1fr; }
}

.table-soft {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0 6px;
}

.table-soft th {
  text-align: left;
  font-weight: 700;
  font-size: .95rem;
  color: #344054;
  padding: 10px 12px;
}

.table-soft td {
  background: #fff;
  border: 1px solid #eef0f5;
  border-radius: 10px;
  padding: 12px;
}

/* --- small helpers --- */
.badge {
  display: inline-block;
  font-size: .8rem;
  padding: .2rem .5rem;
  border-radius: 999px;
  background: #eef2ff;
  color: #334155;
  border: 1px solid #c7d2fe;
}

.logo-row {
  display: flex;
  flex-wrap: wrap;
  gap: 10px 14px;
  align-items: center;
}

.logo-row img {
  max-height: 56px;
  width: auto;
  height: auto;
  object-fit: contain;
  background: #fff;
  padding: .25rem .4rem;
  border-radius: 10px;
  border: 1px solid #eef0f5;
}

/* --- Core Team cards --- */
.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 16px;
}

.team-card {
  display: flex;
  gap: 12px;
  align-items: flex-start;
  background: #fff;
  border: 1px solid #eef0f5;
  border-radius: 14px;
  padding: 14px;
}

.team-card img {
  width: 64px;
  height: 64px;
  border-radius: 12px;
  object-fit: cover;
  border: 1px solid #e8ecf3;
  background: #fff;
}

.team-meta .name {
  font-weight: 700;
  color: #1d2a56;
}

.team-meta .affil {
  font-size: .92rem;
  color: #64748b;
}

.team-meta .role {
  font-size: .92rem;
  color: #475569;
}

/* --- clean inline social icons beside names --- */
.socials {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  margin-left: 6px;
  margin-bottom: -2px;
}

.socials a {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  color: #1d4ed8;
  text-decoration: none;
  background: none;
  border: none;
  box-shadow: none;
  width: auto;
  height: auto;
  padding: 0;
  transition: color 0.2s ease;
}

.socials a:hover {
  color: #0f172a;
}

.socials svg {
  width: 17px;
  height: 17px;
  fill: currentColor;
  vertical-align: middle;
}
</style>


<div class="section-card">
  <h2>Our Mission</h2>
  <p>
    The <strong>Machine Learning for Microscopy Hackathon</strong> accelerates the use of AI in microscopy and materials research.
    By connecting microscopy and machine-learning communities, we foster collaboration, open science, and reproducible workflows
    for imaging, spectroscopy, and automated experimentation.
  </p>
</div>

<div class="section-card">
  <h2>Hackathon History</h2>
  <p>
    The <a href="https://kaliningroup.github.io/mic-hackathon/" target="_blank" rel="noopener">first edition</a> took place at the University of Tennessee, Knoxville, in <strong>2024</strong>, with 250+ registrants and 80+ active participants
    from around the world. 
  </p>
  <p>
    The <strong>2025</strong> edition marked a major milestone, evolving into a massive 3-day <em>multi-site hybrid event</em>. As highlighted in our <a href="https://kaliningroup.github.io/mic_hackathon_2/summary/" target="_blank" rel="noopener">2025 Event Summary</a>, it connected over 250 participants across 12+ global sites and generated more than 70 innovative projects, proving the power of real-time collaboration across worldwide research centers.
  </p>
  <p>
    Now, the upcoming <strong>2026</strong> edition aims to push these boundaries even further, bringing new challenges and expanding our global community of AI/ML and microscopy innovators.
  </p>
</div>

<div class="section-card">
  <h2>Core Organizing Team</h2>

  <div class="team-grid">
    <!-- Sergei -->
    <div class="team-card">
      <img src="{{ '/assets/svk.png' | relative_url }}" alt="Sergei V. Kalinin">
      <div class="team-meta">
        <div class="name">
          Sergei V. Kalinin
          <span class="socials">
            <!-- Website -->
            <a href="https://ae-spm.utk.edu/group-leader-pi/" target="_blank" rel="noopener" title="Website" aria-label="Website">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20Zm0 2c.9 0 2.4 2.1 3 6H9c.6-3.9 2.1-6 3-6ZM5.06 11a7.8 7.8 0 0 1 .16-1h3.01a20 20 0 0 0 0 2H5.22a7.8 7.8 0 0 1-.16-1Zm6.94 9c-.9 0-2.4-2.1-3-6h6c-.6 3.9-2.1 6-3 6Zm3.77-7a20 20 0 0 0 0-2h3.01c.21.98.21 2.02 0 3H15.77ZM7.2 7H4.9a8 8 0 0 1 3.4-2.6c-.43.82-.8 1.7-1.1 2.6Zm9.6 0c-.3-.9-.67-1.78-1.1-2.6A8 8 0 0 1 19.1 7h-2.3ZM7.2 17c.3.9.67 1.78 1.1 2.6A8 8 0 0 1 4.9 17h2.3Zm9.6 0h2.3a8 8 0 0 1-3.4 2.6c.43-.82.8-1.7 1.1-2.6Z"/></svg>
            </a>
            <!-- GitHub -->
            <a href="https://github.com/SergeiVKalinin" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
            <!-- Email -->
            <a href="mailto:sergei2@utk.edu" title="sergei2@utk.edu" aria-label="Email">
              <svg viewBox="0 0 24 24"><path fill="currentColor" id="Subtract" fill-rule="evenodd" clip-rule="evenodd" d="M7 2.75C5.38503 2.75 3.92465 3.15363 2.86466 4.1379C1.79462 5.13152 1.25 6.60705 1.25 8.5V15.5C1.25 17.393 1.79462 18.8685 2.86466 19.8621C3.92465 20.8464 5.38503 21.25 7 21.25H17C18.615 21.25 20.0754 20.8464 21.1353 19.8621C22.2054 18.8685 22.75 17.393 22.75 15.5V8.5C22.75 6.60705 22.2054 5.13152 21.1353 4.1379C20.0754 3.15363 18.615 2.75 17 2.75H7ZM19.2285 8.3623C19.5562 8.10904 19.6166 7.63802 19.3633 7.31026C19.1101 6.98249 18.6391 6.9221 18.3113 7.17537L12.7642 11.4616C12.3141 11.8095 11.6858 11.8095 11.2356 11.4616L5.6886 7.17537C5.36083 6.9221 4.88982 6.98249 4.63655 7.31026C4.38328 7.63802 4.44367 8.10904 4.77144 8.3623L10.3185 12.6486C11.3089 13.4138 12.691 13.4138 13.6814 12.6486L19.2285 8.3623Z"/></svg>              
            </a>
            <!-- LinkedIn -->
            <a href="https://www.linkedin.com/in/sergei-kalinin-5bb44b18/" target="_blank" rel="noopener" title="LinkeId" aria-label="LinkeId">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M18.72 3.99997H5.37C5.19793 3.99191 5.02595 4.01786 4.86392 4.07635C4.70189 4.13484 4.55299 4.22471 4.42573 4.34081C4.29848 4.45692 4.19537 4.59699 4.12232 4.75299C4.04927 4.909 4.0077 5.07788 4 5.24997V18.63C4.01008 18.9901 4.15766 19.3328 4.41243 19.5875C4.6672 19.8423 5.00984 19.9899 5.37 20H18.72C19.0701 19.9844 19.4002 19.8322 19.6395 19.5761C19.8788 19.32 20.0082 18.9804 20 18.63V5.24997C20.0029 5.08247 19.9715 4.91616 19.9078 4.76122C19.8441 4.60629 19.7494 4.466 19.6295 4.34895C19.5097 4.23191 19.3672 4.14059 19.2108 4.08058C19.0544 4.02057 18.8874 3.99314 18.72 3.99997ZM9 17.34H6.67V10.21H9V17.34ZM7.89 9.12997C7.72741 9.13564 7.5654 9.10762 7.41416 9.04768C7.26291 8.98774 7.12569 8.89717 7.01113 8.78166C6.89656 8.66615 6.80711 8.5282 6.74841 8.37647C6.6897 8.22474 6.66301 8.06251 6.67 7.89997C6.66281 7.73567 6.69004 7.57169 6.74995 7.41854C6.80986 7.26538 6.90112 7.12644 7.01787 7.01063C7.13463 6.89481 7.2743 6.80468 7.42793 6.74602C7.58157 6.68735 7.74577 6.66145 7.91 6.66997C8.07259 6.66431 8.2346 6.69232 8.38584 6.75226C8.53709 6.8122 8.67431 6.90277 8.78887 7.01828C8.90344 7.13379 8.99289 7.27174 9.05159 7.42347C9.1103 7.5752 9.13699 7.73743 9.13 7.89997C9.13719 8.06427 9.10996 8.22825 9.05005 8.3814C8.99014 8.53456 8.89888 8.6735 8.78213 8.78931C8.66537 8.90513 8.5257 8.99526 8.37207 9.05392C8.21843 9.11259 8.05423 9.13849 7.89 9.12997ZM17.34 17.34H15V13.44C15 12.51 14.67 11.87 13.84 11.87C13.5822 11.8722 13.3313 11.9541 13.1219 12.1045C12.9124 12.2549 12.7546 12.4664 12.67 12.71C12.605 12.8926 12.5778 13.0865 12.59 13.28V17.34H10.29V10.21H12.59V11.21C12.7945 10.8343 13.0988 10.5225 13.4694 10.3089C13.84 10.0954 14.2624 9.98848 14.69 9.99997C16.2 9.99997 17.34 11 17.34 13.13V17.34Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil">University of Tennessee, Knoxville</div>        
      </div>
    </div>
    <!-- Gerd -->
    <div class="team-card">
      <img src="{{ '/assets/GD.png' | relative_url }}" alt="Gerd Duscher">
      <div class="team-meta">
        <div class="name">
          Gerd Duscher
          <span class="socials">
            <a href="https://tickle.utk.edu/mse/faculty/gerd-duscher/" target="_blank" rel="noopener" title="Website" aria-label="Website">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20Zm0 2c.9 0 2.4 2.1 3 6H9c.6-3.9 2.1-6 3-6ZM5.06 11a7.8 7.8 0 0 1 .16-1h3.01a20 20 0 0 0 0 2H5.22a7.8 7.8 0 0 1-.16-1Zm6.94 9c-.9 0-2.4-2.1-3-6h6c-.6 3.9-2.1 6-3 6Zm3.77-7a20 20 0 0 0 0-2h3.01c.21.98.21 2.02 0 3H15.77ZM7.2 7H4.9a8 8 0 0 1 3.4-2.6c-.43.82-.8 1.7-1.1 2.6Zm9.6 0c-.3-.9-.67-1.78-1.1-2.6A8 8 0 0 1 19.1 7h-2.3ZM7.2 17c.3.9.67 1.78 1.1 2.6A8 8 0 0 1 4.9 17h2.3Zm9.6 0h2.3a8 8 0 0 1-3.4 2.6c.43-.82.8-1.7 1.1-2.6Z"/></svg>
            </a>
            <a href="https://github.com/gduscher" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil">University of Tennessee, Knoxville</div>        
      </div>
    </div>
    <!-- Rama -->
    <div class="team-card">
      <img src="{{ '/assets/rama.png' | relative_url }}" alt="Rama Vasudevan">
      <div class="team-meta">
        <div class="name">
          Rama Vasudevan
          <span class="socials">
            <a href="https://www.ornl.gov/staff-profile/rama-k-vasudevan" target="_blank" rel="noopener" title="Website" aria-label="Website">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20Zm0 2c.9 0 2.4 2.1 3 6H9c.6-3.9 2.1-6 3-6ZM5.06 11a7.8 7.8 0 0 1 .16-1h3.01a20 20 0 0 0 0 2H5.22a7.8 7.8 0 0 1-.16-1Zm6.94 9c-.9 0-2.4-2.1-3-6h6c-.6 3.9-2.1 6-3 6Zm3.77-7a20 20 0 0 0 0-2h3.01c.21.98.21 2.02 0 3H15.77ZM7.2 7H4.9a8 8 0 0 1 3.4-2.6c-.43.82-.8 1.7-1.1 2.6Zm9.6 0c-.3-.9-.67-1.78-1.1-2.6A8 8 0 0 1 19.1 7h-2.3ZM7.2 17c.3.9.67 1.78 1.1 2.6A8 8 0 0 1 4.9 17h2.3Zm9.6 0h2.3a8 8 0 0 1-3.4 2.6c.43-.82.8-1.7 1.1-2.6Z"/></svg>
            </a>
            <a href="https://github.com/ramav87" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil">CNMS, Oak Ridge National Laboratory</div>       
      </div>
    </div>    
    <!-- Yongtao -->
    <div class="team-card">
      <img src="{{ '/assets/Yliu.png' | relative_url }}" alt="Yongtao">
      <div class="team-meta">
        <div class="name">
          Yongtao Liu
          <span class="socials">
            <a href="https://www.ornl.gov/staff-profile/yongtao-liu" target="_blank" rel="noopener" title="Website" aria-label="Website">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20Zm0 2c.9 0 2.4 2.1 3 6H9c.6-3.9 2.1-6 3-6ZM5.06 11a7.8 7.8 0 0 1 .16-1h3.01a20 20 0 0 0 0 2H5.22a7.8 7.8 0 0 1-.16-1Zm6.94 9c-.9 0-2.4-2.1-3-6h6c-.6 3.9-2.1 6-3 6Zm3.77-7a20 20 0 0 0 0-2h3.01c.21.98.21 2.02 0 3H15.77ZM7.2 7H4.9a8 8 0 0 1 3.4-2.6c-.43.82-.8 1.7-1.1 2.6Zm9.6 0c-.3-.9-.67-1.78-1.1-2.6A8 8 0 0 1 19.1 7h-2.3ZM7.2 17c.3.9.67 1.78 1.1 2.6A8 8 0 0 1 4.9 17h2.3Zm9.6 0h2.3a8 8 0 0 1-3.4 2.6c.43-.82.8-1.7 1.1-2.6Z"/></svg>
            </a>
            <a href="https://github.com/yongtaoliu" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil">CNMS, Oak Ridge National Laboratory, TN</div>       
      </div>
    </div>
    <!-- Richard -->
    <div class="team-card">
      <img src="{{ '/assets/rliu.png' | relative_url }}" alt="Richard Liu">
      <div class="team-meta">
        <div class="name">
          Richard Liu
          <span class="socials">
            <a href="https://github.com/RichardLiuCoding" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil"> University of Tennessee, Knoxville</div>        
      </div>
    </div>
    <!-- Boris -->
    <div class="team-card">
      <img src="{{ '/assets/Boris.png' | relative_url }}" alt="Boris Slautin">
      <div class="team-meta">
        <div class="name">
          Boris Slautin
          <span class="socials">
            <a href="https://github.com/Slautin" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil"> University of Tennessee, Knoxville</div>        
      </div>
    </div>
    <!-- Austin -->
    <div class="team-card">
      <img src="{{ '/assets/Austin.png' | relative_url }}" alt="Austin Houston">
      <div class="team-meta">
        <div class="name">
          Austin Houston
          <span class="socials">
            <a href="https://github.com/AustinHouston" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil">University of Tennessee, Knoxville</div>       
      </div>
    </div>    
    <!-- Utkarsh -->
    <div class="team-card">
      <img src="{{ '/assets/up.png' | relative_url }}" alt="Utkarsh Pratiush">
      <div class="team-meta">
        <div class="name">
          Utkarsh Pratiush
          <span class="socials">
            <a href="https://utkarshp1161.github.io/UtkarshsAIInScience.github.io/" target="_blank" rel="noopener" title="Website" aria-label="Website">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20Zm0 2c.9 0 2.4 2.1 3 6H9c.6-3.9 2.1-6 3-6ZM5.06 11a7.8 7.8 0 0 1 .16-1h3.01a20 20 0 0 0 0 2H5.22a7.8 7.8 0 0 1-.16-1Zm6.94 9c-.9 0-2.4-2.1-3-6h6c-.6 3.9-2.1 6-3 6Zm3.77-7a20 20 0 0 0 0-2h3.01c.21.98.21 2.02 0 3H15.77ZM7.2 7H4.9a8 8 0 0 1 3.4-2.6c-.43.82-.8 1.7-1.1 2.6Zm9.6 0c-.3-.9-.67-1.78-1.1-2.6A8 8 0 0 1 19.1 7h-2.3ZM7.2 17c.3.9.67 1.78 1.1 2.6A8 8 0 0 1 4.9 17h2.3Zm9.6 0h2.3a8 8 0 0 1-3.4 2.6c.43-.82.8-1.7 1.1-2.6Z"/></svg>
            </a>
            <a href="https://github.com/utkarshp1161" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil">University of Tennessee, Knoxville</div>       
      </div>
    </div>
     <!-- Aditya -->
    <div class="team-card">
      <img src="{{ '/assets/Aditya.jpg' | relative_url }}" alt="Aditya Raghavan">
      <div class="team-meta">
        <div class="name">
          Aditya Raghavan
          <span class="socials">
            <a href="https://github.com/adityaraghavan98" target="_blank" rel="noopener" title="GitHub" aria-label="GitHub">
              <svg viewBox="0 0 24 24"><path fill="currentColor" d="M12 .5a11.5 11.5 0 0 0-3.64 22.41c.58.11.79-.25.79-.56v-2.02c-3.34.73-4.04-1.61-4.04-1.61-.53-1.35-1.29-1.71-1.29-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.77 2.73 1.26 3.39.96.1-.76.41-1.26.74-1.55-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.38 1.24-3.22-.13-.3-.54-1.52.12-3.17 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.66 1.65.25 2.87.12 3.17.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.62-5.47 5.92.42.36.79 1.07.79 2.16v3.2c0 .31.21.68.8.56A11.5 11.5 0 0 0 12 .5Z"/></svg>
            </a>
          </span>
        </div>
        <div class="affil">University of Tennessee, Knoxville</div>       
      </div>
    </div>

  </div>
</div>




<div class="section-card">
  <h2>How It Works</h2>
  <table class="table-soft">
    <thead><tr><th>Element</th><th>What to expect</th></tr></thead>
    <tbody>
      <tr><td>Teams</td><td>Interdisciplinary groups mixing microscopy and ML backgrounds; remote and on-site collaboration.</td></tr>
      <tr><td>Data & Tasks</td><td>Real microscopy datasets and challenges spanning imaging, spectroscopy, and automation.</td></tr>
      <tr><td>Mentorship</td><td>Guidance from domain experts and tool builders; cross-site office hours and Slack support.</td></tr>
      <tr><td>Outcomes</td><td>Working prototypes, analysis notebooks, and open-source contributions that persist post-event.</td></tr>
    </tbody>
  </table>
</div>

<div class="section-card">
  <h2>Partners &amp; Support</h2>

<p>
  The hackathon is supported by the <strong>AI Tennessee Initiative</strong> and the 
  <strong>Center for Advanced Materials &amp; Manufacturing (CAMM)</strong>, with participation from 
  <strong>University of Tennessee Knoxville, North Carolina State University, and Italian Institute of Technology (Genoa, Italy)<!-- , Northwestern University, 
  University of Illinois Chicago, ICN2-ALBA Synchrotron Barcelona, University of Toronto, University of Wisconsin–Madison, 
  University of Colorado Boulder, Colorado School of Mines, Indian Institute of Technology Delhi, 
  Thermo Fisher Scientific (Eindhoven), AISCIA Informatics (Doha, Qatar), Pennsylvania State University, 
  University of Pennsylvania, University of Michigan Ann Arbor, Sungkyunkwan University (SKKU), 
  Nanyang Technological University Singapore, and Texas A&M University --></strong>.
</p>


  <p><strong>Sponsors</strong></p>
  <p>
    Our primary sponsors provide critical support for enabling open, collaborative AI-driven microscopy:
  </p> 
  <div class="logo-row" style="margin-top:10px;">    
    <img src="{{ '/assets/tf_logo.svg' | relative_url }}"  style="max-height:64px;">
    <img src="{{ '/assets/renaissance.png' | relative_url }}"  style="max-height:64px;">
    <img src="{{ '/assets/nanosurf.svg' | relative_url }}"  style="max-height:64px;">
    <img src="{{ '/assets/zhinst.svg' | relative_url }}"  style="max-height:64px;">
  </div>
    <!-- <img src="{{ '/assets/ONR.png' | relative_url }}"  style="max-height:64px;">
    <img src="{{ '/assets/TheiaScientific.png' | relative_url }}"  style="max-height:64px;">
    <img src="{{ '/assets/DENS.png' | relative_url }}"  style="max-height:64px;">
    <img src="{{ '/assets/covalent.png' | relative_url }}"  style="max-height:64px;">
    <img src="{{ '/assets/waviks.png' | relative_url }}"  style="max-height:48px;">
    <img src="{{ '/assets/polaron.png' | relative_url }}"  style="max-height:48px;">
    <img src="{{ '/assets/TRI.png' | relative_url }}"  style="max-height:64px;">
    <img src="{{ '/assets/msa_stc.png' | relative_url }}"  style="max-height:64px;"> -->

  <p style="margin-top:20px;"><strong>Partners</strong></p>
  <p>
    Our partners empower open science and innovation in AI for materials research:
  </p>
  <p><i>To be decided</i></p>
  <!-- <div class="logo-row" style="margin-top:10px;">
    <img src="{{ '/assets/mat3ra_logo.png' | relative_url }}" alt="Mat3ra – Materials R&D Cloud logo">
    <img src="{{ '/assets/hf.png' | relative_url }}" alt="Hugging Face logo">
  </div> -->
</div>



<div class="section-card">
  <h2>Get Involved</h2>
  <div class="grid-2">
    <div>
      <strong>Join the Community</strong><br>
      Connect on Slack, meet collaborators, and find a team.<br>
      <i>The link to join Slack workspace will be published soon</i>
      <!-- <div style="margin-top:6px;"><a href="https://tiny.utk.edu/slack">Join the Slack workspace</a></div> -->
    </div>
    <div>
      <strong>Participate</strong><br>
      Register for the hackathon and choose your preferred site (or Online).
      <div style="margin-top:6px;"><a href="{{ '/registration/' | relative_url }}">Register</a></div>
    </div>
  </div>
</div>

<div class="section-card" style="text-align:center;">
  <em>We are building an open, collaborative future for AI-driven microscopy — join us.</em>
</div>
