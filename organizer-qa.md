---
layout: page
title: Organizer Q&A
menu_title: Organizer Q&A
permalink: /organizer-qa/
---

<style>
/* --- PDF & Video Embed Wrappers --- */
.embed-wrapper {
  position: relative;
  padding-bottom: 50%;
  height: 100%;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 6px 18px rgba(0,0,0,0.08);
  border: 1px solid #eef0f5;
  background: #f8f9fa;
}
.embed-wrapper iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 0;
}

/* --- Margin specifically for the top PDF --- */
.pdf-container {
  margin-bottom: 1.5rem;
}

/* --- Expandable Video Accordion --- */
.video-accordion {
  background: #fafbfd;
  border: 1px solid #eef0f5;
  border-radius: 12px;
  padding: 1rem 1.5rem;
  margin-bottom: 3rem;
  box-shadow: 0 2px 8px rgba(0,0,0,0.03);
  transition: all 0.3s ease;
}
.video-accordion summary {
  font-weight: 600;
  color: #1d4ed8;
  font-size: 1.1rem;
  cursor: pointer;
  list-style: none; /* Hides default triangle */
  display: flex;
  align-items: center;
  gap: 10px;
}
.video-accordion summary::-webkit-details-marker {
  display: none; /* Hides default triangle in Safari */
}
.video-accordion summary:hover {
  color: #2d55a9;
}
.video-accordion[open] summary {
  margin-bottom: 1.5rem;
  border-bottom: 2px solid #eef2ff;
  padding-bottom: 1rem;
}

/* Custom animated arrow for the accordion */
.accordion-icon {
  color: #ff8200;
  font-size: 1.2rem;
  transition: transform 0.3s ease;
}
.video-accordion[open] .accordion-icon {
  transform: rotate(90deg);
}

/* --- Q&A Light Box Styles --- */
.qa-topic-box {
  background: #fafbfd;
  border: 1px solid #eef0f5;
  border-radius: 14px;
  padding: 2rem;
  margin-bottom: 2rem;
  box-shadow: 0 2px 8px rgba(0,0,0,0.03);
}
.qa-topic-title {
  color: #1d2a56;
  font-size: 1.4rem;
  font-weight: 700;
  margin-top: 0;
  margin-bottom: 1.5rem;
  border-bottom: 2px solid #eef2ff;
  padding-bottom: 0.75rem;
}
.qa-item {
  margin-bottom: 1.5rem;
}
.qa-item:last-child {
  margin-bottom: 0;
}

/* Flexbox aligns the Q/A markers perfectly with multi-line text */
.qa-question, .qa-answer {
  display: flex;
  align-items: flex-start;
  gap: 15px;
}
.qa-question {
  font-weight: 600;
  color: rgb(18, 48, 131);
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
}
.qa-answer {
  color: #475569;
  line-height: 1.6;
}
.qa-marker {
  color: #ff8200; /* UTK Orange */
  font-weight: 800;
  font-size: 1.2rem;
  flex-shrink: 0; /* Prevents the letter from squishing */
  line-height: 1.4;
  margin-top: -2px;
}
.qa-answer .qa-marker {
  line-height: 1.6; /* Matches the answer paragraph spacing */
}
</style>

<!-- 1. The PDF Slide Carousel -->
<div class="pdf-container">
  <div class="embed-wrapper">
    <iframe src="https://drive.google.com/file/d/1xCrnVPXWQapJ0gY0M9aZ3URllpDPD3S-/preview" allow="autoplay" allowfullscreen></iframe>
  </div>
</div>

<!-- 2. The Expandable Video Box -->
<details class="video-accordion">
  <summary>
    <i class="bi bi-play-circle-fill accordion-icon"></i> 
    <span>Watch the full Q&A Meeting Recording</span>
  </summary>
  <div class="embed-wrapper">
    <iframe src="https://drive.google.com/file/d/1NBUwv_mLacANxs4T35MaaRf92QW8i7rl/preview" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>
</details>

<!-- 3. Q&A Section -->
<div class="qa-topic-box">
  <h2 class="qa-topic-title">Local Site Logistics & Registration</h2>
  
  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>Is there an expected number of participants or teams per local site?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>The number of participants is entirely up to the local organizer and the room's capacity. Previous sites have hosted anywhere from 5 to over 30 participants depending on how broadly the event was advertised locally. If a physical room reaches capacity, the central registration system can cap sign-ups for that specific local site.</span>
    </div>
  </div>

  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>Are there registration fees for participants?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>No, participation in the event is completely free of charge for everyone. All hackathon activities are designed to be cost-neutral to ensure broad accessibility.</span>
    </div>
  </div>

  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>Can existing grants cover local costs, or can we invite local sponsors?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>Local organizers can use existing grants to cover food and coffee, provided they clear this with their local research office. Local sites are also highly encouraged to invite local sponsors for support or to fund local prizes. We are delighted to highlight any sponsor acknowledgments from local site organizers on the central hackathon website.</span>
    </div>
  </div>
</div>

<div class="qa-topic-box">
  <h2 class="qa-topic-title">Participants & Team Formation</h2>
  
  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>Who can participate, and is machine learning expertise required?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>Participation is open to everyone—from high school students to senior scientists—provided local institutional rules regarding external visitors and minors are strictly followed. Participants do not need to be machine learning experts. Understanding the domain problem is far more critical, and the event is specifically designed to pair domain experts with coders.</span>
    </div>
  </div>

  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>How does team formation work?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>Participants will gain access to a Miro board the day before the event to self-organize around specific problems. Teams frequently form heterogeneously across global time zones, though pre-formed local teams are also completely acceptable. Teams generally select problems without any noticeable correlation to their geographic site.</span>
    </div>
  </div>
</div>

<div class="qa-topic-box">
  <h2 class="qa-topic-title">Problems, Datasets & Resources</h2>
  
  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>What types of problems and datasets are acceptable?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>Datasets should ideally focus on microscopy (including optical, mass spectrometry, or scanning probe), but computational models like digital twins are also welcome. Data from previous publications can be used as long as the hackathon workflow and results remain open-source. Very large datasets should be decimated to a representative size suitable for hosting via platforms like Google Colab.</span>
    </div>
  </div>

  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>When is the deadline for submitting problems?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>Organizers ask that datasets and problems be submitted anytime from now until two weeks before the hackathon. To ensure fairness across the competition, all problems are kept confidential and revealed to participants exactly one day before the event begins.</span>
    </div>
  </div>

  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>Are computational resources provided, or do local sites need to supply them?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>Local sites are not expected to provide any special computational resources. Participants generally rely on standard cloud access like Google Colab. The central organizing team is also exploring sponsorships to potentially provide additional cloud computing resources to participants.</span>
    </div>
  </div>

  <div class="qa-item">
    <div class="qa-question">
      <span class="qa-marker">Q:</span>
      <span>How are projects evaluated, and can local organizers join the jury?</span>
    </div>
    <div class="qa-answer">
      <span class="qa-marker">A:</span>
      <span>Submissions are judged by a multi-person panel using a non-disclosed rubric focused on domain understanding, physical significance, and solution robustness. Local site organizers are strongly encouraged to join the jury. Expanding the jury's domain expertise is critical for accurately evaluating the physical significance of the proposed solutions.</span>
    </div>
  </div>
</div>