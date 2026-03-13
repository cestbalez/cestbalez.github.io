---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
paginate: true
posts_limit: 0
description: "A small set of consulting services for founders and product teams who want help scoping and building thoughtful software."
open_graph:
  image:
    path: /assets/images/logo.webp
    caption: Magnus S. Remøe
permalink: /services/
---

<section id="intro">
  <p>
    <strong><em>
      I work with a small number of founders and product teams each year to scope and build thoughtful software, usually internal tools, automation backends, and focused MVPs.
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

<section id="featured-products" class="featured-products">
  <h2>Example Builds</h2>
  <p class="section-subtitle">
    These are representative examples of the kinds of tools I build through the services above. They are here to make the work more concrete, not to present off-the-shelf products.
  </p>

  <div class="product-grid">
    <div class="product-card">
      <h3><a href="/products/quoting-engine">Quoting Engine</a></h3>
      <p class="product-tag">Automation or UI Tool</p>
      <p class="product-card-desc">
        Automate pricing logic and generate scoped quotes in minutes, with or without a web interface. Ideal for SaaS, logistics, or agency quoting.
      </p>
    </div>

    <div class="product-card">
      <h3><a href="/products/proposal-builder">Proposal Builder</a></h3>
      <p class="product-tag">Automation or UI Tool</p>
      <p class="product-card-desc">
        Create branded, exportable proposals automatically, from your CRM, pricing system, or internal logic. Great for sales teams who move fast.
      </p>
    </div>
  </div>

  <p class="product-list-cta">
    <a href="/products" class="text-link">See more example builds →</a>
  </p>
</section>

<section id="testimonials">
  <h2>What People Say</h2>

  {% include testimonials.html %}
</section>

<section id="use-cases">
  <h2>Featured work</h2>
  {%- for entry in site.use_cases limit: 3 -%}
    {% include entry.html show_image=false %}
  {%- endfor -%}
</section>

<div class="featured-quote">
  <p class="quote-text">
    "Magnus was a great colleague, smart, dependable, and a fast learner. He consistently delivered high-quality work and was easy to collaborate with."
  </p>
  <p class="quote-author">– Even Egeberg, VP of Product Operations at Attensi</p>
</div>

<section id="about-me">
  {% include about-me.html %}
</section>

<section id="experiences">
  <h2>Where I've Worked</h2>
  {% include experiences.html %}
</section>
