---
layout: page
title: Live Event Updates
permalink: /event/
---
<style>
/* Thumbnail grid */
.photo-grid{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(220px,1fr));
  gap:14px;
  margin:16px 0 28px 0;
}

.photo-grid img{
  width:100%;
  height:150px;
  object-fit:cover;
  border-radius:10px;
  box-shadow:0 4px 10px rgba(0,0,0,0.12);
}

/* Make any image with this class clickable */
.lightboxable{ cursor:pointer; }

/* Lightbox modal */
.lb{
  position:fixed;
  inset:0;
  z-index:9999;
  display:none;
}
.lb.is-open{ display:block; }

.lb__backdrop{
  position:absolute;
  inset:0;
  background:rgba(0,0,0,0.70);
}

.lb__dialog{
  position:relative;
  max-width:min(950px,92vw);
  max-height:86vh;
  margin:6vh auto 0 auto;
  background:#fff;
  border-radius:14px;
  overflow:hidden;
  box-shadow:0 16px 50px rgba(0,0,0,0.35);
}

.lb__close{
  position:absolute;
  top:8px;
  right:12px;
  width:40px;
  height:40px;
  border:0;
  border-radius:20px;
  font-size:28px;
  line-height:40px;
  cursor:pointer;
  background:rgba(255,255,255,0.92);
}

.lb__img{
  display:block;
  width:100%;
  height:auto;
  max-height:78vh;
  object-fit:contain;
  background:#111;
}

.lb__cap{
  padding:10px 14px;
  font-size:14px;
  color:#444;
}


.clock-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  /* grid-template-columns: repeat(auto-fit, minmax(120px, 1fr)); */
  gap: 16px;
  margin: 24px 0;
}
.clock-card {
  background: #fafbfd;
  border: 1px solid #e8ecf3;
  border-radius: 12px;
  padding: 10px 6px;
  text-align: center;
  box-shadow: 0 1px 2px rgba(16,24,40,.04);
  min-width: 110px;
}
.clock-city {
  font-size: 0.85rem;
  font-weight: 600;
  color: #1d2a56;
  margin-bottom: 4px;
}
.clock-time {
  font-size: 1.1rem;
  font-weight: 700;
  color: #ff8200; 
  font-variant-numeric: tabular-nums;
}
.clock-date {
  font-size: 0.7rem;
  color: #666;
  margin-top: 4px;
}
</style>

<div class="clock-container">
  <!-- US Sites (West to East) -->
  <div class="clock-card">
    <div class="clock-city">Los Angeles (PST)</div>
    <div class="clock-time" id="time-la">--:--:--</div>
    <div class="clock-date" id="date-la">---</div>
  </div>
  
  <div class="clock-card">
    <div class="clock-city">Chicago (CST)</div>
    <div class="clock-time" id="time-chi">--:--:--</div>
    <div class="clock-date" id="date-chi">---</div>
  </div>

  <div class="clock-card">
    <div class="clock-city">Knoxville (EST)</div>
    <div class="clock-time" id="time-knox">--:--:--</div>
    <div class="clock-date" id="date-knox">---</div>
  </div>

  <!-- Europe / Middle East -->
  <div class="clock-card">
    <div class="clock-city">London (GMT)</div>
    <div class="clock-time" id="time-london">--:--:--</div>
    <div class="clock-date" id="date-london">---</div>
  </div>

  <div class="clock-card">
    <div class="clock-city">Berlin (CET)</div>
    <div class="clock-time" id="time-berlin">--:--:--</div>
    <div class="clock-date" id="date-berlin">---</div>
  </div>

  <div class="clock-card">
    <div class="clock-city">Doha (AST)</div>
    <div class="clock-time" id="time-doha">--:--:--</div>
    <div class="clock-date" id="date-doha">---</div>
  </div>

  <!-- Asia -->
  <div class="clock-card">
    <div class="clock-city">New Delhi (IST)</div>
    <div class="clock-time" id="time-delhi">--:--:--</div>
    <div class="clock-date" id="date-delhi">---</div>
  </div>

  <div class="clock-card">
    <div class="clock-city">Tokyo (JST)</div>
    <div class="clock-time" id="time-tokyo">--:--:--</div>
    <div class="clock-date" id="date-tokyo">---</div>
  </div>
</div>


## Hackathon 3 Participation Overview

Registration for the AI/ML Microscopy Hackathon 3 is now open.

Currently we received **815 registrations** in total, with participants joining from universities, national laboratories, and industry worldwide.

- **Online participation:** 315 registered participants  
- **Local site participation:** 500 participants across 77 host institutions

This page will share live snapshots from the ongoing hackathon, including online sessions and local site activities, and will continue to be updated throughout the event.

## Zoom Kick-off Sessions
<!-- <div class="photo-grid">
  <img class="lightboxable"
       src="{{ '/assets/event_photos/Online/Zoom1.png' | relative_url }}"
       alt="Hackathon Zoom session 1">

  <img class="lightboxable"
       src="{{ '/assets/event_photos/Online/Zoom2.png' | relative_url }}"
       alt="Hackathon Zoom session 2">

  <img class="lightboxable"
       src="{{ '/assets/event_photos/Online/Zoom3.png' | relative_url }}"
       alt="Hackathon Zoom session 3">
