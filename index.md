---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
paginate: true
posts_limit: 0
description: "I build software products, write about engineering and entrepreneurship, and explore what it means to build a meaningful, independent life."
open_graph:
  image:
    path: /assets/images/logo.webp
    caption: Magnus S. Remøe
---

<section id="intro">
  <p>
    <strong><em>
      I build software products, write about engineering and entrepreneurship, and explore what it means to build a meaningful, independent life.
    </em></strong>
  </p>
</section>

<section id="about-me">
  {% include about-me.html %}
</section>

<section id="writings">
  <h2>Writings</h2>

  {%- for entry in site.posts limit: 3 -%}
    {% include entry.html %}
  {%- endfor -%}

  <p class="product-list-cta">
    <a href="/blog" class="text-link">See all writings →</a>
  </p>
</section>

<section id="experiences">
  <h2>Where I've Worked</h2>
  {% include experiences.html %}
</section>

<section id="work-with-me">
  <h2>Work with me</h2>

  <p>
    Alongside my day-to-day work, I occasionally take on a small number of consulting projects.
    I usually work with founders and small teams who want help clarifying what to build, scoping
    it well, and shipping something solid without unnecessary overhead.
  </p>

  <p>
    If you are working through a technical decision, trying to move faster, or want an experienced
    builder to help shape and deliver a focused project, I would love to hear what you are building.
  </p>

  <a href="/services" class="cta-button">
    See how I work
  </a>
</section>
