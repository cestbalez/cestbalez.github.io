---
title: "Retreat Estimator - From Lead to Proposal in Minutes"
excerpt: "To streamline lead qualification and improve response time, we built a public-facing cost estimator for Midstay, paired with an automated proposal request flow. Users get instant pricing and can request a tailored proposal via a guided form. Internally, the team can generate branded proposal PDFs in minutes using prefilled data. This system increased qualified leads and reduced manual sales effort."
image: 
  path: assets/images/use_cases/midstay-estimator.png
  thumbnail: assets/images/use_cases/midstay-estimator-thumb.png
  caption: "Photo from [Pexels](https://www.pexels.com)"
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
Users input group size, location, preferences — and get real-time cost estimates.  
`[screenshot: estimator form]`

#### 2. CTA → Proposal Request  
After seeing the estimate, users can click a CTA to request a full proposal.  
`[screenshot: CTA section]`

#### 3. Email Form  
They’re taken to a simple form to submit details like name, company, goals, and preferred dates.  
`[screenshot: form or form preview]`

#### 4. Internal Proposal Generator  
Once submitted, the team can generate a proposal with prefilled content based on internal logic.  
`[screenshot: redacted or dummy-data PDF preview]`

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

