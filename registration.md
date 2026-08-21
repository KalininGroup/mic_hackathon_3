---
layout: page
title: Register for the Hackathon
menu_title: Register
menu_icon: pencil-square
permalink: /registration/
published: true
---

<!-- <div style="
  background: #e9faed;
  border:1px solid #c0f5cc;
  color: #0a4e1a;
  padding:1rem 1.2rem;
  border-radius:10px;
  font-size:1.05rem;
  font-weight:600;
  margin-bottom:1.5rem;
  text-align: center;
">
  Registration will be open soon. Stay tuned!
</div> -->

<!-- <div style="
  background: #fdecea;
  border:1px solid #f5c2c0;
  color: #b71c1c;
  padding:1rem 1.2rem;
  border-radius:10px;
  font-size:1.05rem;
  font-weight:600;
  margin-bottom:1.5rem;
">
  Registration is now closed. If you still wish to participate, please email Alla Slautina
  <a href="mailto:aslautin@utk.edu" style="color:#b71c1c; text-decoration:underline;">
    (aslautin@utk.edu)
  </a>
  to request access for online attendance.
</div> -->

<script>
document.addEventListener("DOMContentLoaded", function () {
  const form = document.getElementById("reg-card");
  if (form) {
    form.style.display = "block"; // block - show entire form | none - hide entire form
  }
});
</script>

<style>
/* keep everything inside the card */
.reg-card, .reg-card * { box-sizing: border-box; }

.reg-card{
  max-width: 820px; margin: 1.2rem auto; padding: 1.2rem 1.4rem;
  background:#fff; border:1px solid #e6e6e6; border-radius:14px;
  box-shadow: 0 6px 18px rgba(0,0,0,.05);
  overflow:hidden;
}

.reg-form p, .reg-form fieldset{ margin: .9rem 0; }
.reg-form label{ font-weight:600; display:block; }
.reg-form input[type="text"],
.reg-form input[type="email"],
.reg-form textarea,
.reg-form select{
  width:100%; padding:.65rem .75rem; border:1px solid #d6d6d6; border-radius:10px;
  outline:none; background:#fafafa; transition: box-shadow .15s, border-color .15s, background .15s;
}
.reg-form textarea{ resize: vertical; min-height: 120px; }
.reg-form input:focus, .reg-form textarea:focus, .reg-form select:focus{
  border-color:#3a7bd5; background:#fff; box-shadow: 0 0 0 3px rgba(58,123,213,.15);
}