</div> -->

<!-- Global Lightbox Modal (one-time) -->
<div id="lightbox" class="lb" aria-hidden="true">
  <div class="lb__backdrop" data-lb-close></div>

  <div class="lb__dialog" role="dialog" aria-modal="true" aria-label="Image preview">
    <button class="lb__close" type="button" aria-label="Close" data-lb-close>&times;</button>
    <img id="lightbox-img" class="lb__img" alt="">
    <div id="lightbox-cap" class="lb__cap"></div>
  </div>
</div>

<script>
(function () {
  const lb = document.getElementById('lightbox');
  const lbImg = document.getElementById('lightbox-img');
  const lbCap = document.getElementById('lightbox-cap');

  function openLightbox(src, alt) {
    lbImg.src = src;
    lbImg.alt = alt || '';
    lbCap.textContent = alt || '';
    lb.classList.add('is-open');
    lb.setAttribute('aria-hidden', 'false');
    document.body.style.overflow = 'hidden';
  }

  function closeLightbox() {
    lb.classList.remove('is-open');
    lb.setAttribute('aria-hidden', 'true');
    lbImg.src = '';
    document.body.style.overflow = '';
  }

  // Works for all current and future images with class="lightboxable"
  document.addEventListener('click', (e) => {
    const img = e.target.closest('img.lightboxable');
    if (!img) return;
    const src = img.getAttribute('data-full') || img.currentSrc || img.src;
    openLightbox(src, img.alt);
  });

  // Close on backdrop or close button
  lb.querySelectorAll('[data-lb-close]').forEach(el => {
    el.addEventListener('click', closeLightbox);
  });

  // Close on ESC
  document.addEventListener('keydown', (e) => {
    if (e.key === 'Escape' && lb.classList.contains('is-open')) closeLightbox();
  });
})();
</script>


<script>
function updateClocks() {
  const now = new Date();
  
  // Setup TWO formatting options (12-hour and 24-hour)
  const timeOptions12 = { hour: '2-digit', minute: '2-digit', second: '2-digit', hour12: true };
  const timeOptions24 = { hour: '2-digit', minute: '2-digit', second: '2-digit', hour12: false };
  const dateOptions = { weekday: 'short', month: 'short', day: 'numeric' };

  // --- 12-HOUR FORMAT CLOCKS (US) ---
  document.getElementById('time-la').textContent = now.toLocaleTimeString('en-US', { ...timeOptions12, timeZone: 'America/Los_Angeles' });
  document.getElementById('date-la').textContent = now.toLocaleDateString('en-US', { ...dateOptions, timeZone: 'America/Los_Angeles' });

  document.getElementById('time-chi').textContent = now.toLocaleTimeString('en-US', { ...timeOptions12, timeZone: 'America/Chicago' });
  document.getElementById('date-chi').textContent = now.toLocaleDateString('en-US', { ...dateOptions, timeZone: 'America/Chicago' });

  document.getElementById('time-knox').textContent = now.toLocaleTimeString('en-US', { ...timeOptions12, timeZone: 'America/New_York' });
  document.getElementById('date-knox').textContent = now.toLocaleDateString('en-US', { ...dateOptions, timeZone: 'America/New_York' });

  // --- 24-HOUR FORMAT CLOCKS (INTERNATIONAL) ---
  document.getElementById('time-london').textContent = now.toLocaleTimeString('en-US', { ...timeOptions24, timeZone: 'Europe/London' });
  document.getElementById('date-london').textContent = now.toLocaleDateString('en-US', { ...dateOptions, timeZone: 'Europe/London' });

  document.getElementById('time-berlin').textContent = now.toLocaleTimeString('en-US', { ...timeOptions24, timeZone: 'Europe/Berlin' });
  document.getElementById('date-berlin').textContent = now.toLocaleDateString('en-US', { ...dateOptions, timeZone: 'Europe/Berlin' });

  document.getElementById('time-doha').textContent = now.toLocaleTimeString('en-US', { ...timeOptions24, timeZone: 'Asia/Qatar' });
  document.getElementById('date-doha').textContent = now.toLocaleDateString('en-US', { ...dateOptions, timeZone: 'Asia/Qatar' });

  document.getElementById('time-delhi').textContent = now.toLocaleTimeString('en-US', { ...timeOptions24, timeZone: 'Asia/Kolkata' });
  document.getElementById('date-delhi').textContent = now.toLocaleDateString('en-US', { ...dateOptions, timeZone: 'Asia/Kolkata' });

  document.getElementById('time-tokyo').textContent = now.toLocaleTimeString('en-US', { ...timeOptions24, timeZone: 'Asia/Tokyo' });
  document.getElementById('date-tokyo').textContent = now.toLocaleDateString('en-US', { ...dateOptions, timeZone: 'Asia/Tokyo' });
}

updateClocks();
setInterval(updateClocks, 1000);
</script>