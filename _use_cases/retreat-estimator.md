---
title: "Retreat Estimator - From Lead to Proposal in Minutes"
excerpt: "To streamline lead qualification and improve response time, we built a public-facing cost estimator for Midstay, paired with an automated proposal request flow. Users get instant pricing and can request a tailored proposal via a guided form. Internally, the team can generate branded proposal PDFs in minutes using prefilled data. This system increased qualified leads and reduced manual sales effort."
image: 
  path: assets/images/use_cases/proposal.jpg
  thumbnail: assets/images/use_cases/proposal.jpg
  caption: "Retreat Estimator at [Midstay](https://www.midstay.com)"
---

To streamline lead qualification and improve response time, we built a public-facing cost estimator for Midstay, paired with an automated proposal request flow. Users get instant pricing and can request a tailored proposal via a guided form. Internally, the team can generate branded proposal PDFs in minutes using prefilled data.<br>

This system increased qualified leads and reduced manual sales effort. Moreover, by cutting the proposal turnaround time from several days to just 1–2, we were able to respond while the lead was still warm — increasing conversion rates and strengthening the perceived professionalism of the sales process.

### Problem  
Handling retreat inquiries manually was slowing down the sales team. Midstay needed a faster way to qualify leads and generate proposals — without the back-and-forth.

---

### Solution  
We built a lightweight **retreat cost estimator** and connected it to a streamlined **proposal request flow**. Visitors get instant price ranges, and if interested, they can request a custom proposal via a guided form and email flow.

---

### Screens & Flow

#### 1. Public Estimator UI  
<p>Users input group size, location, preferences — and get real-time cost estimates.</p>
<img src="/assets/images/use_cases/midstay-estimator.png" class="align-center" alt="">

#### 2. CTA → Proposal Request  
<p>After seeing the estimate, users can click a CTA to request a full proposal.</p>  
<img src="/assets/images/use_cases/email-cta.png" class="align-center" alt="">

#### 3. Email Form  
<p>They’re taken to a simple form to submit details like name, company, goals, and preferred dates.</p>
<div class="proposal-request">
  <img src="/assets/images/use_cases/contact-form.png" alt=""> 
  <img src="/assets/images/use_cases/detailed-plan-form.png" alt=""> 
</div>

#### 4. Internal Proposal Generator  
<p>Once submitted, the team can generate a detailed 20-page proposal, prefilled with content based on internal logic and enriched with manually added data through our proposal flow UI — including itineraries, budget breakdowns, and more.</p>
<img src="/assets/images/use_cases/proposal-generator-example.jpg" class="align-center" alt=""> 

---

### Outcome  
- Increased number of **qualified proposal requests**  
- **Faster turnaround** from inquiry to proposal  
- Reduced manual workload for sales and ops  
- A seamless experience for potential clients

---

### Technical Notes
- Built with: Ruby on Rails, Hotwire, Sidekiq
- Integrations: Hubspot API, Google Slides API

