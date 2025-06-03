---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
paginate: true
posts_limit: 0
description: "Rails developer & startup CTO helping businesses scale through clean, maintainable systems. I also write about entrepreneurship, tech, and building a meaningful, independent life."
open_graph:
  image:
    path: /assets/images/logo.webp
    caption: Magnus S. Remøe
---

<section id="intro">
  <p>
    <strong><em>
      Technical partner for startups and SMBs, helping you build fast, scalable products – from MVPs to microservices.
      I offer productized Rails services using Hotwire & AI, shipped in weeks with clean, maintainable code.
    </em></strong>
  </p>
  <a href="#" onclick="Calendly.initPopupWidget({url: 'https://calendly.com/magnusremoe/new-meeting'}); return false;" class="cta-button">
    Let's Talk
  </a>
</section>

<section id="services">
  <h2>What I Offer</h2>
  {% include services.html %}
</section>

<section id="about-me">
  {% include about-me.html %}
</section>

<section class="experiences">
  <h2>Where I've Worked</h2>
  {% include experiences.html %}
</section>