.reg-form fieldset{
  border:1px solid #eee; border-radius:12px; padding: .8rem 1rem;
}
.reg-form legend{ font-weight:700; padding:0 .4rem; }
.required{ color:#d00; }

/* prettier, even checklist: responsive grid */
.checkgrid{
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap:.5rem 1rem;
}
.checkgrid label{
  display:flex; align-items:flex-start; gap:.5rem;
  padding:.45rem .6rem; border:1px solid #eee; border-radius:10px; background:#fafafa;
}
.checkgrid input{ margin-top:.2rem; }

/* GREYED-OUT CLOSED SITES */
.checkgrid label.site-closed{
  opacity: 0.45;
  cursor: not-allowed;
}
.checkgrid label.site-closed input{
  cursor: not-allowed;
}

/* button */
.btn-primary{
  display:inline-block; padding:.7rem 1.1rem; border-radius:10px;
  border:1px solid #2e6bd6; background:#3a7bd5; color:#fff; font-weight:700;
  text-decoration:none; cursor:pointer; transition: transform .03s ease, box-shadow .15s;
}
.btn-primary:hover{ box-shadow: 0 8px 18px rgba(58,123,213,.25); }
.btn-primary:active{ transform: translateY(1px); }
.hint{ font-size:.9rem; color:#666; margin-top:.3rem; }

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-5px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>

<p class="hint">
  Pick the site that’s closest to you (or choose <strong><a href="{{ '/registration/' | relative_url }}?site=Online" class="btn-primary;" style="color: #3a7bd5; text-decoration: underline; cursor: pointer;">Online</a></strong>). 
  <br><br>
  <em><strong>Note:</strong> We are actively adding more hosting sites! We recommend registering now to get early access to Slack and Miro for team building. If a location closer to you is announced later, you can easily change your site selection by replying to your confirmation email.</em><br><br>
</p>


{% raw %}
<iframe name="gform_target" id="gform_target" style="display:none;"></iframe>

<div class="reg-card" id="reg-card">
  <form class="reg-form"
        action="https://docs.google.com/forms/d/e/1FAIpQLSdi2pCwZvjEdZDKpJhn4xhAve89AXFtOqG60CwQmVFla1ryJg/formResponse"
        method="POST"
        target="gform_target"
        id="active-reg-form">
    <p>
      <label>Name <span class="required">*</span><br>
        <input type="text" name="entry.2092238618" required placeholder="Your full name">
      </label>
    </p>
    <p>
      <label>Email <span class="required">*</span><br>
        <input type="email" 
               name="entry.1556369182" 
               required 
               placeholder="e.g., you@university.edu"
               pattern="[a-z0-9._%+\-]+@[a-z0-9.\-]+\.[a-z]{2,}$"
               title="Please enter a complete email address (e.g., you@university.edu)">
      </label>
    </p>
    <p>
      <label>Organization <span class="required">*</span><br>
        <input type="text" name="entry.479301265" required placeholder="e.g., University of Tennessee">
      </label>
    </p>
    <fieldset>
      <legend>Role in your Organization <span class="required">*</span></legend>
      <label><input type="radio" name="entry.1617455898" value="Undergraduate Student" required> Undergraduate Student</label>
      <label><input type="radio" name="entry.1617455898" value="Graduate Student"> Graduate Student</label>
      <label><input type="radio" name="entry.1617455898" value="Postdoctoral Associates"> Postdoctoral Associates</label>
      <label><input type="radio" name="entry.1617455898" value="Faculty"> Faculty</label>
      <label><input type="radio" name="entry.1617455898" value="__other_option__"> Other</label>      
      <!-- Notice the ID and the default hidden state we added here -->
      <div id="other-role-container" style="display: none; margin-top: 0.5rem; animation: fadeIn 0.2s ease;">
        <input type="text" name="entry.1617455898.other_option_response" placeholder="Please specify your role...">
      </div>
    </fieldset>
    <fieldset>
      <legend>Where do you want to attend the hackathon? <span class="required">*</span></legend>
      <div class="checkgrid">
        <label><input type="checkbox" name="entry.1753222212" value="Online"> Online</label>
        <label><input type="checkbox" name="entry.1753222212" value="University of Tennessee, Knoxville"> University of Tennessee, Knoxville</label>
        <label><input type="checkbox" name="entry.1753222212" value="Italian Institute of Technology - Genoa, Italy"> Italian Institute of Technology - Genoa, Italy</label>
        <label><input type="checkbox" name="entry.1753222212" value="North Carolina State University"> North Carolina State University</label>
        <label><input type="checkbox" name="entry.1753222212" value="Max Planck Institute for Solid State Research - Stuttgart, Germany"> Max Planck Institute for Solid State Research - Stuttgart, Germany</label>
        <label><input type="checkbox" name="entry.1753222212" value="Sungkyunkwan University - Suwon, Republic of Korea"> Sungkyunkwan University - Suwon, Republic of Korea</label>
        <label><input type="checkbox" name="entry.1753222212" value="Humboldt University of Berlin - Berlin, Germany"> Humboldt University of Berlin - Berlin, Germany</label>
        <label><input type="checkbox" name="entry.1753222212" value="The University of Manchester - Manchester, UK"> The University of Manchester - Manchester, UK</label>
        <label><input type="checkbox" name="entry.1753222212" value="Kanazawa University - Kanazawa, Japan"> Kanazawa University - Kanazawa, Japan</label>
        <label><input type="checkbox" name="entry.1753222212" value="Technical University of Darmstadt - Darmstadt, Germany"> Technical University of Darmstadt - Darmstadt, Germany</label>
        <label><input type="checkbox" name="entry.1753222212" value="University of Leeds - Leeds, UK"> University of Leeds - Leeds, UK</label>
        <label><input type="checkbox" name="entry.1753222212" value="Trinity College Dublin - Dublin, Ireland"> Trinity College Dublin - Dublin, Ireland</label>
        <label><input type="checkbox" name="entry.1753222212" value="Ulster University - Belfast, UK"> Ulster University - Belfast, UK</label>
        <label><input type="checkbox" name="entry.1753222212" value="Institute of Industrial Science, The University of Tokyo - Japan"> Institute of Industrial Science, The University of Tokyo - Japan</label>
        <label><input type="checkbox" name="entry.1753222212" value="Institute of Materials Science of Barcelona - Barcelona, Spain"> Institute of Materials Science of Barcelona - Barcelona, Spain</label>
        <label><input type="checkbox" name="entry.1753222212" value="Korea Advanced Institute of Science & Technology (KAIST) - Republic of Korea"> Korea Advanced Institute of Science & Technology (KAIST) - Republic of Korea</label>
        <label><input type="checkbox" name="entry.1753222212" value="AISCIA Informatics - Doha, Qatar"> AISCIA Informatics - Doha, Qatar</label>
        <label><input type="checkbox" name="entry.1753222212" value="University of Sheffield - Sheffield, UK"> University of Sheffield - Sheffield, UK</label>
        <label><input type="checkbox" name="entry.1753222212" value="Ernst Ruska-Centre for Microscopy and Spectroscopy with Electrons - Jülich, Germany"> Ernst Ruska-Centre for Microscopy and Spectroscopy with Electrons - Jülich, Germany</label>
        <label><input type="checkbox" name="entry.1753222212" value="Institute for Bioengineering of Catalonia (IBEC) - Barcelona, Spain"> Institute for Bioengineering of Catalonia (IBEC) - Barcelona, Spain</label>
        <label><input type="checkbox" name="entry.1753222212" value="Department of Materials, University of Oxford - Oxford, UK"> Department of Materials, University of Oxford - Oxford, UK</label>
        <label><input type="checkbox" name="entry.1753222212" value="Institut Català de Nanociència i Nanotecnologia (ICN2) - Barcelona, Spain"> Institut Català de Nanociència i Nanotecnologia (ICN2) - Barcelona, Spain</label>
        <label><input type="checkbox" name="entry.1753222212" value="Norwegian University of Science and Technology (NTNU) - Trondheim, Norway"> Norwegian University of Science and Technology (NTNU) - Trondheim, Norway</label>
        <label><input type="checkbox" name="entry.1753222212" value="Leibniz Institute for New Materials (INM) - Saarbrücken, Germany"> Leibniz Institute for New Materials (INM) - Saarbrücken, Germany</label>
        <label><input type="checkbox" name="entry.1753222212" value="University of Virginia"> University of Virginia</label>
        <label><input type="checkbox" name="entry.1753222212" value="Johns Hopkins University"> Johns Hopkins University</label>
        <label><input type="checkbox" name="entry.1753222212" value="Georgia Institute of Technology"> Georgia Institute of Technology</label>
        <label><input type="checkbox" name="entry.1753222212" value="Chalmers University of Technology - Gothenburg, Sweden"> Chalmers University of Technology - Gothenburg, Sweden</label>
        <label><input type="checkbox" name="entry.1753222212" value="Pennsylvania State University"> Pennsylvania State University</label>
        <label><input type="checkbox" name="entry.1753222212" value="Columbia University"> Columbia University</label>
        <label><input type="checkbox" name="entry.1753222212" value="Swiss Federal Technology Institute of Lausanne (EPFL) - Lausanne, Switzerland"> Swiss Federal Technology Institute of Lausanne (EPFL) - Lausanne, Switzerland</label>
        <label><input type="checkbox" name="entry.1753222212" value="Argonne National Laboratory"> Argonne National Laboratory</label>
        <label><input type="checkbox" name="entry.1753222212" value="Northwestern University"> Northwestern University</label>
        <label><input type="checkbox" name="entry.1753222212" value="Texas A&M University"> Texas A&M University</label>
        <label><input type="checkbox" name="entry.1753222212" value="Oklahoma State University"> Oklahoma State University</label>
        <label><input type="checkbox" name="entry.1753222212" value="Ohio State University"> Ohio State University</label>
        <label><input type="checkbox" name="entry.1753222212" value="Rice University"> Rice University</label>
        <label><input type="checkbox" name="entry.1753222212" value="University of Houston"> University of Houston</label>
        <label><input type="checkbox" name="entry.1753222212" value="Indiana University Bloomington"> Indiana University Bloomington</label>
        <!-- <label><input type="checkbox" name="entry.1753222212" value="University College London - London, UK"> University College London - London, UK</label> -->
      </div>
    </fieldset>
    <p>
      <label>What is your area of research?<br>
        <textarea name="entry.2109138769" rows="4" placeholder="e.g., electron microscopy, optimization, active learning"></textarea>
      </label>
    </p>
    <p><button class="btn-primary" type="submit" id="reg-submit">Submit registration</button></p>
  </form>

  <!-- success alert -->
  <div id="reg-success" style="display:none; margin-top:.8rem; padding:.75rem 1rem; border:1px solid #c8e6c9; background:#e8f5e9; border-radius:10px; color:#256029; line-height: 1.5;">
    ✅ <strong>Thank you! Your registration was submitted.</strong><br><br>
    You will receive a confirmation email within the next <strong>5 working days</strong>. If you have not received your confirmation after this period, please submit your registration again or contact Alla Slautina at <a href="mailto:aslautin@utk.edu" style="color:#256029; text-decoration:underline;">aslautin@utk.edu</a>.
  </div>
</div>

<script>
(function() {
  const form   = document.getElementById('active-reg-form');
  const btn    = document.getElementById('reg-submit');
  const ok     = document.getElementById('reg-success');
  const iframe = document.getElementById('gform_target');

  iframe.addEventListener('load', function () {
    if (!form.dataset.submitted) return;
    btn.disabled = false;
    btn.textContent = 'Submit registration';
    form.reset();
    ok.style.display = 'block';
    form.dataset.submitted = '';
  });

  form.addEventListener('submit', function () {
    ok.style.display = 'none';
    btn.disabled = true;
    btn.textContent = 'Submitting...';
    form.dataset.submitted = '1';
  });
})();
</script>
{% endraw %}

<script>
(function(){
  const params = new URLSearchParams(location.search);
  const site = params.get('site');
  if(!site) return;

  // Find the checkbox group and tick the one that matches
  const boxes = document.querySelectorAll('input[type="checkbox"][name="entry.1753222212"]');
  let matched = false;
  boxes.forEach(b => {
    if (b.value.trim() === site.trim()) {
      b.checked = true;
      matched = true;
    }
  });
  if (matched) {
    const fieldset = boxes[0].closest('fieldset') || boxes[0].parentElement;
    fieldset && fieldset.scrollIntoView({behavior:'smooth', block:'start'});
  }
})();
</script>

<!-- LOCK SPECIFIC SITES -->
<script>
(function(){
  const boxes = document.querySelectorAll('input[type="checkbox"][name="entry.1753222212"]');
  const MESSAGE = 'In-person registration for this site is now closed. Please select Online attendance.';

  // 1. THE APPROVED LIST
  // Add exact site names here.
  // Comment specific site out with // to lock it.
  // If a site is COMMENTED OUT in this list, it will be greyed out and locked.
  const openSites = [
    'Online',
    'University of Tennessee, Knoxville',
    'Italian Institute of Technology - Genoa, Italy',
    'North Carolina State University',
    'Max Planck Institute for Solid State Research - Stuttgart, Germany',
    'Sungkyunkwan University - Suwon, Republic of Korea',
    'Humboldt University of Berlin - Berlin, Germany',
    'The University of Manchester - Manchester, UK',
    'Kanazawa University - Kanazawa, Japan',
    'Technical University of Darmstadt - Darmstadt, Germany',
    'University of Leeds - Leeds, UK',
    'Trinity College Dublin - Dublin, Ireland',
    'Ulster University - Belfast, UK',
    'Institute of Industrial Science, The University of Tokyo - Japan',
    'Institute of Materials Science of Barcelona - Barcelona, Spain',
    'Korea Advanced Institute of Science & Technology (KAIST) - Republic of Korea',
    'AISCIA Informatics - Doha, Qatar',
    'University of Sheffield - Sheffield, UK',
    'Ernst Ruska-Centre for Microscopy and Spectroscopy with Electrons - Jülich, Germany',
    'Institute for Bioengineering of Catalonia (IBEC) - Barcelona, Spain',
    'Department of Materials, University of Oxford - Oxford, UK',
    'Institut Català de Nanociència i Nanotecnologia (ICN2) - Barcelona, Spain',
    'Norwegian University of Science and Technology (NTNU) - Trondheim, Norway',
    'Leibniz Institute for New Materials (INM) - Saarbrücken, Germany',
    'University of Virginia',
    'Johns Hopkins University',
    'Georgia Institute of Technology',
    'Chalmers University of Technology - Gothenburg, Sweden',
    'Pennsylvania State University',
    'Columbia University',
    'Swiss Federal Technology Institute of Lausanne (EPFL) - Lausanne, Switzerland',
    'Argonne National Laboratory',
    'Northwestern University',
    'Texas A&M University',
    'Oklahoma State University',
    'Ohio State University',
    'Rice University',
    'University of Houston',
    'Indiana University Bloomington',
  //  'University College London - London, UK',
  ];

  boxes.forEach(box => {
    const val = box.value.trim();
    
    // 2. CHECK THE LIST
    // This checks if the current checkbox is included in your openSites array
    const isOpen = openSites.includes(val); 

    if (!isOpen) {
      // mark visual state
      const label = box.closest('label');
      if (label) label.classList.add('site-closed');

      // ensure it starts unchecked
      box.checked = false;

      // intercept clicks
      box.addEventListener('click', function(e){
        e.preventDefault();
        box.checked = false;
        alert(MESSAGE);
      });

      // also catch clicks on the label text
      const labelEl = box.closest('label');
      if (labelEl) {
        labelEl.addEventListener('click', function(e){
          e.preventDefault();
          box.checked = false;
          alert(MESSAGE);
        });
      }
    }
  });
})();
</script>

<script>
document.addEventListener("DOMContentLoaded", function() {
  const roleRadios = document.querySelectorAll('input[name="entry.1617455898"]');
  const otherContainer = document.getElementById('other-role-container');

  roleRadios.forEach(radio => {
    radio.addEventListener('change', function() {
      // If 'Other' is selected, show the box. Otherwise, hide it.
      if (this.value === '__other_option__') {
        otherContainer.style.display = 'block';
      } else {
        otherContainer.style.display = 'none';
      }
    });
  });
});
</script>